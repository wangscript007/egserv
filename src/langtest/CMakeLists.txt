cmake_minimum_required(VERSION 2.6)
PROJECT(langtest)
SET(_ ${PROJECT_SOURCE_DIR})
AUX_SOURCE_DIRECTORY(${_} SRC_LIST)
MESSAGE(STATUS "${CMAKE_SHARED_LIBRARY_LINK_C_FLAGS}")
SET(LIBRARY_OUTPUT_PATH ${_})
SET(EXECUTABLE_OUTPUT_PATH  ${_})

ADD_DEFINITIONS(-g -Wall -std=c++11 -Wno-deprecated -fdiagnostics-color=always)
INCLUDE_DIRECTORIES(${_})
LINK_DIRECTORIES(${_})

ADD_EXECUTABLE(langtest ${SRC_LIST})
TARGET_LINK_LIBRARIES(langtest pthread)