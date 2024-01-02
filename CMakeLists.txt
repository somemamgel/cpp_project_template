cmake_minimum_required(VERSION 3.28)

project(CPP_Project_Template 
    VERSION 0.1
    DESCRIPTION "A CPP Template Project"
    LANGUAGES C CXX
)
message(STATUS "Using Cmake version ${CMAKE_VERSION}")


add_subdirectory(src)
add_subdirectory(app)

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
    include(CTest)

    # Docs only available if this is the main app
    find_package(Doxygen)
    if(Doxygen_FOUND)
        add_subdirectory(docs)
    else()
        message(STATUS "Doxygen not found, not building docs")
    endif()
endif()

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME AND BUILD_TESTING)
    add_subdirectory(tests)
    enable_testing()
endif()
