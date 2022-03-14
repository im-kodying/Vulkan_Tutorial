cmake_minimum_required(VERSION 3.21)
project(Vulkan_Tutorial)

set(CMAKE_CXX_STANDARD 14)

add_executable(Vulkan_Tutorial main.cpp)

link_directories("/opt/homebrew/Cellar/glfw/3.3.6/lib")
include_directories("/opt/homebrew/Cellar/glfw/3.3.6/include")


find_package(Vulkan REQUIRED)
target_include_directories(${PROJECT_NAME} PUBLIC ${Vulkan_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} Vulkan::Vulkan)

find_package(PkgConfig REQUIRED)
pkg_search_module(GLM REQUIRED glm)
include_directories(${GLM_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} ${GLM_LIBRARY_DIRS})

find_package(glfw3 3.3 REQUIRED)
target_link_libraries(${PROJECT_NAME} glfw)



