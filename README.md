# Faster R-CNN with ResNet for Object Classification & Detection in Thermal Images

This repository contains an implementation of **Faster R-CNN with a ResNet-50 + FPN backbone** for **object detection and classification**.  
The project focuses on **thermal imaging** datasets to identify and localize objects (humans, cars, animals) in **low-light or adverse conditions**, making it useful for **surveillance, rescue, and security applications**.

---

## Files in this Repository
- **Faster_RCNN_with_with_ResNet.ipynb**  
  Jupyter Notebook with code for training, evaluation, and visualization.  

- **Faster R-CNN with ResNet.pdf**  
  Project report including problem statement, methodology, training procedure, and results.  

---

## Dataset & Annotation
- **Annotation Tool**: [makesense.ai](https://www.makesense.ai/)  
  Used to label objects in images and export annotations in **Pascal VOC XML format**.  

- **Annotation Format**:
  - Bounding box coordinates (`xmin`, `ymin`, `xmax`, `ymax`)
  - Object class labels mapped to IDs:
    - `car → 1`
    - `man → 2`
    - `cat → 3`
    - `background → 0` (internal use by Faster R-CNN)

- **Workflow**:
  1. Upload dataset images to makesense.ai  
  2. Draw bounding boxes around objects  
  3. Assign labels (car, man, cat)  
  4. Export in Pascal VOC XML format  
  5. Parsed in Python using `xml.etree.ElementTree`

Features

Object Detection → Predicts bounding boxes around detected objects

Object Classification → Distinguishes between classes (car, man, cat)

Transfer Learning → Uses pre-trained ResNet-50 backbone for accuracy on small datasets

Thermal Imaging Support → Converts grayscale images to RGB for compatibility

Visualization → Bounding boxes + labels + confidence scores drawn on images

Requirements

Install dependencies:

pip install torch torchvision opencv-python matplotlib

Usage

Clone this repository:

git clone https://github.com/your-username/faster-rcnn-resnet.git
cd faster-rcnn-resnet


Run the notebook:

jupyter notebook Faster_RCNN_with_with_ResNet.ipynb


Training automatically computes:

Classification loss (Cross-Entropy)

Bounding box regression loss (Smooth L1)

Evaluation metrics include:

Precision, Recall

IoU (Intersection over Union)

mean Average Precision (mAP)

 one single read me file
