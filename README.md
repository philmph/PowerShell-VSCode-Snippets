# PWSH_VSCodeSnippets

This repository is used by myself to maintain my VS Code snippets for powershell.

## Installation

Requires git in ```$env:PATH```. Execute commands in PowerShell:

```powershell
git clone git@github.com:philmph/PWSH_VSCodeSnippets.git C:\Temp\PWSH_VSCodeSnippets
Copy-Item -Path C:\Temp\PWSH_VSCodeSnippets\powershell.json -Destination "C:\Users\$($env:USERNAME)\AppData\Roaming\Code\User\snippets\powershell.json" -Force
Remove-Item -Path C:\Temp\PWSH_VSCodeSnippets -Force -Recurse
```
