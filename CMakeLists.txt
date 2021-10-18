cmake_minimum_required(VERSION 2.9)
project(edith_msgs)

find_package(catkin REQUIRED  
rospy
std_msgs
actionlib_msgs
message_generation
geometry_msgs
)

 add_action_files(
   DIRECTORY action
   FILES
   Id.action
 )

add_service_files(
  DIRECTORY srv
  FILES
  Id.srv
  SparseCN.srv
)

add_message_files(FILES
   Plane.msg
   Table.msg
   TableViewpoints.msg
)


 generate_messages(
   DEPENDENCIES
   std_msgs  
   actionlib_msgs
   geometry_msgs
 )

catkin_package( CATKIN_DEPENDS actionlib_msgs std_msgs message_runtime )
include_directories()
