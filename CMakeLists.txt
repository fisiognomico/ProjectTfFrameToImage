cmake_minimum_required(VERSION 2.8.3)
project(learning_image_geometry)

#Personal configuration, please check where is opencv-config.cmake
#on your machine
set(OpenCV_DIR /opt/ros/kinetic/share/OpenCV-3.1.0-dev)
find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_geometry
  image_transport
  image_view
  sensor_msgs         #Added from the original CMake file
  #opencv2            #Commented, probably not supported
  OpenCV
  tf
)


###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES learning_image_geometry
#  CATKIN_DEPENDS cv_bridge image_geometry image_transport image_view opencv2 tf
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
# include_directories(include)
include_directories(
  ${catkin_INCLUDE_DIRS}
  ${OpenCV_INCLUDE_DIRS}
)

## Modified from the original tutorial in order to work with catkin_make
add_executable(draw_frames draw_frames.cpp)
