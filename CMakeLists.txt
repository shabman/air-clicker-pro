cmake_minimum_required(VERSION 3.23.2)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_MODULE_PATH /home/user/Libs/cmake)

project(ACP)

add_executable(${PROJECT_NAME} src/main.cpp)

FIND_PACKAGE(PkgConfig REQUIRED)
pkg_check_modules(CLUTTERGTK REQUIRED "clutter-gtk-1.0 >= 1.0.0")
pkg_check_modules(CLUTTER REQUIRED "clutter-1.0 >= 1.0.0")
pkg_check_modules(GTK+ REQUIRED "gtk+-3.0 >= 3.0.8")

target_link_directories(${PROJECT_NAME} PUBLIC ${GTK3_LIBRARY_DIRS} ${CLUTTER_LIBRARY_DIRS})
target_include_directories(${PROJECT_NAME} PUBLIC ${GTK3_INCLUDE_DIRS} ${CLUTTER_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} ${GTK3_LIBRARIES} ${CLUTTER_LIBRARIES})