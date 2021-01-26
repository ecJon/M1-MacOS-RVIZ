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
RUN apt-get install -y ros-melodic-teleop-twist-keyboard
RUN apt-get install -y ros-melodic-laser-proc
RUN apt-get install -y ros-melodic-rgbd-launch
RUN apt-get install -y ros-melodic-depthimage-to-laserscan
RUN apt-get install -y ros-melodic-rosserial-arduino
RUN apt-get install -y ros-melodic-rosserial-python
RUN apt-get install -y ros-melodic-rosserial-server
RUN apt-get install -y ros-melodic-rosserial-client
RUN apt-get install -y ros-melodic-rosserial-msgs
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
RUN apt-get install -y bash
RUN apt-get install -y fluxbox
RUN apt-get install -y git
RUN apt-get install -y net-tools
RUN apt-get install -y novnc
RUN apt-get install -y supervisor
RUN apt-get install -y x11vnc
RUN apt-get install -y xterm
RUN apt-get install -y xvfb
RUN mkdir -p /root/catkin_ws
WORKDIR /root/catkin_ws
RUN /bin/bash -c "source /opt/ros/melodic/setup.bash"
RUN echo "source /opt/ros/melodic/setup.sh" >> /root/.bashrc
WORKDIR /root/catkin_ws
ENV HOME=/root \
    DEBIAN_FRONTEND=noninteractive \
    LANG=en_US.UTF-8 \
    LANGUAGE=en_US.UTF-8 \
    LC_ALL=C.UTF-8 \
    DISPLAY=:0.0 \
    DISPLAY_WIDTH=1024 \
    DISPLAY_HEIGHT=768 \
    RUN_XTERM=yes \
    RUN_FLUXBOX=yes \
    ROS_MASTER_URI=http://172.16.0.240:11311 \
    ROS_HOSTNAME=ros
COPY . /app
CMD ["/app/entrypoint.sh"]
EXPOSE 8080
