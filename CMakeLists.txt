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
  det_and_compare_obj.srv
  extract_permanent_objects.srv
)

add_message_files(FILES
   Plane.msg
   Table.msg
   TableViewpoints.msg
   CandidateObject.msg
   ObjectMatch.msg
   Object.msg
   ObjectStateClass.msg
)


 generate_messages(
   DEPENDENCIES
   std_msgs  
   actionlib_msgs
   geometry_msgs
   sensor_msgs
 )

catkin_package( CATKIN_DEPENDS actionlib_msgs std_msgs sensor_msgs message_runtime )
include_directories()
