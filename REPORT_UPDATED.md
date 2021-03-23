# REPORT UPDATED
Sono riuscito a superare l'errore legato a cv-bridge.
E sono arrivato finalmente al momento di esecuzione con ROS.
Qui però ricominciano i problemi:
La documentazione di DXSLAM_ROS dice:


Only for DXSLAM - Run `feature_extraction/feature_extraction_node.py` from [deep_features](https://github.com/cedrusx/deep_features) to extract and publish features for images on a given topic:
```
cd YOUR_CATKIN_WS
. devel/setup.bash
rosrun feature_extraction feature_extraction_node.py [PARAMS]
```

And launch dxslam_ros in another terminal, for example.......

# Il problema
Il mio problema è nell'esecuzione di feature extraction:
