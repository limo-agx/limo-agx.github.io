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

    # install dependencies
    cd ~/catkin_ws/
    rosdep install --from-paths src --ignore-src -y

    # build everything
    catkin_make