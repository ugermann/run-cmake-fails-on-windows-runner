add_executable(helloWorld main.cpp)
# the following breaks things with cmake -G Ninja on windows:
# set_target_properties(helloWorld PROPERTIES OUTPUT_NAME "${CMAKE_BINARY_DIR}/helloWorld.exe")
set_target_properties(helloWorld PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

