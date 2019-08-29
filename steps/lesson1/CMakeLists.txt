cmake_minimum_required (VERSION 2.6)

project (Tutorial)

message("Binary dir " ${CMAKE_BINARY_DIR})
message("Source dir " ${CMAKE_SOURCE_DIR})

add_executable (Tutorial tutorial.cpp)
