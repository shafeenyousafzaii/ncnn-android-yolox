project(ncnnyolox)

cmake_minimum_required(VERSION 3.10)

set(OpenCV_DIR ${CMAKE_SOURCE_DIR}/opencv-mobile-3.4.20-android/sdk/native/jni)
find_package(OpenCV REQUIRED core imgproc)

set(ncnn_DIR ${CMAKE_SOURCE_DIR}/ncnn-20240410-android-vulkan/${x86_64)}/lib/cmake/ncnn)
find_package(ncnn REQUIRED)

add_library(ncnnyolox SHARED yoloxncnn.cpp yolox.cpp ndkcamera.cpp)

target_link_libraries(ncnnyolox ncnn ${OpenCV_LIBS} camera2ndk mediandk)
