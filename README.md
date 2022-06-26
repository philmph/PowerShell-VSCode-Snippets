# PowerShell VSCode Snippets

**Note**: This project is not actively maintained by me due to moving away from PowerShell development.

Feel free to use this code if you consider it useful.

## About

This repository is used by myself to maintain my VS Code snippets for powershell.

## Installation

Requires git in `$env:PATH` and user context installation of vs code. Execute commands in PowerShell:

```powershell
$TempPath = New-Item -Path $env:TEMP -Name 'PWSH_VSCodeSnippets' -ItemType Directory -Force
$JSONPath = Join-Path -Path "C:\Users\$($env:USERNAME)\AppData\Roaming\Code\User\snippets" -ChildPath 'powershell.json'

git clone https://github.com/philmph/PWSH_VSCodeSnippets.git $TempPath

if (Test-Path -Path $JSONPath -PathType Leaf) {
    Rename-Item -Path $JSONPath -NewName ("powershell.json.old-{0}" -f (Get-Date -Format "yyyyMMdd-HHmmss"))
}

Copy-Item -Path "$TempPath\powershell_template.json" -Destination $JSONPath -Force

Remove-Item -Path $TempPath -Force -Recurse
```
