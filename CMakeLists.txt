cmake_minimum_required(VERSION 3.15)
project(OmniSolvers LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 添加 pybind11 子目录
add_subdirectory(external/pybind11)

# 查找并处理Python相关依赖
find_package(Python REQUIRED COMPONENTS Development)

# 添加第三方库的头文件搜索路径  
target_include_directories(OmniSolvers PRIVATE ${PROJECT_SOURCE_DIR}/external/eigen)

# 添加 core 子目录
add_subdirectory(core)