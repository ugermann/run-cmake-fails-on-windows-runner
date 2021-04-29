# Minimal setup to demonstrate how cmake with -G Ninja fails on windows
`cmake -GNinja` fails on Windows if the CMakeLists.txt file contains 
```
set_target_properties(<target> PROPERTIES OUTPUT_NAME <name>)
```

I've noticed two different versions of the error:
- Error1: if the above command is in the root CMakeLists.txt, Ninja complains about two different instruction to produce the same executable:
  ```
  ninja: error: build.ninja:166: multiple rules generate D:/a/run-cmake-fails-on-windows-runner/run-cmake-fails-on-windows-runner/build/helloWorld1.exe [-w dupbuild=err]
  ```
- Error2: occurs if the command is in a subdirectory that has been added with add_subdirectory(). In this case, path prefix and added subdirectory are swapped, resulting in something like
  ```
   ninja: error: FindFirstFileExA(src/d:/a/run-cmake-fails-on-windows-runner/run-cmake-fails-on-windows-runner/build): The filename, directory name, or volume label syntax is incorrect.
  ```

Run with `-DSHOW_ERROR1=on` to trigger error 1, `-DSHOW_ERROR2=on` to trigger error 2.

This problem has been reported to the cmake team here: https://gitlab.kitware.com/cmake/cmake/-/issues/22133
