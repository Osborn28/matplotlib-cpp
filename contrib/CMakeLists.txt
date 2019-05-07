cmake_minimum_required(VERSION 3.5)
project (MatplotlibCPP_Test)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(PythonLibs 2.7)

include_directories(${PYTHONHOME}/include)
include_directories(${PYTHONHOME}/Lib/site-packages/numpy/core/include)
link_directories(${PYTHONHOME}/libs)

add_definitions(-DMATPLOTLIBCPP_PYTHON_HEADER=Python.h)

# message(STATUS "*** dump start cmake variables ***")
# get_cmake_property(_variableNames VARIABLES)
# foreach(_variableName ${_variableNames})
#         message(STATUS "${_variableName}=${${_variableName}}")
# endforeach()
# message(STATUS "*** dump end ***")

add_executable(minimal ${CMAKE_CURRENT_SOURCE_DIR}/../examples/minimal.cpp)
target_include_directories(minimal PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(minimal ${PYTHON_LIBRARIES})

add_executable(basic ${CMAKE_CURRENT_SOURCE_DIR}/../examples/basic.cpp)
target_include_directories(basic PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(basic ${PYTHON_LIBRARIES})

add_executable(modern ${CMAKE_CURRENT_SOURCE_DIR}/../examples/modern.cpp)
target_include_directories(modern PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(modern ${PYTHON_LIBRARIES})

add_executable(animation ${CMAKE_CURRENT_SOURCE_DIR}/../examples/animation.cpp)
target_include_directories(animation PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(animation ${PYTHON_LIBRARIES})

add_executable(nonblock ${CMAKE_CURRENT_SOURCE_DIR}/../examples/nonblock.cpp)
target_include_directories(nonblock PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(nonblock ${PYTHON_LIBRARIES})

add_executable(xkcd ${CMAKE_CURRENT_SOURCE_DIR}/../examples/xkcd.cpp)
target_include_directories(xkcd PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(xkcd ${PYTHON_LIBRARIES})

add_executable(bar ${CMAKE_CURRENT_SOURCE_DIR}/../examples/bar.cpp)
target_include_directories(bar PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(bar ${PYTHON_LIBRARIES})

add_executable(surface ${CMAKE_CURRENT_SOURCE_DIR}/../examples/surface.cpp)
target_include_directories(surface PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(surface ${PYTHON_LIBRARIES})

add_executable(update ${CMAKE_CURRENT_SOURCE_DIR}/../examples/update.cpp)
target_include_directories(update PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(update ${PYTHON_LIBRARIES})
