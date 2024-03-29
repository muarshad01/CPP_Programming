## 275. Section Overview

***

## 280. Installing VSCode on Mac OSX

* Extensions -> search codelldb -> Install `CodeLLDB`

***

## 281. Building and Running C++ Programs with VSCode on Mac OSX

* Extensions -> search codelldb -> Install `CodeLLDB`

* View -> `Command Palette` -- OR --> `shift + command + p` -> search C++ -> `C/C++ Edit Configuration (UI)`
    - Compiler path -> select `/usr/bin/g++`
    - C++ standard -> select `c++17`


* select `main.cpp` -> Terminal -> `Configure Default Build Task` -> select `compiler: /usr/bin/g++`
    - update `tasks.json`:
```json
"args": [
    "-fdiagnostics-color=always",
    "-g",
->  "-Wall",                         # Tell the compiler to generate all warnings.
->  "--std=c++17",
->	"${fileDirname}/*.cpp",
    "-o",
    "${fileDirname}/${fileBasenameNoExtension}"
],
```
    - save with `command + s`


* select `main.cpp` -> Terminal -> `Run Build Task`
* select `main` -> right-click -> `Open in Integrated Terminal`

***

## 282. Debugging C++ Programs with VSCode on Mac

* select `main.cpp` -> Run -> Add Configuation -> `C++ (GDB/LLDB)`
    - edit `launch.json`
```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "g++ - Build and debug active file",
            "type": "lldb",
            "request": "launch",
            "program": "${fileDirname}/${fileBasenameNoExtension}",
            "args": [],
            "cwd": "${fileDirname}",
            "preLaunchTask": "C/C++: g++ build active file"
        }
    ]
}
```

* `main.cpp` -> `Run and Debug` -> Breakpoint: click a particular codeline -> `g++ - Build and debug active file`
    - `VARIABLES`
    - WATCH
    - CALL STACK
    - `BREAKPOINTS`
    - MODULES
    - EXCLUDED CALLERS

***

## 283. Using the Course Source Code with VSCode on Mac

### STEP-1 (Setup `IntelliSense`)
* `main.cpp` -> View -> `Command Palette` OR `cmd + shift + p` -> search C++ -> `C/C++: Edit Configuration (UI)`
    - Compiler path: `/usr/local/g++`
    - C++ standard: `c++17`

We can see that `.vscode` folder is created with `{} c_cpp_properties.json` file

### STEP-2 (Setup `Default Build Task`)
* Terminal -> Configure `Default Build Task` (compiler: `/usr/bin/g++`)

We can see that `{} tasks.json` file is created. Edit and update it as follows:

```json
"args": [
    "-fdiagnostics-color=always",
    "-g",
->    "-Wall",
->    "-std=c++17",
->    "${fileDirname}/*.cpp",
    "-o",
    "${fileDirname}/${fileBasenameNoExtension}"
],
```

### Step-3 (RUN the code)
* `main.cpp` -> Terminal -> `Run Build Task` (`shift + command + b`)
* `main` -> right-click `Open in Integrated Terminal`

### Step-4 (DEBUG)

* `main.cpp` -> Run -> `Add Configuation` -> `C++ (GDB/LLDB)`

This will create `{} launch.json` file. Edit and update it as follows:

```
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "g++ - Build and debug active file",
            "type": "lldb",
            "request": "launch",
            "program": "${fileDirname}/${fileBasenameNoExtension}",
            "args": [],
            "cwd": "${fileDirname}",
            "preLaunchTask": "C/C++: g++ build active file"
        }
    ]
}
```

***

##
