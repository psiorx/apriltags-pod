cmake_minimum_required(VERSION 2.8.3)
project(apriltags)

find_package(catkin REQUIRED COMPONENTS)

catkin_package(LIBRARIES ${PROJECT_NAME} 
  INCLUDE_DIRS
    include
  CATKIN_DEPENDS)

include_directories(
  include/apriltags
  include/apriltags/common
)

add_library(${PROJECT_NAME} 
	src/apriltag.c
	src/apriltag_demo.c
	src/apriltag_quad_thresh.c
	src/g2d.c
	src/tag16h5.c
	src/tag25h7.c
	src/tag25h9.c
	src/tag36artoolkit.c
	src/tag36h10.c
	src/tag36h11.c
	src/common/getopt.c
	src/common/homography.c
	src/common/image_f32.c
	src/common/image_u32.c
	src/common/image_u8.c
	src/common/matd.c
	src/common/pnm.c
	src/common/string_util.c
	src/common/svd22.c
	src/common/time_util.c
	src/common/unionfind.c
	src/common/workerpool.c
	src/common/zarray.c
	src/common/zhash.c
	src/common/zmaxheap.c)