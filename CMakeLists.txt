cmake_minimum_required(VERSION 3.21)

set(ECP Economic-Planning)
set(CMAKE_OBJECT_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/intermediate_objects)

project(${ECP})

set(CMAKE_CXX_STANDARD 17)

# -------------------- Packages -------------------- #

find_package(Vulkan)

# Link against Vulkan
target_link_libraries(MyProject PRIVATE ${Vulkan_LIBRARIES})


find_package(OpenMP)
if(OpenMP_CXX_FOUND)
    target_link_libraries(MyProject PRIVATE OpenMP::OpenMP_CXX)
endif()

# -------------------- Library -------------------- #

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

add_executable(${ECP} main.cpp ${SRC} ${INC})

if(OpenMP_CXX_FOUND)
    target_link_libraries(your_target_name OpenMP::OpenMP_CXX)
endif()

set_target_properties(${ECP} PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin/${CMAKE_SYSTEM_NAME}/)

# -------------------- Main Program -------------------- #
