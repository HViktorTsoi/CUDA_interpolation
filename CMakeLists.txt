cmake_minimum_required(VERSION 3.17)
project(G_IDW)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall -g -pthread")

find_package(CUDA REQUIRED)

set(CUDA_NVCC_FLAGS ${CUDA_NVCC_FLAGS} "-Xcompiler -Wextra")

include_directories(${CUDA_INCLUDE_DIRS})
include_directories(include)

cuda_add_executable(G_IDW src/main.cu include/idw.h src/idw.cu)