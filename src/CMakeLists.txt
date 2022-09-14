add_library(StatsdClient statsd_client.cpp)

target_include_directories(StatsdClient PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} ${PROJECT_BINARY_DIR})

install (TARGETS StatsdClient DESTINATION lib)
install (FILES statsd_client.h DESTINATION include)
