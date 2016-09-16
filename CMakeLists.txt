cmake_minimum_required (VERSION 3.2)
project (StatsdClient)

set (StatsdClient_VERSION_MAJOR 1)
set (StatsdClient_VERSION_MINOR 0)

include_directories ("${PROJECT_SOURCE_DIR}/src")
add_subdirectory (src)

configure_file (
  "${PROJECT_SOURCE_DIR}/src/StatsdClientConfig.h.in"
  "${PROJECT_BINARY_DIR}/StatsdClientConfig.h"
  )

include_directories("${PROJECT_BINARY_DIR}")

install (FILES "${PROJECT_BINARY_DIR}/StatsdClientConfig.h"
         DESTINATION include)

