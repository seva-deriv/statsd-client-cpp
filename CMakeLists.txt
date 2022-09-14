cmake_minimum_required (VERSION 3.2)
project (StatsdClient)

set (StatsdClient_VERSION_MAJOR 1)
set (StatsdClient_VERSION_MINOR 1)

add_subdirectory ("src")
add_subdirectory ("demo")

configure_file (
  "src/StatsdClientConfig.h.in"
  "StatsdClientConfig.h"
  )

set_property (SOURCE "StatsdClientConfig.h" PROPERTY GENERATED TRUE)

target_compile_features(StatsdClient PRIVATE cxx_nullptr)

install (FILES "${PROJECT_BINARY_DIR}/StatsdClientConfig.h"
         DESTINATION include)

