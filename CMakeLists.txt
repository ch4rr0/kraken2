cmake_minimum_required(VERSION 2.8)

project(kraken2)

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_compile_options(-Wall)
add_definitions(-DLINEAR_PROBING)

set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")

find_package(Threads REQUIRED)
link_libraries(Threads::Threads)

find_package(ZLIB REQUIRED)
link_libraries(${ZLIB_LIBRARIES})
include_directories(${ZLIB_INCLUDE_DIRS})

add_subdirectory(src)
