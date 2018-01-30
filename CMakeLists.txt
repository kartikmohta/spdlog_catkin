cmake_minimum_required(VERSION 2.8.12)
project(spdlog_catkin)

find_package(catkin REQUIRED)

include(cmake/spdlog_catkin-extras.cmake)

catkin_package(
  INCLUDE_DIRS spdlog/include
  CFG_EXTRAS ${PROJECT_NAME}-extras.cmake
)

# install headers
install(
  DIRECTORY "spdlog/include/"
  DESTINATION ${CATKIN_GLOBAL_INCLUDE_DESTINATION}
  FILES_MATCHING
  PATTERN "*.h"
  PATTERN "*.hpp"
  PATTERN "*.hh"
  PATTERN "*.cc"
)
