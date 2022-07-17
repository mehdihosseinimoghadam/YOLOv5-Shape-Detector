# Shape detector with YOLOv5 🚀
![picture](https://drive.google.com/uc?export=view&id=1Z3YlmPgvOyqIMxXjt7ZQeCKY8PXbEuHV)

This Package contains YOLOv5 model which has been trained over dataset of shapes (containing two classes of polygons and ellipse), model is capable of detecting two classes and counting the number of each class in a given image


# What is YOLOv5?
YOLOv5 🚀 is a family of compound-scaled object detection models trained on the COCO dataset, and includes simple functionality for Test Time Augmentation (TTA), model ensembling, hyperparameter evolution, and export to ONNX, CoreML and TFLite.


![picture](https://drive.google.com/uc?export=view&id=15iAZ1TwkVwnDpwCd_ZVIAY4WpEZj6I-R)


##### Data Set Structure 💻:

For this model I used about 700 images containing different number of ellipses and polygons which all has been labeled manually, down below you can find some of the images which used for training:

![picture](https://drive.google.com/uc?export=view&id=1l9PpEuQAuI_0gKCBO0ogPFnp2RU_iFtT)

![picture](https://drive.google.com/uc?export=view&id=1Pgxxnn9DyEL8jhw6Uvb-cyiOLnyfav7b)
##### YOLOv5 Advantages? 🏛️:
- It is about 88% smaller than YOLOv4 (27 MB vs 244 MB)
- It is about 180% faster than YOLOv4 (140 FPS vs 50 FPS)
- It is roughly as accurate as YOLOv4 on the same task (0.895 mAP vs 0.892 mAP)




[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/mehdihosseinimoghadam/YOLOv5-Shape-Detector/blob/main/shapedetector.ipynb)





Prerequisites 🧰
-------------
- `YOLOv5` 
- `Pytorch`
- `Numpy`
- `Pandas`
- `gdown`



# Accuracy 📈
For accuracy I used about 1864 images to get the number of ellipses, out of this number only 193 of images were predicted wrong with the count of ellipses.
the overall accuracy of the model was about 90%.
here is a sample of out put from the model with the image and text file with containes the number of each object and their exact position.

![picture](https://drive.google.com/uc?export=view&id=10g8gQa9LMBDRMZXLjkaNwJyAKRXWAKQA)
```
2 0.283482 0.604911 0.183036 0.236607
0 0.872768 0.792411 0.245536 0.352679
0 0.767857 0.647321 0.3125 0.321429
0 0.189732 0.381696 0.370536 0.40625
0 0.477679 0.700893 0.294643 0.3125
```

First column shows the classes (0 for ellipse, 1 for triangle, 2 for general polygon), and the rest of columns show position of the item



## Features

- Easy to use
- Fast
- Accurate

## Usage

Pip install the package:
```
pip install shapedetector==0.0.1
```
Download Weights :

```sh
gdown https://drive.google.com/uc?id=1nXiNOfZRfovIWDz00rgSbFJp2a0mlHrX
```

Some Imports
```py
from shape_detector.main import init_detector 
from shape_detector.main import detect_ellipse
```

init the modell:

```py
init_detector()
```
Run the model (you might need to run this code twice to load properly)
arguments are (path to model, image dim, path to image file)

```py
detect_ellipse("/content/best.pt", 224, "/content/test0099.png")
```

To see the result image run:

```py
from IPython.display import Image
Image('/content/yolov5/runs/detect/exp2/test0036.png', width=500)
```
![picture](https://drive.google.com/uc?export=view&id=10g8gQa9LMBDRMZXLjkaNwJyAKRXWAKQA)

To get the file containing classes, number of objects and their position run:

```py
cat /content/yolov5/runs/detect/exp2/labels/test0036.txt

>>>
2 0.283482 0.604911 0.183036 0.236607
0 0.872768 0.792411 0.245536 0.352679
0 0.767857 0.647321 0.3125 0.321429
0 0.189732 0.381696 0.370536 0.40625
0 0.477679 0.700893 0.294643 0.3125
```
First column shows the classes (0 for ellipse, 1 for triangle, 2 for general polygon), and the rest of columns show position of the item


## Author

| Name | Github | Home Page |
| ------ | ------ | ------|
| Mehdi Hosseini Moghadam | https://github.com/mehdihosseinimoghadam |https://mehdihosseinimoghadam.github.io/|


## License

MIT

**Free Software, Hell Yeah!**


