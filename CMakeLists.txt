cmake_minimum_required(VERSION 3.20)

project(c-logger
        VERSION 1.0
        DESCRIPTION "A simple logging library implemented in C90"
        LANGUAGES C)

include(cmake/enable-coloration.cmake)

option(BUILD_DOCUMENTATION "Build documentation" OFF)
option(BUILD_EXAMPLES "Build examples" OFF)

add_compile_options(-Wall -Wextra -Werror)

add_subdirectory(lib)

if (BUILD_EXAMPLES)
  add_subdirectory(examples)
endif ()

if (BUILD_DOCUMENTATION)
  add_subdirectory(docs)
endif ()
