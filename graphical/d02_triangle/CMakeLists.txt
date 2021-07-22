cmake_minimum_required(VERSION 3.0.0)
set(proj "d02_Triangle")
project(${proj} VERSION 0.1.0)
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
# set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -lglew -lglfw -framework OpenGL")

# find_package(GLEW REQUIRED)
find_library(glew_lib GLEW)
find_library(glfw_lib GLFW)
find_library(opengl_lib OpenGL)

add_executable(${proj} main.cpp)

# target_link_libraries(${proj} ${GLEW_LIBRARIES})
# target_include_directories(${proj} PUBLIC ${GLEW_INCLUDE_DIRS})
# target_link_libraries(${proj} glew)
# target_link_libraries(${proj} "glfw")
target_link_libraries(${proj} ${glew_lib})
target_link_libraries(${proj} ${glfw_lib})
target_link_libraries(${proj} ${opengl_lib})
target_include_directories(${proj} PUBLIC "/usr/local/include")




