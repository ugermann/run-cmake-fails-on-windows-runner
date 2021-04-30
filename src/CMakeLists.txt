add_executable(helloWorld2 main.cpp)
set_target_properties(helloWorld2 PROPERTIES
  RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}
  OUTPUT_NAME "${CMAKE_BINARY_DIR}/helloWorld2")
