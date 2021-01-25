# M1-MacOS-RVIZ
This project can run ROS and RVIZ on MacOS with M1 chip.

# Usage

1. Open a Terminal window
    * ```git clone https://github.com/ecJon/M1-MacOS-RVIZ.git```

    * ```cd M1-MacOS-RVIZ/ros-melodic-desktop-full```

    *  ```docker build . -t="ros:v0.0.1" # Build ros image for M1 docker```

    * ```cd ../novnc```

    * ```docker build . -t="novnc:v0.0.1" # Build novnc image for M1 docker```

    * ```cd ..```

    * ```docker-compose up```

2. Open the second Terminal window
    * ```docker exec -it M1-MacOS-RVIZ_ros_1 /bin/bash```

3. Now you can run any ros tools in the second Terminal windows and visual windows will display in novnc !For example:
    * ```rviz -d some.rviz```
    And Then
    * Open Browser with address http://localhost:8080

# Note

* This project base on docker currently,Please install docker first!

* ROS version is Melodic.

* All Dockerfiles are using chinese apt sources,Foreign friends can delete sources modify in Dockerfiles.

# Thanks
[@theasp](https://github.com/theasp/docker-novnc) Novnc dockerfile and config base on docker-novnc

[@nebocleaning](https://github.com/nebocleaning/mac-ros) ros dockerfile and docker-compos base on mac-ros


# Open source agreement
[MIT](https://opensource.org/licenses/mit-license.php)
