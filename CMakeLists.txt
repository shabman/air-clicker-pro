cmake_minimum_required(VERSION 3.23.2)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_MODULE_PATH /home/user/Libs/cmake)

project(ACP)

add_subdirectory(cegui)
add_subdirectory(cegui-dependencies)

add_executable(${PROJECT_NAME} src/main.cpp)

target_link_libraries(${PROJECT_NAME} ${CEGUI_LIBRARIES})