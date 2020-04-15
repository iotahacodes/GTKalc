cmake_minimum_required(VERSION 3.17)
project(GTKalc C)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c11")
find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})
add_definitions(${GTK3_CFLAGS_OTHER})

set(SOURCE_FILES main.c buttons.h)
add_executable(GTKalc ${SOURCE_FILES})
target_link_libraries(GTKalc ${GTK3_LIBRARIES} m)