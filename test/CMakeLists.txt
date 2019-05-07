cmake_minimum_required(VERSION 3.5)
project (myproject)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(PythonLibs 2.7)

include_directories(${PYTHONHOME}/include)
include_directories(${PYTHONHOME}/Lib/site-packages/numpy/core/include)
link_directories(${PYTHONHOME}/libs)

add_definitions(-DMATPLOTLIBCPP_PYTHON_HEADER=Python.h)

add_executable(mytest test.cpp)
target_include_directories(mytest PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(mytest ${PYTHON_LIBRARIES})

