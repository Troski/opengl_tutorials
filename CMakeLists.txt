cmake_minimum_required(VERSION 3.5)
set(CMAKE_CXX_COMPILER /usr/bin/g++-7) # using g++7 compiler.
set(CMAKE_CXX_STANDARD 14) # Selected C++14 as the standard.
set(CMAKE_CXX_STANDARD_REQUIRED ON) # C++14 required for all targets.
set(CMAKE_CXX_EXTENSIONS OFF) #...without compiler extensions like gnu++11
project(opengl_tutorials)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
include_directories(${OPENGL_INCLUDE_DIRS}, ${GLUT_INCLUDE_DIRS})
include_directories(include)

add_executable(simple_draw src/simple_draw.cpp)
target_link_libraries(simple_draw ${OPENGL_LIBRARIES} ${GLUT_LIBRARY})