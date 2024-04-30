# CppMake

Developing C++ applications can be hard, but there are a lot of tools to make that task easier. Compiler warnings, hardening options, sanitizers, and static analyzers are some examples of that. At the same time, CMake became the go-to building tool for C++ projects, so this repository serves as a hub of CMake utilities for C++ development

## How to use it

1. Copy the desired file to your project
1. Include it in your `CMakeLists.txt`
1. Call the defined function with your target and desired options

### [warnings.cmake](cmake/warnings.cmake)

Defines the `cppmake_enable_warnings` function that adds warning options to the target's private compiler options

Argument          | Description
:---------------- | :----------------------------------
TARGET \<target\> | Defines the target
AS_ERRORS         | Enables treating warnings as errors

### [sanitize.cmake](cmake/sanitize.cmake)

Defines the `cppmake_sanitize` function that adds sanitizer options to the target's private compiler and link options

Argument          | Description
:---------------- | :------------------------------------------------------------------------------------------------
TARGET \<target\> | Defines the target
LEAK              | Enables [LeakSanitizer](https://clang.llvm.org/docs/LeakSanitizer.html)
STACK             | Enables [SafeStack](https://clang.llvm.org/docs/SafeStack.html)
MEMORY            | Enables [MemorySanitizer](https://clang.llvm.org/docs/MemorySanitizer.html)
THREAD            | Enables [ThreadSanitizer](https://clang.llvm.org/docs/ThreadSanitizer.html)
ADDRESS           | Enables [AddressSanitizer](https://clang.llvm.org/docs/AddressSanitizer.html)
UNDEFINED         | Enables [UndefinedBehaviorSanitizer](https://clang.llvm.org/docs/UndefinedBehaviorSanitizer.html)

> **Note:** At least one sanitizer must be specified in the arguments

## References

- [joseasoler/cmake_cpp_warnings](https://github.com/joseasoler/cmake_cpp_warnings)
- [cpp-best-practices/cmake_template](https://github.com/cpp-best-practices/cmake_template)
- [cpp-best-practices/cppbestpractices](https://github.com/cpp-best-practices/cppbestpractices/blob/master/02-Use_the_Tools_Available.md)
