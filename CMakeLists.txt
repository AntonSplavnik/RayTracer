cmake_minimum_required(VERSION 3.10)
project(OpenGLTest)

set(CMAKE_CXX_STANDARD 17)

find_package(OpenGL REQUIRED)

# Use pkg-config to find GLFW
find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)

include_directories(${GLFW_INCLUDE_DIRS})
link_directories(${GLFW_LIBRARY_DIRS})

add_executable(OpenGLTest main.cpp)

target_link_libraries(OpenGLTest
    ${GLFW_LIBRARIES}
    ${OPENGL_gl_LIBRARY}
)
