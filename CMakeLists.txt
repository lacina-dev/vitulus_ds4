################################################################################
# Set minimum required version of cmake, project name and compile options
################################################################################
cmake_minimum_required(VERSION 3.0.2)
project(vitulus_ds4)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

################################################################################
# Find catkin packages and libraries for catkin and system dependencies
################################################################################
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  roslaunch
)

################################################################################
# Setup for python modules and scripts
################################################################################
# catkin_python_setup()

################################################################################
# Declare ROS messages, services and actions
################################################################################
# add_message_files(
#   FILES
# )

# generate_messages(
#   DEPENDENCIES
#   std_msgs
# )
################################################################################
# Declare ROS dynamic reconfigure parameters
################################################################################

################################################################################
# Declare catkin specific configuration to be passed to dependent projects
################################################################################
catkin_package(
  INCLUDE_DIRS
  CATKIN_DEPENDS roscpp rospy
)

################################################################################
# Build
################################################################################
# include_directories(
#   ${catkin_INCLUDE_DIRS}
# )
# )

# include_directories(
#   include/
#   ${catkin_INCLUDE_DIRS}
# )

# add_executable(${PROJECT_NAME}_node
#   src/vitulus_template.cpp
# )

# target_link_libraries(${PROJECT_NAME}_node
#   ${catkin_LIBRARIES}
# )

# add_dependencies(${PROJECT_NAME}_node
#   ${${PROJECT_NAME}_EXPORTED_TARGETS}
#   ${catkin_EXPORTED_TARGETS}
# )


################################################################################
# Install
################################################################################

install(DIRECTORY launch config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

catkin_install_python(PROGRAMS
  nodes/node_ds4
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

################################################################################
# Test
################################################################################
