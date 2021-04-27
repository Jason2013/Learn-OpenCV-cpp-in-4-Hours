cmake_minimum_required(VERSION 3.19)
project(opencv_Chapter4)

# set environment variable 'OPENCV_ROOT' before run cmake
# set OPENCV_ROOT=D:\app\opencv-4.5.2-vc14_vc15\opencv\build

set(MY_TARGET Chapter4)

add_executable(${MY_TARGET} ../Chapter4.cpp)
target_include_directories(${MY_TARGET} PRIVATE $ENV{OPENCV_ROOT}/include)
target_link_libraries(${MY_TARGET} PRIVATE $ENV{OPENCV_ROOT}/x64/vc15/lib/opencv_world452$<$<CONFIG:Debug>:d>.lib)
set_target_properties(${MY_TARGET} PROPERTIES
    VS_DEBUGGER_WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}
    VS_DEBUGGER_ENVIRONMENT "PATH=$ENV{OPENCV_ROOT}\\x64\\vc15\\bin")
 
