
<div align="center" markdown>
<img src="https://github.com/user-attachments/assets/37456854-3675-4b86-8c2c-35e6e8daf352"/>  

# Train YOLOv8 | v9 | v10 | v11

<p align="center">
  <a href="#Overview">Overview</a> •
  <a href="#How-To-Run">How To Run</a> •
  <a href="#App-Specifications">App Specifications</a> •
  <a href="#How-To-Use-Your-Trained-Model-Outside-Supervisely">How To Use Your Trained Model Outside Supervisely</a> •
  <a href="#Related-apps">Related apps</a> •
  <a href="#Screenshot">Screenshot</a> •
  <a href="#Acknowledgment">Acknowledgment</a>
</p>

[![](https://img.shields.io/badge/supervisely-ecosystem-brightgreen)](https://ecosystem.supervisely.com/apps/supervisely-ecosystem/yolov8/train)
[![](https://img.shields.io/badge/slack-chat-green.svg?logo=slack)](https://supervisely.com/slack)
![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/supervisely-ecosystem/yolov8)
[![views](https://app.supervisely.com/img/badges/views/supervisely-ecosystem/yolov8/train.png)](https://supervisely.com)
[![runs](https://app.supervisely.com/img/badges/runs/supervisely-ecosystem/yolov8/train.png)](https://supervisely.com)

</div>

# Overview

🔥 Application now supports different checkpoints from YOLOv8, YOLOv9, YOLOv10 and YOLOv11 architectures.

YOLOv8 is a powerful neural network architecture that provides both decent accuracy of predictions and high speed of inference. In comparison to YOLOv5, YOLOv8 uses an anchor-free head (allowing to speed up the non-max suppression (NMS) process), a new backbone, and new loss functions.

YOLOv9 builds on the advancements of YOLOv8 by further improving the model's performance and efficiency. It incorporates extended feature extraction techniques, advanced loss functions and optimized training processes for better accuracy and faster inference times.

YOLOv10 introduces consistent dual assignments for NMS-free training and adopts a holistic efficiency-accuracy-driven model design strategy.

YOLOv11, the latest iteration in the YOLO series, continues the trend of balancing accuracy and efficiency with significant advancements. It introduces a hybrid architecture that combines the strengths of anchor-free and anchor-based methods, allowing the model to adapt dynamically based on the characteristics of the input data.

This app allows you to train models using YOLOv8, YOLOv9, YOLOv10 and YOLOv11 on a selected dataset. You can define model checkpoints, data split methods, training hyperparameters, data augmentation, and many other features related to model training. The app supports both models pretrained on COCO or Open Images V7 dataset and models trained on custom datasets. Supported task types include object detection, instance segmentation, and pose estimation.

**Export to ONNX / TensorRT:**

You can now export your trained model to ONNX or TensorRT formats after training. Exported model can be deployed in various frameworks and used for efficient inference on edge devices.
- **TensorRT** is a very optimized environment for Nvidia GPU devices. TensorRT can significantly boost the inference speed. Additionally, you can select *FP16 mode* to reduce GPU memory usage and further increase speed. Usually, the accuracy of predictions remains the same.
- **ONNXRuntime** can speed up inference on some CPU and GPU devices.

---

**Updates:**

- v1.0.60 - Extended support for Open Images V7 and YOLOv9 checkpoints.
- v1.0.63 - Added multiclass pose estimation support.
- v1.0.73 - Enabled support for freezing layers to allow more flexible model training.
- v1.0.87 - Integrated the YOLOv10 checkpoints.
- v1.1.8  - Added model benchmark evaluation after training.
- v1.1.9  - Added export to ONNX and TesnorRT.
- v1.1.20 - Integrated the YOLOv11 checkpoints

🔥🔥🔥 Check out our [youtube tutorial](https://youtu.be/Rsr8xWJ6s9I) and the [complete guide in our blog](https://supervisely.com/blog/train-yolov8-on-custom-data-no-code/):   

<a href="https://youtu.be/Rsr8xWJ6s9I" target="_blank"><img src="https://github.com/supervisely-ecosystem/yolov8/assets/12828725/beb89aaf-94cb-4044-84f1-33f2f17bbe7e"/></a>

# How To Run

Select images project, select GPU device in "Agent" field, click on `RUN` button:

https://user-images.githubusercontent.com/91027877/249008934-293b3176-d5f3-4edb-9816-15bffd3bb869.mp4

# App Specifications

Please, remember that pose estimation task requires target object to be labeled by both graphs (keypoints) and bounding boxes (rectangles). For better experience, please, use [object binding](https://developer.supervisely.com/advanced-user-guide/objects-binding) to speed up the process of matching graphs and bounding boxes. If there are no binding keys in annotations, approach based on euclidian distance between centers of graphs and boxes will be used to match them with each other.

# How To Use Your Trained Model Outside Supervisely

You can use your trained models outside Supervisely platform without any dependencies on Supervisely SDK. See this [Jupyter Notebook](https://github.com/supervisely-ecosystem/yolov8/blob/master/outside_supervisely/inference_outside_supervisely.ipynb) for details. If you also want to apply the model to a video, using the same deepsort algorithm, you can refer to the official YOLO documentation [here](https://docs.ultralytics.com/modes/track/#tracker-selection).

# Related apps

- [Export to YOLOv8 format](https://ecosystem.supervisely.com/apps/export-to-yolov8) - app allows to transform data from Supervisely format to YOLOv8 format.   
    <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/export-to-yolov8" src="https://github.com/supervisely-ecosystem/yolov8/assets/115161827/01d6658f-11c3-40a3-8ff5-100a27fa1480" height="70px" margin-bottom="20px"/>  

- [Serve YOLOv8 | v9 | v10 | v11](https://ecosystem.supervisely.com/apps/yolov8/serve) - app allows to deploy YOLOv8 | v9 | v10 | v11 model as REST API service.   
    <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/yolov8/serve" src="https://github.com/supervisely-ecosystem/yolov8/assets/115161827/721f5344-013c-4466-bc05-88cc3efef5ca" height="70px" margin-bottom="20px"/>

- [NN Image Labeling](https://ecosystem.supervisely.com/apps/supervisely-ecosystem%252Fnn-image-labeling%252Fannotation-tool) - integrate any deployed NN to Supervisely Image Labeling UI. Configure inference settings and model output classes. Press `Apply` button (or use hotkey) and detections with their confidences will immediately appear on the image.   
    <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/nn-image-labeling/annotation-tool" src="https://i.imgur.com/hYEucNt.png" height="70px" margin-bottom="20px"/>

- [Apply NN to Videos Project](https://ecosystem.supervisely.com/apps/apply-nn-to-videos-project) - app allows to label your videos using served Supervisely models.  
  <img data-key="sly-module-link" data-module-slug="supervisely-ecosystem/apply-nn-to-videos-project" src="https://imgur.com/LDo8K1A.png" height="70px" margin-bottom="20px" />
  
# Screenshot

![train_yolov8_full_screen](https://user-images.githubusercontent.com/91027877/250972249-7d27d601-3aa8-4614-bf11-d4d71a425602.png)


# Acknowledgment

This app is based on the great work `YOLOv8` ([github](https://github.com/ultralytics/ultralytics)). ![GitHub Org's stars](https://img.shields.io/github/stars/ultralytics/ultralytics?style=social)
