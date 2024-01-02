cmake_minimum_required(VERSION 3.28)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)
FetchContent_Declare(
    googletest
    GIT_REPOSITORY git@github.com:google/googletest.git
    GIT_TAG        release-1.12.1
    SOURCE_DIR ${PROJECT_SOURCE_DIR}/third_party/googletest/
)
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
set(BUILD_GMOCK OFF CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)


add_executable(
    unit_test
    unit_test.cpp
)

target_link_libraries(
    unit_test
    PRIVATE
    GTest::gtest_main
    # GTest::gtest
    # GTest::gmock
    lib_template
)

include(GoogleTest)
gtest_discover_tests(unit_test
    PROPERTIES
        LABELS "unit"
    DISCOVERY_TIMEOUT  # in seconds
        60
)