# PWSH_VSCodeSnippets

This repository is used by myself to maintain my VS Code snippets for powershell.

## Installation

Requires git in ```$env:PATH``` and user context installation of vs code. Execute commands in PowerShell:

```powershell
$TempPath = Join-Path -Path $env:TEMP -ChildPath 'PWSH_VSCodeSnippets'

git clone git@github.com:philmph/PWSH_VSCodeSnippets.git $TempPath

Copy-Item -Path "$($TempPath)\powershell.json" -Destination "C:\Users\$($env:USERNAME)\AppData\Roaming\Code\User\snippets\powershell.json" -Force

Remove-Item -Path $TempPath -Force -Recurse
```
