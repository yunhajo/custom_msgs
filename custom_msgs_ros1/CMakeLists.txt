cmake_minimum_required(VERSION 3.0.2)
project(custom_msgs)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  message_runtime
  roscpp
  rospy
  std_msgs
  geometry_msgs
  std_srvs
  message_filters
)

## Declare the service files to be built
add_service_files(
  DIRECTORY
    srv
  FILES
    SetBoundingBox.srv
)

generate_messages(
  DEPENDENCIES
    std_msgs
    geometry_msgs
    std_srvs
)

catkin_package(
  CATKIN_DEPENDS
  message_runtime
  std_msgs
  geometry_msgs
  std_srvs
)
