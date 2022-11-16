cmake_minimum_required(VERSION 2.8)
project(test)
find_package(OpenCV)
include_directories(
${OpenCV_INCLUDE_DIRS}
)

add_executable(pymaid pymaid.cpp)
target_link_libraries(pymaid ${OpenCV_LIBS})