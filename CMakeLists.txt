cmake_minimum_required(VERSION 3.5)

project(knt LANGUAGES CXX)

#版本14以下可能会导致abseil不支持
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# add_subdirectory(third/)

include_directories(${PROJECT_NAME} ${CMAKE_CURRENT_LIST_DIR}/include)
include_directories(${PROJECT_NAME} ${CMAKE_CURRENT_LIST_DIR}/include/knt)
#包含的源文件和头文件
set(SOURCES
    include/knt/base64.h
    src/base64.cpp
    include/knt/knt.h
    src/knt.cpp
    include/knt/rtcm_decode.h
    src/rtcm_decode.cpp)
    

add_library(${PROJECT_NAME} STATIC ${SOURCES})

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
