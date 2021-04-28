cmake_minimum_required (VERSION 3.5.1)
project (helloWorld CXX)

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
include_directories(src)
add_subdirectory(src)
