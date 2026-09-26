---
title: ExampleMod/ExampleModPlugin.cs

---

# ExampleMod/ExampleModPlugin.cs



## Namespaces

| Name           |
| -------------- |
| **[ExampleMod2](../Namespaces/namespace_example_mod2/)**  |
| **[Microsoft::Xna::Framework](../Namespaces/namespace_microsoft_1_1_xna_1_1_framework/)**  |
| **[Microsoft::Xna::Framework::Graphics](../Namespaces/namespace_microsoft_1_1_xna_1_1_framework_1_1_graphics/)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ExampleMod2::ExampleModPlugin2](../Classes/class_example_mod2_1_1_example_mod_plugin2/)**  |
| class | **[ExampleMod2::TestComputerExecutor](../Classes/class_example_mod2_1_1_test_computer_executor/)**  |
| class | **[ExampleMod2::TestExe](../Classes/class_example_mod2_1_1_test_exe/)**  |
| class | **[ExampleMod2::TestDaemon](../Classes/class_example_mod2_1_1_test_daemon/)**  |
| class | **[ExampleMod2::TestGoal](../Classes/class_example_mod2_1_1_test_goal/)**  |
| class | **[ExampleMod2::TestCondition](../Classes/class_example_mod2_1_1_test_condition/)**  |
| class | **[ExampleMod2::TestAction](../Classes/class_example_mod2_1_1_test_action/)**  |
| class | **[ExampleMod2::TestAdministrator](../Classes/class_example_mod2_1_1_test_administrator/)**  |
| class | **[ExampleMod2::PatchClass2](../Classes/class_example_mod2_1_1_patch_class2/)**  |




## Source code

