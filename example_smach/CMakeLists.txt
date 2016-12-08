cmake_minimum_required(VERSION 2.8.3)
project(example_smach)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  message_generation
)


 ##Generate messages in the 'msg' folder
 add_message_files(
   FILES
   Num.msg
 )

## Generate services in the 'srv' folder
 add_service_files(
   FILES
   AddTwoInts.srv
   AddThreeInts.srv
   AddFourInts.srv
 )



## Generate added messages and services with any dependencies listed here
 generate_messages(
   DEPENDENCIES
   std_msgs
 )


catkin_package(
   CATKIN_DEPENDS message_runtime
#  DEPENDS system_lib
)

#


