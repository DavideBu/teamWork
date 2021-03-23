# UPDATED REPORT 
Sono riuscito a superare l'errore legato a cv-bridge.
E sono arrivato finalmente al momento di esecuzione con ROS.
Qui però ricominciano i problemi:
La documentazione di DXSLAM_ROS dice:

### Run
Only for DXSLAM - Run `feature_extraction/feature_extraction_node.py` from [deep_features](https://github.com/cedrusx/deep_features) to extract and publish features for images on a given topic:
```
cd YOUR_CATKIN_WS
. devel/setup.bash
rosrun feature_extraction feature_extraction_node.py [PARAMS]
```

And launch dxslam_ros in another terminal, for example.......

### Il problema
Il mio problema è nell'esecuzione di feature extraction:
![new_error](https://github.com/DavideBu/teamWork/blob/main/new_error.PNG)

Penso che il problema sia legato al modello di Tensorflow ma credo anche di non aver sbagliato niente nel build di Deep Features. 
Ho due idee di quale possa essere il problema:
1) Non ho mai runnato feature extraction. Citando la documentazione di deep_features:
### Feature extraction
Start the feature extraction node, which will subscribe to one or more image topic(s) and publish the extracted image features on corresponding topic(s) with `/features` suffix.

With OpenVINO model:
```
. /opt/intel/openvino/bin/setupvars.sh
. YOUR_PATH_TO_CATKIN_WS/devel/setup.bash
rosrun feature_extraction feature_extraction_node.py _topics:=/YOUR_CAMERA_TOPIC _net:=hfnet_vino _model_path:=YOUR_PATH_TO_MODEL_FOLDER
```

With TensorFlow model:
```
. YOUR_PATH_TO_CATKIN_WS/devel/setup.bash
rosrun feature_extraction feature_extraction_node.py _topics:=/YOUR_CAMERA_TOPIC _net:=hfnet_tf _model_path:=YOUR_PATH_TO_MODEL_FOLDER
```

The `topics` param can take one or more topic names (separated by a comma), e.g. `/usb_cam/image_raw`, or `/left_cam/image_raw,/right_cam/image_raw`.

Additional params and their default values (more model-specific params are defined in the `default_config` dict in the source code):
```
_keypoint_number:=500 \
_keypoint_threshold:=0.002 \
_gui:=True \
_log_interval:=3.0 \
```

Io questo non l'ho mai fatto perché non so come creare quel topic. e visto che in questi comandi vedo scritto hf_net e io non ho usato niente del genere penso che il problema sia questo.

2) Qualche riga più in su quando si parla del build di deep_features ho trovato scritto questo punto:

5. Donwload one of the saved [HF-Net](https://github.com/ethz-asl/hfnet) models from the [Releases](https://github.com/cedrusx/deep_features/releases), and unzip it.

Io ho eseguito il punto, ma dato che non è spiegato in che punto unzippare, ho provato a mettere il file un po' dappertutto e ovviamente non ha funzionato.

