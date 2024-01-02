set(MY_LIB_NAME "lib_template")

# include(${PROJECT_SOURCE_DIR}/cmake/FindLibUring.cmake)

set(SOURCE_LIST
    "${PROJECT_SOURCE_DIR}/src/lib_template/template.cpp"
)

set(HEADER_LIST
    "${PROJECT_SOURCE_DIR}/include/lib_template/template.h"
)


add_library(${MY_LIB_NAME} STATIC)
target_sources(${MY_LIB_NAME}
    PRIVATE
    ${SOURCE_LIST}
    PUBLIC
    ${HEADER_LIST}
)

target_include_directories(${MY_LIB_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include)
# target_compile_features(${MY_LIB_NAME} PUBLIC cxx_std_17)
target_compile_features(${MY_LIB_NAME} PUBLIC cxx_std_20)