cmake_minimum_required(VERSION 3.10)
project(test)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_subdirectory(vendor/glfw)
add_subdirectory(vendor/glad)
add_subdirectory(vendor/imgui)

find_package(OpenGL REQUIRED)

add_executable(${PROJECT_NAME} 
    src/main.cpp)

target_link_libraries(${PROJECT_NAME} 
    OpenGL::GL
    glfw
    glad
    imgui)