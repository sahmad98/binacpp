cmake_minimum_required(VERSION 3.0)

project(binacpp)

set(LIBCURL_DIR "lib/libcurl-7.56.0")
set(JSONCPP_DIR "lib/jsoncpp-1.8.3")
set(LIBWS_DIR "lib/libwebsockets-2.4.0")
set(CMAKE_VERBOSE_MAKEFILE ON)

include_directories(${LIBCURL_DIR}/include)
include_directories(${JSONCPP_DIR}/include)
include_directories(${LIBWS_DIR}/include)

link_directories(${LIBCURL_DIR}/lib)
link_directories(${JSONCPP_DIR}/build)
link_directories(${LIBWS_DIR}/lib)

add_subdirectory(${JSONCPP_DIR})
add_subdirectory(example)
add_subdirectory(src)
