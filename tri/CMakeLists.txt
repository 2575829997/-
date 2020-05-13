cmake_minimum_required( VERSION 2.8 )
project( imageBasics )
 
# 添加c++ 11标准支持
set( CMAKE_CXX_FLAGS "-std=c++11" )
 
# 寻找OpenCV库
set(OpenCV_DIR /media/ufo/存储/qq下载的/ufoo/opencv-3.4.1/)
find_package( OpenCV 3 REQUIRED )
# 添加头文件
include_directories( ${OpenCV_INCLUDE_DIRS} )
 
add_executable( triangulation triangulation.cpp )
# 链接OpenCV库
target_link_libraries( triangulation ${OpenCV_LIBS} )


