# PWSH_VSCodeSnippets

This repository is used by myself to maintain my VS Code snippets for powershell.

## Installation

Requires git in ```$env:PATH``` and user context installation of vs code. Execute commands in PowerShell:

```powershell
$TempPath = Join-Path -Path $env:TEMP -ChildPath 'PWSH_VSCodeSnippets\powershell_template.json'

git clone git@github.com:philmphdev/PWSH_VSCodeSnippets.git $TempPath

$JSONPath = "C:\Users\$($env:USERNAME)\AppData\Roaming\Code\User\snippets\powershell.json"

if (Test-Path -Path $JSONPath -PathType Leaf) {
    Copy-Item -Path $JSONPath -Destination ($JSONPath -replace "\.json$", ".json.old")
}

Copy-Item -Path $TempPath -Destination $JSONPath -Force

Remove-Item -Path $TempPath -Force -Recurse
```
