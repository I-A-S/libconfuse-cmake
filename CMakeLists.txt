cmake_minimum_required(VERSION 3.20)

project(LibConfuse VERSION 3.4.0 LANGUAGES C)

include(CheckFunctionExists)

set(CMAKE_C_STANDARD 99)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib")

check_function_exists(fmemopen HAVE_FMEMOPEN)
check_function_exists(reallocarray HAVE_REALLOCARRAY)
check_function_exists(strdup HAVE_STRDUP)
check_function_exists(strndup HAVE_STRNDUP)
check_function_exists(strcasecmp HAVE_STRCASECMP)

add_subdirectory(src)
