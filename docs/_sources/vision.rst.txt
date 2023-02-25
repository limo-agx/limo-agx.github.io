Vision
======

The Limo is equipped with a Jetson Nano computer.  This PC is designed for doing advanced parallel processing such as Deep Learning.  We're going to use these capabilities to find objects and better understand the environment around the robot

Getting the Vision Package
--------------------------

In your workspace, you will need to clone and build the vision package.  

.. note::
    
    You will need access to the internet the first time you build these packages

.. code-block:: bash

    git clone --recursive http://github.com/limo-agx/limo_vision.git
    cd ..
    catkin_make
    source devel/setup.bash

Once the package is built, it can be launched using the command below:

.. code-block:: bash

    roslaunch limo_vision darknet_ros.launch

What this will do is subscribe to the video stream from the stereo camera.  On each frame of the video, it will feed it through a pre-trained YOLO network and output the results.  You can subscribe to the resulting image to see what objects its detected using this command.

If you are using a real robot or simulating on another computer and you want to monitor the detection network, make sure to look at the :doc:`Networking <networking>` section

.. code-block:: bash

    rosrun image_view image_view image:=/darknet_ros/detection_image

.. image:: images/yolo.png

If you are wanting to use your own detection network, look at the documentation `Here <https://github.com/leggedrobotics/darknet_ros>`_
