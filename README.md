READMe PCB Recycling Project

### Below is a list of all the requirements for the project :

- Computer running with a version of Ubuntu compatible with ROS2 Hawksbill, we recommend Ubuntu 22.04 that can be downloaded here :

	Image : https://releases.ubuntu.com/jammy/
	Installation tutorial : https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview
	Flashing software : https://etcher.balena.io/

- Your computer should have ROS2 Hawksbill installed, you can find a tutorial on how to install it here :

	Installation tutorial : https://docs.ros.org/en/humble/Installation.html
	Note : Make sure to install the "deb packages" not the "binary archive"

- A robot compatible with ROS2 commands, such as Tiago from PalRobotics

	Note : The robot should have a way to connect itself to your desktop computer (wifi or ethernet)

### Packages related to ROS2 functionnalities :

First to build packages you will need to use colcon, which you can follow an installation tutorial here :

	Colcon installation : https://docs.ros.org/en/foxy/Tutorials/Beginner-Client-Libraries/Colcon-Tutorial.html#install-colcon

Once ROS2 is installed on your desktop computer with colcon you will need to install a few differents packages to make sure all your nodes will run correctly, those packages are the following :

	> rclpy 
	> geometry_msgs
	> example_interfaces
	> pip pynput
	Note : a "package.xml" file can be found in the ressources folder, this file contain everything you need to install all those packages.

### Creating and Editing nodes in ROS2 :

In this project the code for the arm controller node is already written and ready to use, you only to put it into a functionnal python executable node.
For node creation and editing we recommend following these videos if you're unfamiliar with ROS2 :

	ROS2 crash course : https://www.youtube.com/watch?v=0aPbWsyENA8&list=PLLSegLrePWgJudpPUof4-nVFHGkB62Izy

Using gedit and visualstudio you should be able to get yourself correctly configured nodes. Make sure to build the nodes once you have finished with colcon build and de not forget to source your work.

### Working processus

Once you've installed everything, you can boot up your desktop computer as well as your robot, establish a connection between the two.
Open a terminal and run your nodes, you can effectively see which nodes are running with the "rqt graph" command, you should use this to ensure everything is working as intended.

At this point you should be able to interact with the robot by giving manual inputs on your keyboard or manually triggering function calls.


### Making sure Tiago as booted up correctly :

If you want to add a layer of security after having started Tiago you can go to the following link :

	Webcommander for Tiago : https://docs.pal-robotics.com/sdk/23.12/management/webcommander.html

This webcommander allow you to see the status of Tiago's robot executable. Here you can see if something crashed or hasn't booted up properly in the log and starting tabs.

You can manually control joints to make sure there isn't a mdchanical robot side issue.

### GitHub details

The Information_Documetns folder contains PDF files relatives to the PCB recycling topic, we mainly used those to get a grasp on the subject and identify the issues with the current regulations and procedures. There is also the package.xml file mentionned earlier.

PCB_Components_Recognition_Yolo is the folder related to the AI detection of PCB components with every program used to train and test the AI on databases as well as the code responsible for creating coordinates based on photos taken with Tiago.

Tiago single arm is a folder with files gathered from pal robotics related to the startup, installation and configuration of TIAGO.

Program files is a folder containing files that are python codes for ros2 nodes that are used to control TIAGO's arm.
