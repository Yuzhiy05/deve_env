cmake_minimum_required(VERSION 3.5.0)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED true)
set(CMAKE_CXX_EXTENSIONS OFF)
project(hello)

message(STATUS "PROJECT_SOURCE_DIR目录为=${PROJECT_SOURCE_DIR}")
message(STATUS "PROJECT_BINARY_DIR目录为=${PROJECT_BINARY_DIR}")

set(ROOT_DIR "${PROJECT_SOURCE_DIR}/src")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/out)

#file(GLOB list_src LIST_DIRECTORIES true RELATIVE ${ROOT_DIR}/* CONFIGURE_DEPENDS ./src/*.cpp )

#aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LIST)

#message(STATUS "file查找文件=${list_src}")

#include_directories(src)

#message(STATUS "源码路径SRC_LIST文件=${SRC_LIST}")

add_subdirectory(spdlog)

include_directories(spdlog/include/spdlog)


add_executable(hello main.cpp )

target_link_libraries(hello spdlog)