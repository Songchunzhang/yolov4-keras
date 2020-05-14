## YOLOV4：You Only Look Once目标检测模型在Keras当中的实现
---

### 所需环境
tensorflow-gpu==1.13.1  
keras==2.1.5  

### 注意事项
代码中的yolo4_weights.h5是基于608x608的图片训练的，但是由于显存原因。我将代码中的图片大小修改成了416x416。有需要的可以修改回来。 代码中的默认anchors是基于608x608的图片的。   

### 训练步骤
1、本文使用VOC格式进行训练。  
2、训练前将标签文件放在VOCdevkit文件夹下的VOC2007文件夹下的Annotation中。  
3、训练前将图片文件放在VOCdevkit文件夹下的VOC2007文件夹下的JPEGImages中。  
4、在训练前利用voc2yolo3.py文件生成对应的txt。  
5、再运行根目录下的voc_annotation.py，运行前需要将classes改成你自己的classes。  
```python
classes = ["aeroplane", "bicycle", "bird", "boat", "bottle", "bus", "car", "cat", "chair", "cow", "diningtable", "dog", "horse", "motorbike", "person", "pottedplant", "sheep", "sofa", "train", "tvmonitor"]
```
6、就会生成对应的2007_train.txt，每一行对应其图片位置及其真实框的位置。  
7、在训练前需要修改model_data里面的voc_classes.txt文件，需要将classes改成你自己的classes。  
8、运行train.py即可开始训练。

### Reference
https://github.com/qqwweee/keras-yolo3/
https://github.com/Cartucho/mAP
https://github.com/Ma-Dan/keras-yolo4
