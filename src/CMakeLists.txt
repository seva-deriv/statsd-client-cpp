add_library(StatsdClient statsd_client.cpp)

include_directories("${PROJECT_BINARY_DIR}")

install (TARGETS StatsdClient DESTINATION lib)
install (FILES statsd_client.h DESTINATION include)
