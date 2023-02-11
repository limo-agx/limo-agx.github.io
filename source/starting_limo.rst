Limo Startup
============

Connect to the Limo
-------------------

.. code-block:: bash

    ssh agilex@<limo_IP>

Once in the Limo, you can start up the robot driver, lidar, and stereo camera with

.. code-block:: bash

    roslaunch limo_bringup limo_start.launch 

To be able to disconnect from the robot after starting the software and have it keep running, check out `Screen <https://www.geeksforgeeks.org/screen-command-in-linux-with-examples/>`_

Once the robot is up and running, make sure to look at :doc:`Networking <networking>` to remotely monitor and control the robot

Automatic Startup
-----------------

If you are always working with ROS and want the ROS software to start automatically, the `robot_upstart` package can handle that.  First, install it in case it isn't already

.. code-block:: bash

    sudo apt install ros-melodic-robot-upstart

Then, make sure your workspace is sourced properly.  Check out *Sourcing Your Workspace* under :doc:`Factory Reset <factory_reset>`

words and stuff