add_library(StatsdClient2 statsd_client.cpp)

install (TARGETS StatsdClient2 DESTINATION bin)
install (FILES MathFunctions.h DESTINATION include)
