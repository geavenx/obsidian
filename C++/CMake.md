
# TLDR step-by-step
1. Create a CMakeLists.txt file on root of the project
2. add **cmake_minimum_required**(VERSION {version of cmake}), **project**({name of the project}), **set**({c++ standard}) and **add_executable**({name of the executable}, {path to main.cpp}) to the file.
	1. example here:
		```
		cmake_minimum_required(VERSION 3.25)
		
		project(yelang)

		set(CMAKE_CXX_STANDARD 20)
		
		add_executable(yelang src/main.cpp)
		```
# Quick start
## Basic building
For simple projects, a single `CMakeLists.txt` with only 3 commands is enough!
Any projects `CMakeLists.txt` file should start with the `cmake_minimum_required()` command, this ensures that the following CMake functions are run with a compatible version of CMake.

To name a project, use the `project(name)` after the `cmake_minimum_required()` command. And finally use the `add_executable(source_code_files)` command to tell CMake to create an executable using the specified code files.
## Specify C++ Standard
CMake has a bunch of special variables that are created behind the scenes or have importance when set by project code. Most of them starts with "CMAKE_". Try to avoid this naming convention in your project variables. Two of these special variables are `CMAKE_CXX_STANDARD` and `CMAKE_CXX_STANDARD_REQUIRED`. These are used to specify the C++ standard needed to build the project.
* **`CMAKE_CXX_STANDARD`** -> value -> specify the C++ version.
* **`CMAKE_CXX_STANDARD_REQUIRED`** -> Bool -> Describe whether the value of CXX_STANDARD is a requirement.
## Debugging
```cmake
# Enable all warnings
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")

# Add optimization flags (optional)
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3")
```