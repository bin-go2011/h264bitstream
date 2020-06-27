cmake_minimum_required(VERSION 3.15)
project(h264bitstream LANGUAGES C)
add_library(h264bitstream
    h264_stream.c 
    h264_sei.c 
    h264_nal.c
)

add_definitions(-Wall -std=c99)

add_executable(h264_analyze h264_analyze.c)
target_link_libraries(h264_analyze h264bitstream)

add_executable(svc_split svc_split.c)
target_link_libraries(svc_split h264bitstream)
