cmake_minimum_required(VERSION 3.0.2)
project(hello_f)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  message_generation
)

 add_message_files(
   FILES 
   motor_control_msg.msg
   )

catkin_package(
  #INCLUDE_DIRS include
  #LIBRARIES hospital
  #CATKIN_DEPENDS roscpp rospy std_msgs
  #DEPENDS system_lib
CATKIN_DEPENDS message_runtime
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
  src/motor.py src/joystick.py
   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
 )
