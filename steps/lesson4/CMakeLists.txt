cmake_minimum_required(VERSION 2.6)

project(Tutorial)

option (USE_MYMATH "Use tutorial provided math implementation" ON)

# The version number
set(Tutorial_VERSION_MAJOR 1)
set(Tutorial_VERSION_MINOR 0)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR}/bin)

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
if (USE_MYMATH)
  include_directories("${PROJECT_SOURCE_DIR}/MathFunctions")
  add_subdirectory(MathFunctions)
  set (EXTRA_LIBS ${EXTRA_LIBS} MathFunctions)
endif (USE_MYMATH)

add_executable(Tutorial tutorial.cpp)
target_link_libraries (Tutorial  ${EXTRA_LIBS})
