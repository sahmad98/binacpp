cmake_minimum_required(VERSION 3.14)

project(binacpp)

set(CMAKE_VERBOSE_MAKEFILE ON)

include(FetchContent)

FetchContent_Declare(
  jsoncpp
  GIT_REPOSITORY https://github.com/open-source-parsers/jsoncpp.git
  GIT_TAG 1.8.4
)

FetchContent_MakeAvailable(jsoncpp)

include_directories(${jsoncpp_SOURCE_DIR}/include)

add_subdirectory(example)
add_subdirectory(src)
