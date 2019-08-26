cmake_minimum_required(VERSION 2.6)

project(Tutorial)

# The version number
set(Tutorial_VERSION_MAJOR 1)
set(Tutorial_VERSION_MINOR 0)
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})

# Configure a header file to pass some
# of the CMake settings to the source
# code
configure_file(
	"${PROJECT_SOURCE_DIR}/TutorialConfig.h.in"
	"${PROJECT_BINARY_DIR}/TutorialConfig.h"
    )

# Add the binary tree to the search path
# for include files so that we will find
# TutorialConfig.h
include_directories("${PROJECT_BINARY_DIR}")

add_executable(Tutorial tutorial.cpp)
