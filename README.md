[Beginning C++ Programming - From Beginner to Beyond](https://www.udemy.com/course/beginning-c-plus-plus-programming/) -- 10/27/2023

***

# Sections


## PART-1

* [Section 01: Introduction]()
* [Section 02: Installation and Setup](https://github.com/muarshad01/CPP_Programming/blob/main/section_02_installation_and_setup.md) -- 10/27/2023
* [Section 03: Curriculum Overview]()
* [Section 04: Getting Started](https://github.com/muarshad01/CPP_Programming/blob/main/section_04_getting_started.md) -- 10/28/2023
* [Section 05: Structure of C++ Program](https://github.com/muarshad01/CPP_Programming/blob/main/section_05_structure_of_a_c%2B%2B_program.md) -- 10/30/2023
* [Section 06: Variables and Constants](https://github.com/muarshad01/CPP_Programming/blob/main/section_06_variables_and_constants.md) -- 10/30/2023
* [Section 07: Arrays and Vectors](https://github.com/muarshad01/CPP_Programming/blob/main/section_07_arrays_and_vectors.md) -- Nov. 13, 2023
* [Section 08: Statements and Operators](https://github.com/muarshad01/CPP_Programming/blob/main/section_08_statements_and_operators.md) -- Nov. 14, 2023
* [Section 09: Controlling Program Flow]() -- skip
* [Section 10: Characters and Strings](https://github.com/muarshad01/CPP_Programming/blob/main/section_10_characters_and_strings.md) -- Nov. 14, 2023
* [Section 11: Functions](https://github.com/muarshad01/CPP_Programming/blob/main/section_11_functions.md) -- 11/01/2023
* [Section 12: Pointers and References](https://github.com/muarshad01/CPP_Programming/blob/main/section_12_pointers_and_references.md) -- 11/02/2023

## PART-2 (OOP)

* [Section 13: OOP - Classes and Objects](https://github.com/muarshad01/CPP_Programming/blob/main/section_13_oop_classes_and_objects.md) -- 11/06/2023
* [Section 14: Operator Overloading](https://github.com/muarshad01/CPP_Programming/blob/main/section_14_operator_overloading.md) -- Nov. 13, 2023
* [Section 15: Inheritance](https://github.com/muarshad01/CPP_Programming/blob/main/section_15_inheritance.md) -- 11/07/2023
* [Section 16: Polymorphism](https://github.com/muarshad01/CPP_Programming/blob/main/section_16_polymorphism.md) -- 11/07/2023
* [Section 17: Smart Pointers](https://github.com/muarshad01/CPP_Programming/blob/main/section_17_smart_pointers.md) -- Nov. 13, 2023

## PART-3

* [Section 18: Exception Handling](https://github.com/muarshad01/CPP_Programming/blob/main/section_18_exception_handling.md) -- Nov. 12, 2023
* [Section 19: I/O and Streams](https://github.com/muarshad01/CPP_Programming/blob/main/section_19_io_and_streams.md) -- Nov. 12, 2023
* [Section 20: The Standard Template Library (STL)](https://github.com/muarshad01/CPP_Programming/blob/main/section_20_STL.md) -- Nov. 11, 2023
* [Section 21: Lambda Expressions](https://github.com/muarshad01/CPP_Programming/blob/main/section_21_lambda_expressions.md) -- Nov. 15, 2023
* [Section 22: Using VSCode](https://github.com/muarshad01/CPP_Programming/blob/main/section_22_Using_VSCode.md) -- 10/28/2023
* [Section 23: Enumerations](https://github.com/muarshad01/CPP_Programming/blob/main/section_23_enumerations.md) -- Nov. 15, 2023

***

## Install MinGW for Windows

* Goto [https://winlibs.com](https://winlibs.com) -> Downloads
    - Press `Windows-Key` -> `Type Control Panel` -> `System and Security` -> `System` -> View amount of RAM and processor Speed
        - System type: 64-bit operating system, x64-based processor
    - Download `Zip Archive`
    - Extract .zip file to `C:\`
    - Copy `C:\mingw64\bin` to PATH
```
$ g++ --version
```

```
$ g++
```

***


### Check if compiler is installed on MaxOS
```        
$ clang --version        # MacOS
$ g++ --version          # Windows
```

```
Apple clang version 14.0.3 (clang-1403.0.22.14.1)
Target: arm64-apple-darwin22.6.0
Thread model: posix
InstalledDir: /Library/Developer/CommandLineTools/usr/bin
```

```        
$ gcc -> clang: error: no input files
$ g++ -> clang: error: no input files
```

* Otherwise, install using: `$ xcode-select --install` 

***

## `VSCode` Extensions for `C++`

* [Run C++ and C in Visual Studio Code](https://www.youtube.com/watch?v=3-9sObAg6R0)
* [How to Run C++ in VSCode on MacOS](https://www.youtube.com/watch?v=tdAD0WZjXrM)
    - Open `VSCode`, we need to install TWO extensions:
      - Extensions -> search c/c++ -> Install `C/C++ IntelliSense` 
      - Extensions -> search code codelldb -> Install `CodeLLDB (Code Runner)`

***

## 283. Using the `Course Source Code` with `VSCode` on `MacOS`

### STEP-1 (Setup `IntelliSense`)

* `main.cpp` -> View -> `Command Palette` OR `cmd + shift + p` -> search C++ -> `C/C++: Edit Configuration (UI)`
    - Compiler path: `/usr/local/g++` OR `C:/mingw64/bin/g++.exe`
    - C++ standard: `c++17`

We can see that `.vscode` folder is created with `{} c_cpp_properties.json` file

### STEP-2 (Setup `Default Build Task`)

* Terminal -> `Configure Default Build Task` (compiler: `/usr/bin/g++`)

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

* `main.cpp` -> Launch `Run and Debug` -> Click on a particular code-line # 
-> Run `g++ - Build and debug active file` -> step-over -> STOP

***

## Other

```
$ g++ --std=c++11 hello.cpp
```
