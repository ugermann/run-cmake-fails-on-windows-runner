cmake_minimum_required (VERSION 3.5.1)
project (helloWorld CXX)

set(CMAKE_BUILD_TYPE "Release")

# cmake -G Ninja fails on Windows if the target property OUTPUT_NAME 
# is set explicit in an included subdirectory.
option(WITH_SET_TARGET_PROPERTIES_OUTPUT_NAME 
  "Set target output name in added subdirectory" off)

# see if setting output name explicitly works from the root directory
add_executable(helloWorld0 src/hello_world.cpp)
set_target_properties(helloWorld0 PROPERTIES OUTPUT_NAME ${CMAKE_BINARY_PATH}/helloWorld0.exe)

# now try it from a subdirectory
add_subdirectory(src)
