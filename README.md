# pothole_detection_yolo
Simple pothole object detection practice using yolov12

# codes
please refer the pothole_yolov12.ipynb for more details.

## data augmentation
We use default data augmentation mode of ultralytics(scale=0.5, hsv_s=0.7, auto_augment = 'randaugment' etc...)

please see [data augmentation parameters docs](https://docs.ultralytics.com/ko/modes/train/#augmentation-settings-and-hyperparameters) for more information about augmentation parameter setting in model.train()

If you want to know how each parameter affects data augmentation and images, please see [data augmentation using Ultralytics](https://docs.ultralytics.com/ko/guides/yolo-data-augmentation/)
## training
```py
from ultralytics import YOLO
model = YOLO("yolo12n.pt")
results = model.train(data="pothole.yaml", epochs=100, imgsz=512)

# Training with custom augmentation parameters
# model.train(data="coco.yaml", epochs=100, hsv_h=0.03, hsv_s=0.6, hsv_v=0.5,shear=5.0)
```

# results

## train results
![train_results](https://github.com/minchoCoin/pothole_detection_yolo/blob/main/train/results.png)

![valid results](https://github.com/minchoCoin/pothole_detection_yolo/blob/main/train/train_batch39242.jpg)

## valid results
- valid prediction results
![valid results](https://github.com/minchoCoin/pothole_detection_yolo/blob/main/train/val_batch0_pred.jpg)

- (reference) valid true label
![valid true label](https://github.com/minchoCoin/pothole_detection_yolo/blob/main/train/val_batch0_labels.jpg)

- valid result1

![result1](https://github.com/minchoCoin/pothole_detection_yolo/blob/main/results1.png)

- valid result2

![result2](https://github.com/minchoCoin/pothole_detection_yolo/blob/main/results2.png)

# Environment
- Google Colab A100

# library
- [ultralytics](https://docs.ultralytics.com/ko)

# references
- https://docs.ultralytics.com/ko/quickstart/
- https://docs.ultralytics.com/ko/models/yolo12/#usage-examples
- https://docs.ultralytics.com/ko/modes/train/#augmentation-settings-and-hyperparameters
- https://docs.ultralytics.com/ko/guides/yolo-data-augmentation/
- https://xandroid.tistory.com/entry/yolo8-python-310-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EA%B0%9D%EC%B2%B4-%EC%9D%B8%EC%8B%9D-3-%EC%BB%A4%EC%8A%A4%ED%85%80-%EA%B0%90%EC%A7%80%ED%8F%AC%ED%8A%B8%ED%99%80
