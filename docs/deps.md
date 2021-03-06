# [ContactDB: Analyzing and Predicting Grasp Contact via Thermal Imaging](https://contactdb.cc.gatech.edu)
# Dependencies
1. Download [this fork](https://github.com/samarth-robo/Open3D/tree/surface_normals_for_colormapping) of Open3D. Make sure to get the `surface_normals_for_colormapping` branch. Compile it from source ([instructions](http://www.open3d.org/docs/compilation.html)).
2. Install [ROS Kinetic Kame](http://wiki.ros.org/kinetic/Installation) (the `ros-kinetic-desktop-full` version).
3. `sudo apt-get install python-qt4 python-pip ros-kinetic-ar-track-alvar ros-kinetic-camera-info-manager-py`
4. `pip install -r requirements.txt`
5. Download and set up [ip_basic](https://github.com/kujason/ip_basic) for depth map hole filling, and add it to the `PYTHONPATH` environment variable.

Check that `#include <pcl/registration/boost.h>` is included in PCL's header file `ROOT/registration/warp_point_rigid.h`.

## Installing Horus (only needed if you want to record your own data)
We use the [Ciclop 3D scanner from CowTech](https://www.cowtechengineering.com/3d-scanners) as a turntable for recording data, which is operated by the [Horus](https://horus.readthedocs.io/) software.
1. Remove system OpenCV: `sudo apt-get remove libopencv-dev && sudo apt-get autoremove`. This does not remove ROS OpenCV.

2. Install dependencies:
```
sudo apt-get install python-serial python-opengl python-pyglet python-numpy python-scipy python-matplotlib
sudo apt-get install python-wxgtk3.0
sudo apt-get install avrdude v4l-utils
```
Taken from [here](https://github.com/LibreScanner/horus/blob/develop/doc/development/ubuntu.md).

3. `sudo add-apt-repository ppa:bqlabs/horus-dev && sudo apt-get update`

4. `sudo apt-get install python-opencv` - this installs a modified version of OpenCV from the `horus-dev` PPA for use with Horus. It will not interfere with ROS OpenCV 

6. `sudo apt-get install horus`

7. Permissions (log out and log in afterwards):
```
sudo usermod -a -G dialout $USER
sudo usermod -a -G tty $USER
```

## Setting up the turntable
Following the [instructions](http://media.wix.com/ugd/ed8e91_d1173069b4cc4e569961f77c45803b0c.pdf), you will need to open up Horus and upload firmware to the Arduino on the first time. Once this is done, the code in this repository can directly connect to the turntable and control it.

Here are the things I had to do to get it to work:
- Use Windows for the first firmware uploading step
- Even though the instructions mention setting the baud rate to 115200, I found that that did not work on the first try. Instead, I had to select 9600, upload firmware, select the next higher baud rate, upload the firmware, and so on and re-upload at 115200. Now, the firmware will successfully upload and work.
