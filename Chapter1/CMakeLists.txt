cmake_minimum_required(VERSION 3.19)
project(opencv_project1)

set(OPENCV_ROOT D:/app/opencv-4.5.2-vc14_vc15/opencv/build)
set(MY_TARGET Project1)

add_executable(${MY_TARGET} ../Chapter1.cpp)
target_include_directories(${MY_TARGET} PRIVATE ${OPENCV_ROOT}/include)
target_link_libraries(${MY_TARGET} PRIVATE ${OPENCV_ROOT}/x64/vc15/lib/opencv_world452$<$<CONFIG:Debug>:d>.lib)
