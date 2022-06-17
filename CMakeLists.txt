cmake_minimum_required(VERSION 3.23.2)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_MODULE_PATH /home/user/Libs/cmake)

project(ACP)

add_subdirectory(cegui)
add_subdirectory(cegui-dependencies)
add_subdirectory(glm)

find_package(glm REQUIRED)

target_include_directories(${PROJECT_NAME} PUBLIC cegui/cegui/include)
target_link_directories(${PROJECT_NAME} PRIVATE cegui/cegui/src)

add_executable(${PROJECT_NAME} src/main.cpp)

target_link_libraries(${PROJECT_NAME} cegui glm)