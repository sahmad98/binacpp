cmake_minimum_required(VERSION 3.14)

project(binacpp)

set(LIBCURL_DIR "lib/libcurl-7.56.0")
set(LIBWS_DIR "lib/libwebsockets-2.4.0")
set(CMAKE_VERBOSE_MAKEFILE ON)

include_directories(${LIBCURL_DIR}/include)
include_directories(${LIBWS_DIR}/include)

link_directories(${LIBCURL_DIR}/lib)
link_directories(${LIBWS_DIR}/lib)

include(FetchContent)

FetchContent_Declare(
  jsoncpp
  GIT_REPOSITORY https://github.com/open-source-parsers/jsoncpp.git
  GIT_TAG 1.8.4
  CONFIGURE_COMMAND "-DBUILD_SHARED_LIB=OFF"
)

FetchContent_MakeAvailable(jsoncpp)

include_directories(${jsoncpp_SOURCE_DIR}/include)

add_subdirectory(example)
add_subdirectory(src)
