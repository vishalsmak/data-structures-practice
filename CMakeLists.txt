cmake_minimum_required(VERSION 3.14)
project(data-structure-practice C CXX)

set(CMAKE_CXX_STANDARD 14)

set(ELF_NAME "dataStructurePractice.elf")

add_executable(${ELF_NAME} main.cpp)

add_custom_target(PRINT_ELF_SIZE_${ELF_NAME} ALL COMMAND ${SIZE_TOOL} --format=berkeley $<TARGET_FILE:${ELF_NAME}> --radix=10 DEPENDS ${ELF_NAME})
add_dependencies(PRINT_ELF_SIZE_${ELF_NAME} ${ELF_NAME})
add_definitions(-DUSE_FULL_LL_DRIVER)