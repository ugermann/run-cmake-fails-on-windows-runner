add_executable(helloWorld2 main.cpp)
# the following breaks things with cmake -G Ninja on windows:
if (SHOW_ERROR2)
  message("Setting custom name for binary.")
  set_target_properties(helloWorld2 PROPERTIES OUTPUT_NAME "${CMAKE_BINARY_DIR}/helloWorld2")
else(SHOW_ERROR2)
  message("Setting custom output directory for binary.")
  set_target_properties(helloWorld2 PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
endif(SHOW_ERROR2)

