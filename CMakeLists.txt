CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
SET(CMAKE_CXX_COMPILER "g++")
SET(CMAKE_C_COMPILER "gcc")

#工程名称
PROJECT(performance)

#编译参数
SET(CMAKE_CXX_FLAGS "-O2 -std=c++11")

#库引用
SET(LIBS pthread rt)

#宏定义
#ADD_DEFINITIONS(-D_LINUX_VERSION)

#附加包含目录
AUX_SOURCE_DIRECTORY(./ SRC_LIST)

#引用目录
INCLUDE_DIRECTORIES(./)

#动态库编译
ADD_LIBRARY(performance SHARED ${SRC_LIST})	

#链接库设置
TARGET_LINK_LIBRARIES(performance ${LIBS})
