cmake_minimum_required (VERSION 3.5.1)
project (helloWorld CXX)

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
message("CMAKE BINARY DIR IS ${CMAKE_BINARY_DIR}")
add_subdirectory(src)
