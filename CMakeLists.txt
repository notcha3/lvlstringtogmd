cmake_minimum_required(VERSION 3.11.x)
project(lvlstringtogmd C)
set(CMAKE_C_STANDARD 99)

add_executable(${PROJECT_NAME} main.c main.h)

if(MSVC)
  target_compile_options(${PROJECT_NAME} PRIVATE /W4 /WX)
  add_definitions(-D_CRT_SECURE_NO_WARNINGS)
else()
  target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -Wpedantic -Werror -O2)
endif()