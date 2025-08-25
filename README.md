# Faster R-CNN with ResNet for Object Detection in Thermal Images

This repository contains an implementation of **Faster R-CNN with a ResNet-50 + FPN backbone** for object detection and classification in thermal imaging datasets. The model is designed to identify and localize objects (humans, cars, animals) in low-light or adverse conditions, making it particularly useful for surveillance, rescue operations, and security applications.

## Features

- **Object Detection**: Predicts bounding boxes around detected objects
- **Object Classification**: Distinguishes between multiple classes (car, man, cat)
- **Transfer Learning**: Utilizes pre-trained ResNet-50 backbone for improved accuracy on small datasets
- **Thermal Imaging Support**: Converts grayscale thermal images to RGB for compatibility with pre-trained models
- **Visualization**: Draws bounding boxes with labels and confidence scores on detected images

## Dataset & Annotation

- **Annotation Tool**: [makesense.ai](https://www.makesense.ai/)
- **Annotation Format**: Pascal VOC XML format containing:
  - Bounding box coordinates (`xmin`, `ymin`, `xmax`, `ymax`)
  - Object class labels mapped to IDs:
    - `car → 1`
    - `man → 2`
    - `cat → 3`
    - `background → 0` (internal use by Faster R-CNN)

### Annotation Workflow

1. Upload dataset images to makesense.ai
2. Draw bounding boxes around objects of interest
3. Assign appropriate labels (car, man, cat)
4. Export annotations in Pascal VOC XML format
5. Parse annotations in Python using `xml.etree.ElementTree`

## Project Structure

```
├── Faster_RCNN_with_with_ResNet.ipynb  # Main Jupyter notebook with implementation
├── Faster R-CNN with ResNet.pdf        # Detailed project report
└── README.md                           # This file
```

## Requirements

Install the necessary dependencies:

```bash
pip install torch torchvision opencv-python matplotlib
```

## Usage

1. Clone this repository:
```bash
git clone https://github.com/your-username/faster-rcnn-resnet.git
cd faster-rcnn-resnet
```

2. Run the Jupyter notebook:
```bash
jupyter notebook Faster_RCNN_with_with_ResNet.ipynb
```

3. Follow the notebook instructions to:
   - Load and preprocess your thermal image dataset
   - Parse XML annotations
   - Configure and train the Faster R-CNN model
   - Evaluate model performance
   - Visualize detection results

## Training and Evaluation

The training process automatically computes:
- Classification loss (Cross-Entropy)
- Bounding box regression loss (Smooth L1)

Evaluation metrics include:
- Precision and Recall
- IoU (Intersection over Union)
- mean Average Precision (mAP)

## Applications

This implementation is particularly suited for:
- Surveillance systems in low-light conditions
- Search and rescue operations
- Security applications
- Wildlife monitoring
- Autonomous navigation in adverse conditions

## Technical Details

The model architecture consists of:
- **Backbone**: ResNet-50 with Feature Pyramid Network (FPN)
- **Region Proposal Network (RPN)**: Generates candidate object regions
- **RoI Heads**: Performs classification and bounding box regression on proposed regions

For detailed information about the methodology, training procedure, and results, please refer to the project report: **Faster R-CNN with ResNet.pdf**
