cmake_minimum_required (VERSION 2.6)
project(HomeAutomationServer)
# The version number
set(HomeAutomationServer_VERSION_MAJOR 0)
set(HomeAutomationServer_VERSION_MINOR 1)

# include header directories
include_directories ( "{$PROJECT_SOURCE_DIR}/include" )
add_subdirectory (include)

# configure a header file to pass some of the CMake settings
# to the source code
configure_file(
    "${PROJECT_SOURCE_DIR}/include/HomeAutomationServerConfig.h.in"
    "${PROJECT_BINARY_DIR}/HomeAutomationServerConfig.h"
    )

# add the binary tree to the search path for include files
# so that we will find HomeAutomationServerConfig.h
include_directories("${PROJECT_BINARY_DIR}")


add_executable(HomeAutomationServer main.cxx)
