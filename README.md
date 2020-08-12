# PWSH_VSCodeSnippets

This repository is used by myself to maintain my VS Code snippets for powershell.

## Installation

Requires git in ```$env:PATH``` and user context installation of vs code. Execute commands in PowerShell:

```powershell
$TempPath = Join-Path -Path $env:TEMP -ChildPath "PWSH_VSCodeSnippets"
$JSONPath = "C:\Users\$($env:USERNAME)\AppData\Roaming\Code\User\snippets"
$JSONPathFile = Join-Path -Path $JSONPath -ChildPath "powershell.json"

git clone git@github.com:philmphdev/PWSH_VSCodeSnippets.git $TempPath

if (Test-Path -Path $JSONPathFile -PathType Leaf) {
    Rename-Item -Path $JSONPathFile -NewName "powershell.json.old"
}

Copy-Item -Path "$TempPath\powershell_template.json" -Destination $JSONPathFile -Force -Confirm

Remove-Item -Path $TempPath -Force -Recurse
```
