# Custom data sets Licence-Plate-Detection-using-YOLO-V8  + Raspberry Pi 

- The main steps involved:
* <> Data logistics
* <> Training the data
* <> Optimizing the model
* <> Integrating with RPI

## Data Sources:
- There are two datasets that you can use:

1. [390 images][def]
2. [1001 images][def2]

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

- Use whatever images you have to test the model 

* video

```
source = 'directory'
```

- After training is done, follow the directory to see the test results.

```
Speed: 0.2ms pre-process, 2.8ms inference, 0.0ms loss, 3.6ms post-process per image
Saving runs/detect/train/predictions.json...
Results saved to runs/detect/train
```



- Further studies,

[Ultralytics Official Link][def3]


[def]: https://universe.roboflow.com/mochoye/license-plate-detector-ogxxg
[def2]: https://universe.roboflow.com/playground-wxriu/kenyan-number-plate-detection
[def3]: https://docs.ultralytics.com/tasks/detect/#models
