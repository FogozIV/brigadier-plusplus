cmake_minimum_required(VERSION 3.28)
project(Brigadier VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 17)

file(GLOB_RECURSE HEADERS "include/single-header/*.h")
file(GLOB_RECURSE HEADERS "include/header-only/brigadier/*.hpp")
file(GLOB_RECURSE HEADERS "include/header-only/brigadier/*.h")
file(GLOB_RECURSE HEADERS "include/single-header/*.hpp")

add_library(${PROJECT_NAME} INTERFACE)
target_include_directories(${PROJECT_NAME} INTERFACE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/single-header>
        $<INSTALL_INTERFACE:include>
)