```csharp
using BepInEx;
using HarmonyLib;
using Hacknet;
using Microsoft.Xna.Framework;
using Microsoft.Xna.Framework.Graphics;
using Pathfinder.Action;
using Pathfinder.Administrator;
using Pathfinder.Util;
using Pathfinder.Daemon;
using Pathfinder.GUI;
using Pathfinder.Mission;
using Pathfinder.Util.XML;

namespace ExampleMod2;

[BepInPlugin("com.Windows10CE.Example", "Example", "1.0.0")]
public class ExampleModPlugin2 : BepInEx.Hacknet.HacknetPlugin
{
    public override bool Load()
    {
        base.HarmonyInstance.PatchAll(typeof(PatchClass2));

        Pathfinder.Executable.ExecutableManager.RegisterExecutable<TestExe>("#PF_TEST_EXE#");
        Pathfinder.Port.PortManager.RegisterPort("ex", "example port", 1515);
        Pathfinder.Daemon.DaemonManager.RegisterDaemon<TestDaemon>();
        Pathfinder.Command.CommandManager.RegisterCommand("pathfinder", TestCommand);
        Pathfinder.Mission.GoalManager.RegisterGoal<TestGoal>("resetIP");
        Pathfinder.Action.ConditionManager.RegisterCondition<TestCondition>("OnDelete");
        Pathfinder.Action.ActionManager.RegisterAction<TestAction>("RandomFlag");
        Pathfinder.Replacements.ContentLoader.RegisterExecutor<TestComputerExecutor>("Computer", ParseOption.FireOnEnd);
        Pathfinder.Administrator.AdministratorManager.RegisterAdministrator<TestAdministrator>();

        return true;
    }

    public override bool Unload()
    {
        PatchClass2.bruhButton.Dispose();
        PatchClass2.bruhButton = null;
            
        return base.Unload();
    }

    public static void TestCommand(OS os, string[] args)
    {
        os.write("pathfinder is here!");
        os.write("Arguments passed in: " + string.Join(" ", args));
    }
}

public class TestComputerExecutor : Pathfinder.Replacements.ContentLoader.ComputerExecutor
{
    public override void Execute(EventExecutor exec, ElementInfo info)
    {
        Comp.name = "hello from custom executor!";
    }
}

public class TestExe : Pathfinder.Executable.BaseExecutable
{
    public TestExe(Rectangle location, OS operatingSystem, string[] args) : base(location, operatingSystem, args) { this.ramCost = 761; }

    public override void LoadContent()
    {
        base.LoadContent();
        Programs.getComputer(os, targetIP).hostileActionTaken();
        os.write(string.Join(" ", Args));
    }

    public override void Draw(float t)
    {
        base.Draw(t);
        drawTarget();
        drawOutline();
        Hacknet.Gui.TextItem.doLabel(new Vector2(Bounds.Center.X, Bounds.Center.Y), "blue text", new Color(255, 0, 0));
    }

    private float total = 0f;
    public override void Update(float t)
    {
        base.Update(t);
            
        total += t;
        if (total > 2.5f)
        {
            isExiting = true;
            Programs.getComputer(os, targetIP).openPort(50, os.thisComputer.ip);
        }
    }
}

public class TestDaemon : BaseDaemon
{
    public TestDaemon(Computer computer, string serviceName, OS opSystem) : base(computer, serviceName, opSystem) { }

    public override string Identifier => "Test Daemon! :)";

    [XMLStorage]
    public string DisplayString;

    public override void draw(Rectangle bounds, SpriteBatch sb)
    {
        base.draw(bounds, sb);

        var center = os.display.bounds.Center;
        Hacknet.Gui.TextItem.doLabel(new Vector2(center.X, center.Y), DisplayString, Color.Aquamarine);
    }
}

public class TestGoal : PathfinderGoal
{
    [XMLStorage]
    public string NodeID;

    public string OriginalIP;

    public override void LoadFromXML(ElementInfo info)
    {
        base.LoadFromXML(info);
            
        OriginalIP = Programs.getComputer(OS.currentInstance, NodeID).ip;
    }

    public override bool isComplete(List<string> additionalDetails = null)
    {
        return Programs.getComputer(OS.currentInstance, NodeID).ip != OriginalIP;
    }
}

public class TestCondition : PathfinderCondition
{
    [XMLStorage]
    public string Computer;
    [XMLStorage] 
    public string Directory;
    [XMLStorage]
    public string File;

    private Computer Comp;
        
    public override bool Check(object os_obj)
    {
        var os = (OS)os_obj;

        if (Computer == null || Directory == null)
            throw new FormatException("TestCondition: Need a node ID and directory!");
            
        if (Comp == null)
            Comp = Programs.getComputer(os, Computer);

        var folder = Comp.getFolderFromPath(Directory);

        if (File == null)
            return folder.files.Count == 0;

        return folder.files.All(x => x.name != File);
    }
}

public class TestAction : DelayablePathfinderAction
{
    [XMLStorage]
    public string Min;
    [XMLStorage]
    public string Max;
    [XMLStorage(IsContent = true)]
    public string stringToWrite;

    private int min = 0;
    private int max = 9;
        
    private static readonly Random Rand = new Random();
        
    public override void Trigger(OS os)
    {
        os.Flags.Flags.RemoveAll(x => x.StartsWith("randomInt"));
        os.Flags.Flags.Add("randomInt" + Rand.Next(min, max));
            
        if (stringToWrite != null)
            os.write(stringToWrite);
    }

    public override void LoadFromXml(ElementInfo info)
    {
        base.LoadFromXml(info);

        if (Min != null)
            min = int.Parse(Min);
        if (Max != null)
            max = int.Parse(Max);
    }
}

public class TestAdministrator : BaseAdministrator
{
    public TestAdministrator(Computer computer, OS opSystem) : base(computer, opSystem)
    {
        Console.WriteLine("Test administrator created.");
    }
    public override void disconnectionDetected(Computer c, OS os)
    {
        os.write("TestAdmin detected disconnection");
    }

    public override void traceEjectionDetected(Computer c, OS os)
    {
        os.write("TestAdmin detected trace ejection");
    }
}

[HarmonyPatch]
public static class PatchClass2
{
    internal static PFButton bruhButton = new PFButton(5, 5, 30, 600, "bruh", Color.BlueViolet);
        
    [HarmonyPostfix]
    [HarmonyPatch(typeof(MainMenu), nameof(MainMenu.Draw))]
    public static void MainMenuTextPatch()
    {
        if (bruhButton == null)
            return;
            
        GuiData.startDraw();
        bruhButton.Do();
        GuiData.endDraw();
    }
}
```


-------------------------------

Updated on 2026-09-26 at 01:50:00 +0000
