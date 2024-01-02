cmake_minimum_required(VERSION 3.28)

project(
    CPP_PROJECT_TEMPLATE
    VERSION 0.1
    DESCRIPTION "A template for C++ projects"
    LANGUAGES CXX C
)
message(STATUS "Using CMake version ${CMAKE_VERSION}")

add_subdirectory(src)
add_subdirectory(app)