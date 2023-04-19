cmake_minimum_required(VERSION 3.0)

project(learn-opengl)

# Find the required packages
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

# Add the include directories for the libraries
include_directories(${OPENGL_INCLUDE_DIRS})
include_directories(${GLFW_INCLUDE_DIRS})

# Add the executable target
add_executable(learn-opengl src/main.cpp)

add_library(glad external/glad/src/glad.c)

target_include_directories(glad PUBLIC external/glad/include)


# Link the libraries to the executable target
target_link_libraries(learn-opengl ${OPENGL_LIBRARIES} glfw glad)