Factory Reset
=============

If you are changing the SD card in your Jetson computer, or having issues with the operating system, you may need to reset the Limo computer to an initial state.

Reinsall the Operating System
-----------------------------

You will need to reinstall the operating system from scratch.  Follow the setup steps at the `Jetson Developer Support Site <https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit>`_


Install ROS
-----------

You will need to install ROS.  Follow the setup steps at the `ROS Wiki <http://wiki.ros.org/melodic/Installation/Ubuntu>`_.  Make sure to follow all of the steps so you are able to build packages and install dependencies using rosdep

Install Limo Software
-----------------------

Currently the Limo software is distributed from source and built locally.  To create and build the workspace, follow the commands below

.. code-block:: bash

    # make a workspace
    mkdir -p ~/catkin_ws/src
    cd ~/catkin_ws/src
    source /opt/ros/melodic/setup.bash
    catkin_init_workspace

    # download source code
    git clone https://github.com/limo-agx/limo.git
    git clone https://github.com/limo-agx/limo_robot.git
    git clone https://ithub.com/limo-agx/limo_desktop.git
    git clone https://github.com/orbbec/ros_astra_camera.git

    # install dependencies
    cd ~/catkin_ws/
    rosdep install --from-paths src --ignore-src -y

    # build everything
    catkin_make

.. _sourcing:
Sourcing Your Workspace
-----------------------

Once everything is setup and built, you will need to source you workspace.  This makes the software available in the terminal.

.. code-block:: bash

    source ~/catkin_ws/devel/setup.bash

The command needs to be typed in every terminal you start.  If you want it to always be sourced, you can add the line to the bottom of your ~/.bashrc file

Setup Orbbec Camera
-------------------

.. code-block:: bash

    sudo apt install libgflags-dev  ros-$ROS_DISTRO-image-geometry ros-$ROS_DISTRO-camera-info-manager\
    ros-$ROS_DISTRO-image-transport ros-$ROS_DISTRO-image-publisher libgoogle-glog-dev libusb-1.0-0-dev libeigen3-dev

.. code-block:: bash

    git clone https://github.com/libuvc/libuvc.git
    cd libuvc
    mkdir build && cd build
    cmake .. && make -j4
    sudo make install
    sudo ldconfig

