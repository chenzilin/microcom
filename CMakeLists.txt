project(microcom)
cmake_minimum_required(VERSION 3.5)
aux_source_directory(. DIR_SRCS)
add_executable(microcom ${DIR_SRCS})

set (SRC_VERSION_MAJOR 1)
set (SRC_VERSION_MINOR 0)
set (SRC_VERSION_PATCH 1)
set (SRC_VERSION ${SRC_VERSION_MAJOR}.${SRC_VERSION_MINOR}.${SRC_VERSION_PATCH})

# 加入一个配置头文件，用于输出版本
set (PROJECT_VERSION "\"${SRC_VERSION}\"")
configure_file (
    "${PROJECT_SOURCE_DIR}/config.h.in"
    "${PROJECT_BINARY_DIR}/config.h"
)

add_definitions(-DUSE_CAN)

target_link_Libraries(microcom pthread)
target_link_Libraries(microcom readline)

install(TARGETS microcom DESTINATION bin)
