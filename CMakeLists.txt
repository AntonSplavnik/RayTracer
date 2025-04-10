cmake_minimum_required(VERSION 3.10)
project(RayTracer)

set(CMAKE_CXX_STANDARD 17)

find_package(OpenGL REQUIRED)
find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)

include_directories(${GLFW_INCLUDE_DIRS} ${OPENGL_INCLUDE_DIR})
link_directories(${GLFW_LIBRARY_DIRS})

add_executable(RayTracer main.cpp)

target_link_libraries(RayTracer
    ${GLFW_LIBRARIES}
    ${OPENGL_gl_LIBRARY}
)
