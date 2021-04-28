add_executable(mainProgram main.cpp)
set_target_properties(mainProgram PROPERTIES
  OUTPUT_NAME "${CMAKE_BINARY_DIR}/helloWorld.exe")
