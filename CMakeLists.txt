cmake_minimum_required (VERSION 3.5.1)
project (helloWorld CXX)

set(CMAKE_BUILD_TYPE "Release")

# cmake -G Ninja fails on Windows if the target property OUTPUT_NAME 
# is set explicit in an included subdirectory.
option(WITH_SET_TARGET_PROPERTIES_OUTPUT_NAME 
  "Set target output name in added subdirectory" off)
add_subdirectory(src)
