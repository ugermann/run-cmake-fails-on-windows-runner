add_executable(helloWorld main.cpp)
# the following breaks things with cmake -G Ninja on windows:
if (WITH_SET_TARGET_PROPERTIES_OUTPUT_NAME)
  message("Setting custom name for binary.")
  set_target_properties(helloWorld PROPERTIES OUTPUT_NAME "${CMAKE_BINARY_DIR}/helloWorld")
else(WITH_SET_TARGET_PROPERTIES_OUTPUT_NAME)
  message("Setting custom output directory for binary.")
  set_target_properties(helloWorld PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
endif(WITH_SET_TARGET_PROPERTIES_OUTPUT_NAME)

