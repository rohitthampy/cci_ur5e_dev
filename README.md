## Requirements

- A machine running Ubuntu Linux
- Visual Studio Code with Dev Containers extension
- Docker Engine or Docker Desktop

## How to use this Dev Container

1) Make sure you meet all the requirements.
2) clone this repository using the command: `git clone https://github.com/rohitthampy/cci_turtlebot4_dev.git`
3) Open vscode and then open the `cci_ur5e_dev` folder.
4) Open the command pallet in vscode and search for "Reopen in Container" and hit enter.
5) If everything goes well, the container should start without any errors. On the bottom left corner, you should also see the container's name, which is `cci ur5e`.

## Setting up container to work with physical ur5e
1) Make sure your machine and the ur5e are connected to the same network. Details about connecting your machine to the robot are given here: [https://wiki.cci.arts.ac.uk/books/robotics-lab/page/using-ur5e-with-2f-85-adaptive-gripper#bkmrk-establishing-connect]


To test if the setup has worked, run the command `ros2 topic list` and if everything works, you should see a list of ros2 topics from the turtlebot4.

