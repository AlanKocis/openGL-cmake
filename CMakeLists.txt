cmake_minimum_required( VERSION 3.2 )
project(test)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(dep/glfw)
add_executable(test src/main.cpp src/glad.c)


target_link_libraries(test glfw)
target_include_directories(test PRIVATE ${CMAKE_SOURCE_DIR}/include)
set_property( DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT test )

