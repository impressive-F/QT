cmake_minimum_required(VERSION 3.8)

#指定c++标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
project(QtPro)

set(CMAKE_AUTOMOC ON)
#指定头文件包含目录
include_directories("D:\\software\\QT\\6.2.4\\msvc2019_64\\include")
#查找指定的模块
find_package(Qt6 COMPONENTS Widgets REQUIRED)
#在msvc编译器上必须指定Zc:_cplusplus
if(MSVC)
	add_compile_options(/Zc:_cplusplus)
endif()

#指定母庙生成位置
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/bin)
#根据指定的文件生成可执行文件
add_executable(QtPro "main.cpp" )

#给目标链接库文件
target_link_libraries(QtPro Qt6::Widgets)