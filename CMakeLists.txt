cmake_minimum_required(3.1)
set(CMAKE_CXX_STANDARD 17)

find_package(OpenMP)

set(ECP_LIBRARY "Economic-Planning")
project(${ECONOMIC_PLANNING})
add_executable(${ECONOMIC_PLANNING} main.cpp)

