FROM ros:melodic-ros-core-bionic

RUN cat /etc/apt/sources.list|sed "s/ports\.ubuntu\.com/mirrors\.tuna\.tsinghua\.edu\.cn/g" > /etc/apt/sources.list.tmp
RUN cat /etc/apt/sources.list.tmp > /etc/apt/sources.list
RUN rm /etc/apt/sources.list.tmp
RUN cat /etc/apt/sources.list.d/ros1-latest.list|sed  "s/packages\.ros\.org/mirrors\.tuna\.tsinghua\.edu\.cn/g" > /etc/apt/sources.list.d/ros1-latest.list.tmp
RUN cat /etc/apt/sources.list.d/ros1-latest.list.tmp > /etc/apt/sources.list.d/ros1-latest.list
RUN rm /etc/apt/sources.list.d/ros1-latest.list.tmp
RUN apt-get -y update
RUN apt-get install -y ros-melodic-desktop-full
RUN apt-get install -y iputils-ping
RUN apt-get install -y net-tools
RUN apt-get install -y wget
RUN apt-get install -y ros-melodic-joy
RUN apt-get install -y ros-melodic-teleop-twist-joy
RUN apt-get install -y ros-melodic-teleop-twist-keyboard \ 
    ros-melodic-laser-proc
RUN apt-get install -y ros-melodic-rgbd-launch
RUN apt-get install -y ros-melodic-depthimage-to-laserscan
RUN apt-get install -y ros-melodic-rosserial-arduino \ 
    ros-melodic-rosserial-python
RUN apt-get install -y ros-melodic-rosserial-server \ 
    ros-melodic-rosserial-client \ 
    ros-melodic-rosserial-msgs
RUN apt-get install -y ros-melodic-amcl
RUN apt-get install -y ros-melodic-map-server
RUN apt-get install -y ros-melodic-move-base
RUN apt-get install -y ros-melodic-urdf
RUN apt-get install -y ros-melodic-xacro
RUN apt-get install -y ros-melodic-compressed-image-transport
RUN apt-get install -y ros-melodic-rqt-image-view
RUN apt-get install -y ros-melodic-gmapping
RUN apt-get install -y ros-melodic-navigation
RUN apt-get install -y ros-melodic-interactive-markers
RUN mkdir -p /root/catkin_ws/src
WORKDIR /root/catkin_ws
RUN /bin/bash -c "source /opt/ros/melodic/setup.bash"
RUN echo "source /opt/ros/melodic/setup.sh" >> /root/.bashrc
RUN echo "source /root/catkin_ws/devel/setup.bash" >> /root/.bashrc
WORKDIR /root/catkin_ws/src
