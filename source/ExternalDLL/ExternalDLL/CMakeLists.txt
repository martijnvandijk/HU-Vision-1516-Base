cmake_minimum_required(VERSION 2.9)

project(hu_vision)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package(PkgConfig)
pkg_check_modules(OPENCV opencv)
link_directories(${OPENCV_LIBRARY_DIRS})
include_directories(${OPENCV_INCLUDE_DIRS})

file(GLOB SOURCES "*.cpp")
list(REMOVE_ITEM SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/export.cpp")
add_executable(hu_vision ${SOURCES})
target_link_libraries(hu_vision ${OPENCV_LIBRARIES})