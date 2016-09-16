cmake_minimum_required (VERSION 3.2)
project (StatsdClient)

set (StatsdClient_VERSION_MAJOR 1)
set (StatsdClient_VERSION_MINOR 0)

# check for headers
# unix specific headers
include (${CMAKE_ROOT}/Modules/CheckIncludeFile.cmake)
if(UNIX)
  CHECK_INCLUDE_FILE("sys/socket.h" HAVE_SYS_SOCKET_H)
  CHECK_INCLUDE_FILE("arpa/inet.h"  HAVE_APRA_INET_H)
  CHECK_INCLUDE_FILE("netdb.h"      HAVE_NETDB_H)
  CHECK_INCLUDE_FILE("unistd.h"     HAVE_UNISTD_H)
endif(UNIX)

# windows-specific headers
if(NOT UNIX)
  CHECK_INCLUDE_FILE("winsock2.h"     HAVE_WINSOCK2_H)
  CHECK_INCLUDE_FILE("ws2tcpip.h"     HAVE_WS2TCPIP_H)
endif(NOT UNIX)


include_directories ("${PROJECT_SOURCE_DIR}/src")
add_subdirectory (src)

configure_file (
  "${PROJECT_SOURCE_DIR}/src/StatsdClientConfig.h.in"
  "${PROJECT_BINARY_DIR}/StatsdClientConfig.h"
  )

include_directories("${PROJECT_BINARY_DIR}")

install (FILES "${PROJECT_BINARY_DIR}/StatsdClientConfig.h"
         DESTINATION include)

