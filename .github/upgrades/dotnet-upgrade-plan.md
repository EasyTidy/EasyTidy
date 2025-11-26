# .NET 10.0 Upgrade Plan

## Execution Steps

Execute steps below sequentially one by one in the order they are listed.

1. Validate that a .NET 10.0 SDK required for this upgrade is installed on the machine and if not, help to get it installed.
2. Ensure that the SDK version specified in global.json files is compatible with the .NET 10.0 upgrade.
3. Upgrade EasyTidy\EasyTidy.csproj
4. Upgrade EasyTidy.Log\EasyTidy.Log.csproj
5. Upgrade EasyTidy.Util\EasyTidy.Util.csproj
6. Upgrade EasyTidy.Service\EasyTidy.Service.csproj
7. Upgrade EasyTidy.Model\EasyTidy.Model.csproj
8. Upgrade EasyTidy.UpdateLauncher\EasyTidy.UpdateLauncher.csproj
9. Upgrade EasyTidy.Contracts\EasyTidy.Contracts.csproj

## Settings

This section contains settings and data used by execution steps.

### Aggregate NuGet packages modifications across all projects

NuGet packages used across all selected projects or their dependencies that need version update in projects that reference them.

| Package Name                    | Current Version | New Version | Description                                            |
|:--------------------------------|:---------------:|:-----------:|:-------------------------------------------------------|
| H.NotifyIcon.WinUI              | 2.3.2           |             | No supported version found for .NET 10.0               |
| System.Net.Http                 | 4.3.4           |             | Remove - functionality included in .NET 10.0 framework |
| System.Text.RegularExpressions  | 4.3.1           |             | Remove - functionality included in .NET 10.0 framework |
| WinUIEx                         | 2.5.1           |             | No supported version found for .NET 10.0               |

### Project upgrade details

This section contains details about each project upgrade and modifications that need to be done in the project.

#### EasyTidy\EasyTidy.csproj modifications

Project properties changes:
  - Target framework should be changed from `net8.0-windows10.0.22621.0` to `net10.0-windows10.0.22621.0`

NuGet packages changes:
  - H.NotifyIcon.WinUI (version 2.3.2) - no supported version found for .NET 10.0, needs investigation
  - WinUIEx (version 2.5.1) - no supported version found for .NET 10.0, needs investigation
  - System.Net.Http (version 4.3.4) should be removed (*functionality included in .NET 10.0 framework*)
  - System.Text.RegularExpressions (version 4.3.1) should be removed (*functionality included in .NET 10.0 framework*)

#### EasyTidy.Log\EasyTidy.Log.csproj modifications

Project properties changes:
  - Target framework should be changed from `net8.0` to `net10.0`

#### EasyTidy.Util\EasyTidy.Util.csproj modifications

Project properties changes:
  - Target framework should be changed from `net8.0` to `net10.0`

#### EasyTidy.Service\EasyTidy.Service.csproj modifications

Project properties changes:
  - Target framework should be changed from `net8.0` to `net10.0`

#### EasyTidy.Model\EasyTidy.Model.csproj modifications

Project properties changes:
  - Target framework should be changed from `net8.0` to `net10.0`

#### EasyTidy.UpdateLauncher\EasyTidy.UpdateLauncher.csproj modifications

Project properties changes:
  - Target framework should be changed from `net8.0-windows10.0.22621.0` to `net10.0-windows10.0.22621.0`

#### EasyTidy.Contracts\EasyTidy.Contracts.csproj modifications

Project properties changes:
  - Target framework should be changed from `net8.0` to `net10.0`
