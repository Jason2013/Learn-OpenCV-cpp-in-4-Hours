cmake_minimum_required(VERSION 3.19)
project(opencv_Chapter8)

# set environment variable 'OPENCV_ROOT' before run cmake
# set OPENCV_ROOT=D:\app\opencv-4.5.2-vc14_vc15\opencv\build

set(MY_TARGET Chapter8)

add_executable(${MY_TARGET} ../Chapter8.cpp)
target_include_directories(${MY_TARGET} PRIVATE $ENV{OPENCV_ROOT}/include)
target_link_libraries(${MY_TARGET} PRIVATE $ENV{OPENCV_ROOT}/x64/vc15/lib/opencv_world452$<$<CONFIG:Debug>:d>.lib)
file(REAL_PATH .. WORKING_DIR)
set_target_properties(${MY_TARGET} PROPERTIES
    VS_DEBUGGER_WORKING_DIRECTORY ${WORKING_DIR}
    VS_DEBUGGER_ENVIRONMENT "PATH=$ENV{OPENCV_ROOT}\\x64\\vc15\\bin")
 
