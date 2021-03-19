# REPORT DXSLAM ROS
```
cd YOUR_CATKIN_WS/src/
git clone https://github.com/cedrusx/dxslam_ros
git clone https://github.com/cedrusx/deep_features
git clone https://github.com/ivipsourcecode/dxslam
```
Questi comandi sono stati eseguiti senza alcun problema.
Successivamente la documentazione dice di buildare dxslam e/o ORB SLAM 2, noi abbiamo usato solamente dxslam e quindi ho buildato solo quest’ultimo.
```
cd dxslam
./build.sh
cd ..
```
Il problema principale sopraggiunge quando si arriva all’esecuzione di questi comandi:
```
cd YOUR_CATKIN_WS
. /opt/ros/VERSION/setup.bash
catkin build  # OR catkin_make
```
L’errore è nel catkin build (foto allegata)
