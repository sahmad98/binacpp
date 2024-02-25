cmake_minimum_required(VERSION 3.0)

project(libjsoncpp LANGUAGES CXX)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17 -O3 -g")

include_directories(./include)
add_library(jsoncpp SHARED src/jsoncpp.cpp)
