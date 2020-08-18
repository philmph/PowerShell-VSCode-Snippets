# PWSH_VSCodeSnippets

## About

This repository is used by myself to maintain my VS Code snippets for powershell.

## Installation

Requires git in ```$env:PATH``` and user context installation of vs code. Execute commands in PowerShell:

```powershell
$TempPath = Join-Path -Path $env:TEMP -ChildPath "PWSH_VSCodeSnippets"
$JSONPath = Join-Path -Path "C:\Users\$($env:USERNAME)\AppData\Roaming\Code\User\snippets" -ChildPath "powershell.json"

git clone git@github.com:philmph/PWSH_VSCodeSnippets.git $TempPath

if (Test-Path -Path $JSONPath -PathType Leaf) {
    Rename-Item -Path $JSONPath -NewName ("powershell.json.old-{0}" -f (Get-Date -Format "yyyyMMdd-HHmmss"))
}

Copy-Item -Path "$TempPath\powershell_template.json" -Destination $JSONPath -Force -Confirm

Remove-Item -Path $TempPath -Force -Recurse
```
