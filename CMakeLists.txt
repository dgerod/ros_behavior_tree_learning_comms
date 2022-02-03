cmake_minimum_required(VERSION 2.8.3)
project(ros_behavior_tree_learning_comms)

find_package(catkin REQUIRED COMPONENTS
  rospy message_generation std_msgs
)

add_message_files(FILES
    State.msg
    NextGeneration.msg
    PopBehaviorTree.msg
    PushFitness.msg
)

add_service_files(FILES
    GpInteractiveCtrl.srv
)

catkin_python_setup()

generate_messages(DEPENDENCIES
    std_msgs
)

catkin_package(
  LIBRARIES ${PROJECT_NAME}
  CATKIN_DEPENDS rospy message_runtime std_msgs
)
