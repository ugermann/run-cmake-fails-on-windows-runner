add_executable(helloWorld2 main.cpp)
set_target_properties(helloWorld2 PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

# the following breaks things with cmake -G Ninja on windows:
if (SHOW_ERROR2)
  message("Setting custom name for binary.")
  set_target_properties(helloWorld2 PROPERTIES OUTPUT_NAME "helloWorld2Custom")
endif(SHOW_ERROR2)
