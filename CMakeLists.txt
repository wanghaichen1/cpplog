cmake_minimum_required(VERSION 3.14)

# 设置项目名称和版本
project(cpplog VERSION 1.0)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 源文件和头文件
set(SOURCES main.cpp)
set(HEADERS cpplog.hpp)

# 添加可执行文件
add_executable(cpplog_test ${SOURCES})

# 定义编译选项
target_compile_definitions(cpplog_test PRIVATE CPPLOG_THREADING CPPLOG_SYSTEM_IDS)

# 添加清理命令
set_property(DIRECTORY APPEND PROPERTY ADDITIONAL_MAKE_CLEAN_FILES "*.log")

add_library(cpplog INTERFACE)
target_include_directories(cpplog INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})