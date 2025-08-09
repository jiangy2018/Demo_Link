cmake_minimum_required(VERSION 3.25.1) #最低版本

project(Demo_Link) #工程文件

include_directories(${PROJECT_SOURCE_DIR}/include) #包含头文件

file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/src/main.c)

set(HOME ${CMAKE_CURRENT_SOURCE_DIR})
#定义一个变量用于存储一个绝对路径
set(EXECUTABLE_OUTPUT_PATH ${HOME}/bin)
# 包含静态库路径
link_directories(${PROJECT_SOURCE_DIR}/lib)
# 链接静态库
link_libraries(calc)

add_executable(app ${SRC_LIST})
