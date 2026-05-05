FROM osrf/ros:humble-desktop-full

# Add ubuntu user with same UID and GID as your host system, if it doesn't already exist
# Since Ubuntu 24.04, a non-root user is created by default with the name vscode and UID=1000
ARG USERNAME=docker-user
ARG USER_UID=1000
ARG USER_GID=$USER_UID
RUN if ! id -u $USER_UID >/dev/null 2>&1; then \
        groupadd --gid $USER_GID $USERNAME && \
        useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME; \
    fi
# Add sudo support for the non-root user
RUN apt-get update && \
    apt-get install -y sudo && \
    echo "$USERNAME ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/$USERNAME && \
    chmod 0440 /etc/sudoers.d/$USERNAME 

# Switch from root to user
USER $USERNAME

# Update all packages
RUN sudo apt update && sudo apt upgrade -y

# Installing git
RUN sudo apt install -y git

# Installing net-tools to use ifconfig and iputils for ping
RUN sudo apt install net-tools

# Installing iputils for ping
RUN sudo apt install -y iputils-ping

# Install python and pip
RUN sudo apt install -y python3-pip

# Install wget
RUN sudo apt install -y wget

# Installing low latency kernel
RUN sudo apt install -y linux-lowlatency

# Installing ur driver 
RUN sudo apt-get install -y ros-${ROS_DISTRO}-ur

# Installing ros2 control
RUN sudo apt install -y ros-${ROS_DISTRO}-ros2-control ros-${ROS_DISTRO}-ros2-controllers