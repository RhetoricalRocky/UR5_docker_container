Website: https://github.com/UniversalRobots/Universal_Robots_ROS_Driver/tree/master?tab=readme-ov-file#extract-calibration-information

Connect ethernet cable to robot dont go on MIR wifi though stay on eduroam
robot ip = 192.168.12.52 or 192.168.12.251      internal ip 10.0.023


run container, first step:

	$ roslaunch ur_calibration calibration_correction.launch \
	  robot_ip:=<robot_ip> target_filename:="${HOME}/my_robot_calibration.yaml"

new container

	$ roslaunch ur_robot_driver <robot_type>_bringup.launch robot_ip:=192.168.12.52

new container
	** need to download docker file download did not work
	/scaled_pos_joint_traj_controller/follow_joint_trajectory

	rosrun rqt_joint_trajectory_controller rqt_joint_trajectory_controller

new container Moveit (should launch and be in the same pose as actual robot 
	
	roslaunch ur5e_moveit_config moveit_planning_execution.launch
	roslaunch ur5e_moveit_config moveit_rviz.launch rviz_config:=$(rospack find ur5e_moveit_config)/launch/moveit.rviz
	
On the UR5 launch External_control_node (currently stuck as it gives error connection could not be established: network is unreachable)
this needs to work for the controller to appear in joint_trajectory_controller