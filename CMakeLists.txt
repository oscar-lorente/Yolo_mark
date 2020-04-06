cmake_minimum_required(VERSION 2.8)
project( yolo_mark CXX )
find_package( OpenCV REQUIRED )
find_package(Boost REQUIRED COMPONENTS filesystem)

include_directories(${Boost_INCLUDE_DIRS})

set( sources main.cpp )

add_executable( yolo_mark ${sources} )

target_compile_options( yolo_mark PUBLIC -std=c++11 -fpermissive -w -Wall )

target_link_libraries( yolo_mark ${Boost_LIBRARIES} ${OpenCV_LIBS} -L/usr/lib64 -ldl )
