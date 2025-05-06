cmake_minimum_required(VERSION 3.5)

project(ezremote-dpi)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-keyword-macro -fPIC -fPIE -march=znver2 -Wall -fstack-protector-all")
set(CMAKE_CXX_FLAGS "${CMAKE_C_FLAGS} -DDEBUG -gfull -gdwarf-2 -O0 -pedantic -pedantic-errors")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O0 ")

include_directories(
  source
)

add_executable(${PROJECT_NAME}.elf
  source/main.cpp
)

target_link_libraries(${PROJECT_NAME}.elf
  SceSysCore
  kernel_sys
  SceAppInstUtil
)
