cmake_minimum_required(VERSION 2.8.3)
project(pr_msgs)


find_package(catkin REQUIRED COMPONENTS
	std_msgs
	sensor_msgs
	geometry_msgs
	actionlib_msgs
	message_generation
)

add_message_files(FILES
Action.msg
AppletState.msg
DefineLocation.msg
ForceRead.msg
HandOff.msg
MaglevFeedback.msg
MaglevSense.msg
NameTypeValue.msg
ObjectPose.msg
ObjectPoseList.msg
OccGrid3D.msg
PixelCoordinate.msg
PixelCoordinateList.msg
QR.msg
RailsState.msg
RotatedLaserScan.msg
Trimesh.msg
Vector3D.msg
WAMJointState.msg
oldAppletCommand.msg
oldAppletState.msg
)
add_service_files(FILES
AppletCommand.srv
ArmConfigCheck.srv
AskUser.srv
Enable.srv
Idle.srv
ResumeTrajectory.srv
)
add_action_files(FILES Signal.action herb.action)
generate_messages(DEPENDENCIES
	std_msgs
	sensor_msgs
	geometry_msgs
	actionlib_msgs
)

catkin_package(
  CATKIN_DEPENDS 
	std_msgs
	sensor_msgs
	geometry_msgs
	actionlib_msgs
	message_runtime
)
