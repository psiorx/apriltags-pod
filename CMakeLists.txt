cmake_minimum_required(VERSION 2.6)
project(apriltags)


set(POD_NAME apriltags)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu99")
include(cmake/pods.cmake)

file(GLOB_RECURSE SOURCE_FILES "src/*.c")

include_directories(src)
include_directories(src/common)

include_directories(AprilTags . /opt/local/include)
add_library(apriltags ${SOURCE_FILES})

pods_install_libraries(apriltags)

file(GLOB_RECURSE header_files "src/*.h")
pods_install_headers(${header_files} DESTINATION AprilTags/)

pods_install_pkg_config_file(apriltags
    LIBS -lapriltags
    VERSION 1.0.0)

