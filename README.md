# CMake Learning

GitHub: [mmdjiji/cmake-learning](https://github.com/mmdjiji/cmake-learning)

## Introduction
After I learned [how to write makefile](https://github.com/mmdjiji/makefile-learning), I found that this was not enough to enable me to build all projects, such as [KDE](https://kde.org/), [OpenCV](https://opencv.org/) and so on. So I determined to learn [CMake](https://cmake.org/), an awesome building tool, which can be use on all platforms. You can download CMake by [this page](https://cmake.org/download/).

## Hello CMake
Create a file named `CMakeLists.txt` and write as follows:
```cmake
cmake_minimum_required (VERSION 2.8)
project (hello)
add_executable(hello hello.c)
```

Maybe you should finish `hello.c` with main function.

Then, use `cmake .` to generate `Makefile`. After done, use `make` to build all the project. Then you can use `./hello` to run the program.

## Multi Source Build
If you have two or more source files, you can use following:
```cmake
cmake_minimum_required (VERSION 2.8)
project (hello)
add_executable (hello hello1.c hello2.c)
```

But this is trouble when you build a big project, not elegant enough. So use follows instead:
```cmake
cmake_minimum_required (VERSION 2.8)
project (fruits)
aux_source_directory (. DIR_SRCS)
add_executable (fruits ${DIR_SRCS})
```
This used `aux_source_directory (<dir> <variable>)` to add source files automatically.

## Commonly Used Functions
```cmake
cmake_minimum_required (<version>) # Set cmake minimum version (VERSION 2.8).
project (<name>) # Set project name.
add_executable (<file>) # Add executable files.
add_subdirectory (<dir>) # Add sub directory <dir> to project.
aux_source_directory (<dir> <variable>) # Find source files from <dir> to <variable>.
include_directories (<dir>) # Add header files path.
set (EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/build) # Set build path.
```

## License
All documents use [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) license, all codes use [GNU GPLv3](https://choosealicense.com/licenses/gpl-3.0/).