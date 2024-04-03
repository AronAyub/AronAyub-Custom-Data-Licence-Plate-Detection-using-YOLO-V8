# Custom data sets Licence-Plate-Detection-using-YOLO-V8  + Raspberry Pi 

- There are three main steps:
* <> Data logistics
* <> Training the data
* <> Optimizing the model
* <> Integrating with RPI

- Open Notebook file and run the commands sequentially.
- Connect to T4 GPU under resources on the right side.

<img width="828" alt="image" src="https://github.com/Arijit1080/Licence-Plate-Detection-and-Recognition-using-YOLO-V8-EasyOCR/assets/55284959/81bc96ff-ae4b-4c56-8303-3fa98551a727">


- Under this section: edit the API Key fetched from Roboflow.

```
!pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="apikeyxxx")
project = rf.workspace("mochoye").project("license-plate-detector-ogxxg")
version = project.version(1)
dataset = version.download("yolov8")
```

- You can test your model perfomance after training:

```
 !python /content/Licence-Plate-Detection-and-Recognition-using-YOLO-V8-EasyOCR/ultralytics/yolo/v8/detect/predict.py model='/content/Licence-Plate-Detection-and-Recognition-using-YOLO-V8-EasyOCR/best.pt' source ='directory'
```
- the source can be:

* Live camera 
```
source = 0
```
* For images 
```
source = 'directory.png'
```
* video

```
source = 'directory'
```






