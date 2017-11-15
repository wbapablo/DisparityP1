cmake_minimum_required(VERSION 2.8.3)
project(disp)



find_package(OpenCV REQUIRED)
find_package(PCL 1.2 REQUIRED)





include_directories(${OpenCV_INCLUDE_DIRS})
include_directories(${PCL_INCLUDE_DIRS})


link_directories(${OpenCV_LIBRARY_DIRS})
link_directories(${PCL_LIBRARY_DIRS})


add_definitions(-std=c++0x)
add_definitions(${PCL_DEFINITIONS})


add_executable(disparity src/src.cpp)

target_link_libraries(disparity
        ${OpenCV_LIBRARIES}
        ${PCL_LIBRARIES}
)
