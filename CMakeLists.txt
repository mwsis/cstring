
cmake_minimum_required(VERSION 3.0)

project(cstring)

include_directories(include)

add_subdirectory(./projects/cstring.core)

install(TARGETS cstring)

install(
    DIRECTORY ${CMAKE_SOURCE_DIR}/include/
    DESTINATION include
    FILES_MATCHING PATTERN "*.h"
)

