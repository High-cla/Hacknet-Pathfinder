---
title: PathfinderUpdater::Updater

---

# PathfinderUpdater::Updater





## Public Functions

|                | Name           |
| -------------- | -------------- |
| [Updater](../Classes/class_pathfinder_updater_1_1_updater/) | **[Create< PluginT >](../Classes/class_pathfinder_updater_1_1_updater/#function-create<-plugint->)**(string githubApiUrl, string assetFile, string zipPath, bool includePrereleases =false) |
| bool | **[TryCreate](../Classes/class_pathfinder_updater_1_1_updater/#function-trycreate)**(Type pluginType, out [Updater](../Classes/class_pathfinder_updater_1_1_updater/) updater, bool canSupportUpdaterData =false) |
| void | **[ForceResetAllReleaseData](../Classes/class_pathfinder_updater_1_1_updater/#function-forceresetallreleasedata)**() |
| async Task | **[ForceResetAllReleaseDataAsync](../Classes/class_pathfinder_updater_1_1_updater/#function-forceresetallreleasedataasync)**() |
| delegate Task< [Version](../Files/_hacknet_chainloader_8cs/#using-version) > | **[FindVersionAction](../Classes/class_pathfinder_updater_1_1_updater/#function-findversionaction)**() |
| delegate Task< Stream > | **[GetUpdateStreamAction](../Classes/class_pathfinder_updater_1_1_updater/#function-getupdatestreamaction)**([Version](../Files/_hacknet_chainloader_8cs/#using-version) latest) |
| delegate Task< string > | **[HandleStreamDownloadAction](../Classes/class_pathfinder_updater_1_1_updater/#function-handlestreamdownloadaction)**(Stream stream) |
| | **[Updater](../Classes/class_pathfinder_updater_1_1_updater/#function-updater)**(Type pluginType, [FindVersionAction](../Classes/class_pathfinder_updater_1_1_updater/#function-findversionaction) findVersion, [GetUpdateStreamAction](../Classes/class_pathfinder_updater_1_1_updater/#function-getupdatestreamaction) getUpdateStream =null, [HandleStreamDownloadAction](../Classes/class_pathfinder_updater_1_1_updater/#function-handlestreamdownloadaction) handeStreamDownload =null) |
| | **[Updater](../Classes/class_pathfinder_updater_1_1_updater/#function-updater)**(Type pluginType, string githubApiUrl, string assetFileName, string zipEntryPath, bool includePrerelease =false) |
| | **[Updater](../Classes/class_pathfinder_updater_1_1_updater/#function-updater)**(Type pluginType) |
| async Task< bool > | **[CheckForUpdate](../Classes/class_pathfinder_updater_1_1_updater/#function-checkforupdate)**() |
| async Task | **[PerformDownload](../Classes/class_pathfinder_updater_1_1_updater/#function-performdownload)**() |
| void | **[PerformUpdate](../Classes/class_pathfinder_updater_1_1_updater/#function-performupdate)**() |
| bool | **[TryDeleteDownloadedTempFile](../Classes/class_pathfinder_updater_1_1_updater/#function-trydeletedownloadedtempfile)**() |
| bool | **[TryDeleteDllTempFile](../Classes/class_pathfinder_updater_1_1_updater/#function-trydeletedlltempfile)**() |
| HttpResponseMessage | **[ForceResetReleaseData](../Classes/class_pathfinder_updater_1_1_updater/#function-forceresetreleasedata)**() |
| async Task< HttpResponseMessage > | **[ForceResetReleaseDataAsync](../Classes/class_pathfinder_updater_1_1_updater/#function-forceresetreleasedataasync)**() |
| async Task< [Version](../Files/_hacknet_chainloader_8cs/#using-version) > | **[FindVersionDefault](../Classes/class_pathfinder_updater_1_1_updater/#function-findversiondefault)**() |
| async Task< Stream > | **[GetUpdateStreamDefault](../Classes/class_pathfinder_updater_1_1_updater/#function-getupdatestreamdefault)**([Version](../Files/_hacknet_chainloader_8cs/#using-version) latest) |
| async Task< string > | **[HandleStreamDownloadDefault](../Classes/class_pathfinder_updater_1_1_updater/#function-handlestreamdownloaddefault)**(Stream stream) |

## Public Properties

|                | Name           |
| -------------- | -------------- |
| Type | **[PluginType](../Classes/class_pathfinder_updater_1_1_updater/#property-plugintype)**  |
| [FindVersionAction](../Classes/class_pathfinder_updater_1_1_updater/#function-findversionaction) | **[FindVersion](../Classes/class_pathfinder_updater_1_1_updater/#property-findversion)**  |
| [GetUpdateStreamAction](../Classes/class_pathfinder_updater_1_1_updater/#function-getupdatestreamaction) | **[GetUpdateStream](../Classes/class_pathfinder_updater_1_1_updater/#property-getupdatestream)**  |
| [HandleStreamDownloadAction](../Classes/class_pathfinder_updater_1_1_updater/#function-handlestreamdownloadaction) | **[HandleStreamDownload](../Classes/class_pathfinder_updater_1_1_updater/#property-handlestreamdownload)**  |
| string | **[GithubApiUrl](../Classes/class_pathfinder_updater_1_1_updater/#property-githubapiurl)**  |
| string | **[AssetFileName](../Classes/class_pathfinder_updater_1_1_updater/#property-assetfilename)**  |
| string | **[ZipEntryPath](../Classes/class_pathfinder_updater_1_1_updater/#property-zipentrypath)**  |
| bool | **[IncludePrerelease](../Classes/class_pathfinder_updater_1_1_updater/#property-includeprerelease)**  |
| string | **[CurrentVersion](../Classes/class_pathfinder_updater_1_1_updater/#property-currentversion)**  |
| [Version](../Files/_hacknet_chainloader_8cs/#using-version) | **[LatestVersion](../Classes/class_pathfinder_updater_1_1_updater/#property-latestversion)**  |
| string | **[PathToUpdate](../Classes/class_pathfinder_updater_1_1_updater/#property-pathtoupdate)**  |
| string | **[DownloadedTempPath](../Classes/class_pathfinder_updater_1_1_updater/#property-downloadedtemppath)**  |
| ManualLogSource | **[Log](../Classes/class_pathfinder_updater_1_1_updater/#property-log)**  |

## Public Functions Documentation

### function Create< PluginT >

```csharp
static Updater Create< PluginT >(
    string githubApiUrl,
    string assetFile,
    string zipPath,
    bool includePrereleases =false
)
```


### function TryCreate

```csharp
static bool TryCreate(
    Type pluginType,
    out Updater updater,
    bool canSupportUpdaterData =false
)
```


### function ForceResetAllReleaseData

```csharp
static void ForceResetAllReleaseData()
```


### function ForceResetAllReleaseDataAsync

```csharp
static async Task ForceResetAllReleaseDataAsync()
```


### function FindVersionAction

```csharp
delegate Task< Version > FindVersionAction()
```


### function GetUpdateStreamAction

```csharp
delegate Task< Stream > GetUpdateStreamAction(
    Version latest
)
```


### function HandleStreamDownloadAction

```csharp
delegate Task< string > HandleStreamDownloadAction(
    Stream stream
)
```


### function Updater

```csharp
Updater(
    Type pluginType,
    FindVersionAction findVersion,
    GetUpdateStreamAction getUpdateStream =null,
    HandleStreamDownloadAction handeStreamDownload =null
)
```


### function Updater

```csharp
Updater(
    Type pluginType,
    string githubApiUrl,
    string assetFileName,
    string zipEntryPath,
    bool includePrerelease =false
)
```


### function Updater

```csharp
Updater(
    Type pluginType
)
```


### function CheckForUpdate

```csharp
async Task< bool > CheckForUpdate()
```


### function PerformDownload

```csharp
async Task PerformDownload()
```


### function PerformUpdate

```csharp
void PerformUpdate()
```


### function TryDeleteDownloadedTempFile

```csharp
bool TryDeleteDownloadedTempFile()
```


### function TryDeleteDllTempFile

```csharp
bool TryDeleteDllTempFile()
```


### function ForceResetReleaseData

```csharp
HttpResponseMessage ForceResetReleaseData()
```


### function ForceResetReleaseDataAsync

```csharp
async Task< HttpResponseMessage > ForceResetReleaseDataAsync()
```


### function FindVersionDefault

```csharp
async Task< Version > FindVersionDefault()
```


### function GetUpdateStreamDefault

```csharp
async Task< Stream > GetUpdateStreamDefault(
    Version latest
)
```


### function HandleStreamDownloadDefault

```csharp
async Task< string > HandleStreamDownloadDefault(
    Stream stream
)
```


## Public Property Documentation

### property PluginType

```csharp
Type PluginType;
```


### property FindVersion

```csharp
FindVersionAction FindVersion;
```


### property GetUpdateStream

```csharp
GetUpdateStreamAction GetUpdateStream;
```


### property HandleStreamDownload

```csharp
HandleStreamDownloadAction HandleStreamDownload;
```


### property GithubApiUrl

```csharp
string GithubApiUrl;
```


### property AssetFileName

```csharp
string AssetFileName;
```


### property ZipEntryPath

```csharp
string ZipEntryPath;
```


### property IncludePrerelease

```csharp
bool IncludePrerelease;
```


### property CurrentVersion

```csharp
string CurrentVersion;
```


### property LatestVersion

```csharp
Version LatestVersion;
```


### property PathToUpdate

```csharp
string PathToUpdate;
```


### property DownloadedTempPath

```csharp
string DownloadedTempPath;
```


### property Log

```csharp
ManualLogSource Log;
```


-------------------------------

Updated on 2026-09-26 at 01:20:07 +0000