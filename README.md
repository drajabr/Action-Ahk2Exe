# Action-Ahk2Exe
GitHub Action to compile AutoHotKey V2 scripts using Ahk2Exe

# Inputs
|  name    | Type     |Required|Description |
|:-----|:-----|:-----|:-----|
|in|String|True|The path and name of the script to compile|
|out|String |False|The path\name of the output .exe to be created|
|base|Number |False|compile bit number 32\|64, default 64|
|icon|String |False|The path and name of the icon file|

# Example usage
```yml
name: Compile AHKV2 Script

on:
  push:
    branches:
      - main

jobs:
  compile:
    runs-on: windows-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v3

    - name: Compile AutoHotKey Script
      uses: drajabr/Action-Ahk2Exe@main
      with:
        in: src/myScript.ahk              # Path to your .ahk file
        out: dist/myScript.exe            # Output .exe path (optional)
        base: 64                          # Architecture (optional: 32 or 64)
        icon: assets/myIcon.ico           # Icon path (optional)

    - name: Upload Compiled Executable
      uses: actions/upload-artifact@v3
      with:
        name: MyCompiledScript
        path: dist/myScript.exe
```


# Credits:
[@nekocodeX](https://github.com/nekocodeX) For his reference work for [v1 ](https://github.com/nekocodeX/GitHub-Action-Ahk2Exe/tree/main).

[@CCCC-L](https://github.com/CCCC-L) For the v2 port [AHK v2 Actions template](https://github.com/CCCC-L/Action-Ahk2Exe).

[@alfvar](https://github.com/alfvar) For adding icon support in his repo [AHK v2 Actions template](https://github.com/alfvar/action-ahk2exe)
