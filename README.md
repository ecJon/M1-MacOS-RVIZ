# [M1-MacOS-RVIZ](https://github.com/ecJon/M1-MacOS-RVIZ)
This project can run ROS and RVIZ on MacOS with M1 chip.

## Note

* This project base on docker currently,Please install docker first!

* ROS version is Melodic.

* All Dockerfiles are using chinese apt sources,Foreign friends can delete sources modify in Dockerfiles.

## Usage

1. Open a Terminal window
    * ```git clone https://github.com/ecJon/M1-MacOS-RVIZ.git```

    * ```cd M1-MacOS-RVIZ/ros-rviz-novnc-web```

    *  ```docker build . -t="340651973/ros-rviz-novnc-web:latest" # Build ros image for M1 docker (Foreign friends can docker pull 3340651973/ros-rviz-novnc-web:latest)```

    * ```docker run -it -p 8080:8080 --name ros-rviz-novnc-web 3340651973/ros-rviz-novnc-web:latest```

3. Now open address http://localhost:8080/vnc_auto.html in your Browser !And you will run any ros tool or rivz visually.

## Thanks
[@theasp](https://github.com/theasp/docker-novnc) dockerfile and config base on docker-novnc


## Open source agreement
[MIT](https://opensource.org/licenses/mit-license.php)
