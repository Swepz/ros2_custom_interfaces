cmake_minimum_required(VERSION 3.8)
project(cpp_pubsub)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(custom_intf REQUIRED)                      # CHANGE

add_executable(talker src/publisher.cpp)
ament_target_dependencies(talker rclcpp custom_intf)    # CHANGE

add_executable(listener src/subscriber.cpp)
ament_target_dependencies(listener rclcpp custom_intf)  # CHANGE

install(TARGETS
  talker
  listener
  DESTINATION lib/${PROJECT_NAME})

ament_package()
