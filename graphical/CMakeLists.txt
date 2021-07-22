cmake_minimum_required(VERSION 3.0.0)
project(graphical VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(graphical main.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

add_subdirectory("d01_a_window")
add_subdirectory("d02_triangle")