cmake_minimum_required(VERSION 3.20)
project(lightweight_renderer)

set(CMAKE_CXX_STANDARD 14)

set(INCLUDE_DIR ./include/)
set(HEADER_FILES ${INCLUDE_DIR}glad/glad.h ${INCLUDE_DIR}KHR/khrplatform.h)

find_package(glfw3 REQUIRED)
find_package(OpenGL REQUIRED)

add_executable(lightweight_renderer main.cpp glad.c ${HEADER_FILES})

target_include_directories(lightweight_renderer PRIVATE ${INCLUDE_DIR})
target_link_libraries(lightweight_renderer glfw OpenGL::GL ${CMAKE_DL_LIBS})
