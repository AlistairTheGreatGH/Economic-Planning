cmake_minimum_required(VERSION 3.21)
set(CMAKE_CXX_STANDARD 17)

set(CMAKE_OBJECT_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/intermediate_objects)

# -------------------- Library -------------------- #

file(GLOB_RECURSE INC
    "${CMAKE_CURRENT_SOURCE_DIR}/inc/*.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/inc/*.hpp"
)

file(GLOB_RECURSE SRC
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.c"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cxx"
)

set(ECP Economic-Planning)
project(${ECP})

add_executable(${ECP} main.cpp ${SRC} ${INC})

set_target_properties(${ECP} PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin/${CMAKE_SYSTEM_NAME}/)

# -------------------- Main Program -------------------- #
