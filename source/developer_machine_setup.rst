Developer Machine Setup
=======================

To interact with and develop for the Limo, it helps to have a computer that can remotely monitor and interact with the Limo as well as simulate one.

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
    git clone https://github.com/limo-agx/limo_desktop.git
    git clone https://github.com/limo-agx/limo_simulator.git

    # install dependencies
    cd ~/catkin_ws/
    rosdep install --from-paths src --ignore-src -y

    # build everything
    catkin_make

If you are working with a real robot, make sure to check out the :doc:`Networking <networking>` section
