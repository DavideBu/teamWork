# UPDATED REPORT 
Sono riuscito a superare l'errore legato a cv-bridge.
E sono arrivato finalmente al momento di esecuzione con ROS.
Qui però ricominciano i problemi:
La documentazione di DXSLAM_ROS dice:

## The issue

Esso è legato all'esecuzione dell'ultimo comando della documentazione di DXSLAM_ROS:

### Documentazione DXSLAM_ROS
Only for DXSLAM - Run `feature_extraction/feature_extraction_node.py` from [deep_features](https://github.com/cedrusx/deep_features) to extract and publish features for images on a given topic:
```
cd YOUR_CATKIN_WS
. devel/setup.bash
rosrun feature_extraction feature_extraction_node.py [PARAMS]
```
And launch dxslam_ros in another terminal, for example:
```
cd YOUR_CATKIN_WS
. devel/setup.bash
roslaunch dxslam_ros rgbd.launch slam:=dxslam camera:=d400 pub_tf_child_frame:=base_link
```

Then play your ROS bag or launch `realsense_ros` to provide a live stream.
The arguments above are configurated for the [OpenLORIS-Scene](https://lifelong-robotic-vision.github.io/dataset/scene) datasets. You may need to change them if using other data.

When succeeded, you should be able to see live tracking results in the ORB_SLAM2 GUI, and properly maintained ROS tf and pose topics with RViz or `rqt_tf_tree`.


Il run di feature_extraction funziona:


![cattura](https://github.com/DavideBu/teamWork/blob/main/Cattura.PNG)

ma il secondo comando sul lancio di dxslam_ros mi da il seguente errore:

![error](https://github.com/DavideBu/teamWork/blob/main/d.PNG)

Penso che il problema sia legato a una mia mancanza di conoscenza su ROS e che possa essere risolto velocemente con l'affiancamento di un membro senior.
