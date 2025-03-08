cmake_minimum_required(VERSION 3.8)

project(hacker_cmake LANGUAGES C CXX)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

file(GLOB_RECURSE sources 
    "${CMAKE_SOURCE_DIR}/cudd/*.c"
    "${CMAKE_SOURCE_DIR}/util/*.c"
    "${CMAKE_SOURCE_DIR}/epd/*.c"
    "${CMAKE_SOURCE_DIR}/dddmp/*.c"
    "${CMAKE_SOURCE_DIR}/app/*.c"
    "${CMAKE_SOURCE_DIR}/nanotrav/*.c"
    "${CMAKE_SOURCE_DIR}/st/*.c"
    )

add_executable(hack ${sources})

target_include_directories(hack PUBLIC 
    "${CMAKE_SOURCE_DIR}/cudd"
    "${CMAKE_SOURCE_DIR}/util"
    "${CMAKE_SOURCE_DIR}/mtr"
    "${CMAKE_SOURCE_DIR}/dddmp"
    "${CMAKE_SOURCE_DIR}/epd"
    "${CMAKE_SOURCE_DIR}/nanotrav"
    "${CMAKE_SOURCE_DIR}/st"
    "${CMAKE_SOURCE_DIR}"
    )
