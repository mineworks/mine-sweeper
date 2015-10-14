cmake_minimum_required(VERSION 3.0)
project(mine-sweeper)

add_executable(mine-sweeper src/main.cpp)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}")
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR})

find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIR})

find_package(GLFW 3.0.0)
include_directories(${GLFW_INCLUDE_DIRS})
message(STATUS "FIND GLFW_INCLUDE_DIRS " ${GLFW_INCLUDE_DIRS})

target_link_libraries(mine-sweeper ${OPENGL_LIBRARIES} ${GLFW_LIBRARIES})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

install(TARGETS mine-sweeper RUNTIME DESTINATION bin)