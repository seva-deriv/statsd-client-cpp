add_library(StatsdClient statsd_client.cpp)

install (TARGETS StatsdClient DESTINATION lib)
install (FILES statsd_client.h DESTINATION include)
