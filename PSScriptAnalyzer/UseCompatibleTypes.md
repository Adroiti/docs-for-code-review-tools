Pattern: Use of incompatible type in targeted _PowerShell_ platform

Issue: -

## Description

This rule identifies types that are not available (loaded by default) in targeted PowerShell platforms.

A PowerShell platform is identified by a name in the following format:

```
<os-name>_<os-arch>_<os-version>_<ps-version>_<ps-arch>_<dotnet-version>_<dotnet-edition>
```

Where:

- `<os-name>`: The name of the operating system PowerShell is running on.
    On Windows, this includes the SKU number.
    On Linux, this is the name of the distribution.
- `<os-arch>`: The machine architecture the operating system is running on (this is usually `x64`).
- `<os-version>`: The self-reported version of the operating system (on Linux, this is the distribution version).
- `<ps-version>`: The PowerShell version (from `$PSVersionTable.PSVersion`).
- `<ps-arch>`: The machine architecture of the PowerShell process.
- `<dotnet-version>`: The reported version of the .NET runtime PowerShell is running on (from `System.Environment.Version`).
- `<dotnet-edition>`: The .NET runtime flavor PowerShell is running on (currently `framework` or `core`).

For example:

- `win-4_x64_10.0.18312.0_5.1.18312.1000_x64_4.0.30319.42000_framework` is PowerShell 5.1 running on Windows 10 Enterprise (build 18312) for x64.
- `win-4_x64_10.0.18312.0_6.1.2_x64_4.0.30319.42000_core` is PowerShell 6.1.2 running on the same operating system.
- `ubuntu_x64_18.04_6.2.0_x64_4.0.30319.42000_core` is PowerShell 6.2.0 running on Ubuntu 18.04.

Some platforms come bundled with PSScriptAnalyzer as JSON files, named in this way for targeting in your configuration.

The compatibility analysis compares a type used to both a target profile
and a "union" profile (containing all types available in *any* profile in the profile dir).
If a type is not present in the union profile, it is assumed to be locally created and ignored.
Otherwise, if a type is present in the union profile but not present in a target,
it is deemed to be incompatible with that target.

## Configuration

An example configuration might look like:

```PowerShell
@{
    Rules = @{
        PSUseCompatibleTypes = @{
            Enable = $true
            TargetProfiles = @(
                'ubuntu_x64_18.04_6.1.3_x64_4.0.30319.42000_core'
                'win-48_x64_10.0.17763.0_5.1.17763.316_x64_4.0.30319.42000_framework'
                'MyProfile'
                'another_custom_profile_in_the_profiles_directory.json'
                'D:\My Profiles\profile1.json'
            )
            # You can specify types to not check like this, which will also ignore methods and members on it:
            IgnoreTypes = @(
                'System.IO.Compression.ZipFile'
            )
        }
    }
}
```

Alternatively, you could provide a settings object as follows:

```PowerShell
PS> $settings = @{
      Rules = @{
        PSUseCompatibleTypes = @{
          Enable = $true
          TargetProfiles = @("win-48_x64_10.0.17763.0_5.1.17763.316_x64_4.0.30319.42000_framework")
        }
      }
}
PS> Invoke-ScriptAnalyzer -Settings $settings -ScriptDefinition '[System.Management.Automation.SemanticVersion]"1.18.0-rc1"'

RuleName                            Severity     ScriptName Line  Message
--------                            --------     ---------- ----  -------
PSUseCompatibleTypes                Warning                 1     The type 'System.Management.Automation.SemanticVersion' is
                                                                  not available by default in PowerShell version
                                                                  '5.1.17763.316' on platform 'Microsoft Windows 10 Pro'
```

## Further Reading

* [PSScriptAnalyzer - UseCompatibleTypes](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/UseCompatibleTypes.md)