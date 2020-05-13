cmake_minimum_required(VERSION 2.8)
project(test)
list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules)
set(CMAKE_CXX_STANDARD 11)
SET( G2O_ROOT /usr/local/include/g2o )
find_package( OpenCV REQUIRED )
find_package(Eigen3  REQUIRED)
find_package(G2O REQUIRED)
find_package( CSparse)
include_directories(
${EIGEN3_INCLUDE_DIR}
${OpenCV_INCLUDE_DIRS}
${G2O_INCLUDE_DIRS} 
${CSPARSE_INCLUDE_DIR} 
)
add_executable(pose_estimation_3d2d pose_estimation_3d2d.cpp)
target_link_libraries( pose_estimation_3d2d ${EIGEN3_LIB} ${OpenCV_LIBS} ${G2O_LIB} ${CSPARSE_LIB})
target_link_libraries(pose_estimation_3d2d g2o_core g2o_stuff)
