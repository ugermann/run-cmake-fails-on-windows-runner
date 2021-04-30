cmake_minimum_required (VERSION 3.5.1)
project (helloWorld CXX)

set(CMAKE_BUILD_TYPE "Release")

# cmake -G Ninja fails on Windows if the target property OUTPUT_NAME 
# is set explicit in an included subdirectory.
option(SHOW_ERROR1 "Show error setting target property OUTPUT_NAME in root" off)
option(SHOW_ERROR2 "Show error setting target property OUTPUT_NAME in subdirectory" off)

# see if setting output name explicitly works from the root directory
add_executable(helloWorld1 src/main.cpp)
set_target_properties(helloWorld1 PROPERTIES
  RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}
  OUTPUT_NAME "${CMAKE_BINARY_DIR}/helloWorld1")

# now try it from a subdirectory
add_subdirectory(src)
