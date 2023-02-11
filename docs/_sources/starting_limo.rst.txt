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

To create the startup job, run the command below

.. code-block:: bash

    rosrun robot_upstart install limo_bringup/launch/limo_start.launch
    sudo systemctl daemon-reload && sudo systemctl start limo

Now, every time you turn on your Limo, the default ROS drivers will start. 

If you don't want the ROS to startup automatically anymore, run the command below

.. code-block:: bash

    sudo systemctl disable limo