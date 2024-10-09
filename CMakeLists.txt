cmake_minimum_required(VERSION 3.5)
project(ackermann_msgs)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(Boost REQUIRED)
find_package(builtin_interfaces REQUIRED)

# Define the messages
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/AckermannDrive.msg"
  "msg/AckermannDriveStamped.msg"
  DEPENDENCIES std_msgs builtin_interfaces
  ADD_LINTER_TESTS
)

ament_export_dependencies(rosidl_default_runtime std_msgs builtin_interfaces Boost)
ament_package()
