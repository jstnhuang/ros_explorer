cmake_minimum_required(VERSION 2.8.3)
project(ros_explorer)

find_package(catkin REQUIRED COMPONENTS
)
catkin_package(
)
include_directories(
  ${catkin_INCLUDE_DIRS}
)
#############
## Install ##
#############

# all install targets should use catkin DESTINATION variables
# See http://ros.org/doc/api/catkin/html/adv_user_guide/variables.html

## Mark executable scripts (Python etc.) for installation
## in contrast to setup.py, you can choose the destination
install(PROGRAMS
  scripts/ros_explorer
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}/scripts
)

## Mark executables and/or libraries for installation
# install(TARGETS rose rose_node
#   ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
#   LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
#   RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
# )

install(DIRECTORY frontend/build/es6-bundled/
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}/www
)

## Mark other files for installation (e.g. launch and bag files, etc.)
install(FILES
  launch/ros_explorer.launch
  launch/ros_explorer_websocket.launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
