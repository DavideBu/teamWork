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
L’errore appare quando si esegue: catkin build (foto allegata)

![error1](https://github.com/DavideBu/teamWork/blob/main/error1.png)

Il problema è nel modulo cv_bridge che nella documentazione è spiegato servire per ROS melodic o versioni precedenti.
Sembra proprio un errore nel codice.
Non so se il resto funzioni perché questo errore interrompe completamente la build.
