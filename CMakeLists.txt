cmake_minimum_required(VERSION 2.6)

project(FDTD3dCUDA)

set (CMAKE_CXX_STANDARD 14)

find_package(CUDA)

message(STATUS "CMAKE_MODULE_PATH is " ${CMAKE_CURRENT_SOURCE_DIR})

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

cuda_add_library(FDTD3dCUDAKernel STATIC src/FDTD3dGPU.cu)

add_executable(FDTD3dCUDA src/FDTD3d.cpp src/FDTD3dReference.cpp)
target_link_libraries(FDTD3dCUDA FDTD3dCUDAKernel)