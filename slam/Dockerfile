FROM cristidragomir97/ros-hectorslam:latest
ENV QT_QPA_PLATFORM offscreen

COPY mapping_rplidar.launch /root/catkin_ws/src/HectorSlamForRplidar/hector_mapping/launch/mapping_rplidar.launch
COPY tutorial.launch /root/catkin_ws/src/HectorSlamForRplidar/hector_slam_launch/launch/tutorial.launch

CMD sleep infinity 
#CMD . /opt/ros/noetic/setup.sh \
#    && . /root/catkin_ws/devel/setup.sh \
#    && roslaunch hector_slam_launch tutorial.launch