cmake_minimum_required(VERSION 3.20)
set(CMAKE_CXX_COMPILER clang++)

# set binary directory
set(PROJECT_ROOT_DIR  "${CMAKE_CURRENT_LIST_DIR}/..")
set(PROJECT_SRC_DIR  "${PROJECT_ROOT_DIR}/src")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/..)


project(fs3d)

add_executable(fs3d)
target_sources(fs3d PUBLIC
    ${PROJECT_SRC_DIR}/main.cpp
    ${PROJECT_SRC_DIR}/VulkanRenderer.cpp
)
target_include_directories(fs3d PUBLIC
    ${PROJECT_SRC_DIR}
)
target_link_libraries(fs3d SDL2 vulkan)
