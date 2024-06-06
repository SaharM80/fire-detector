# Fire Detection Using Object Detection Models

Welcome to the Fire Detection project! This project leverages deep learning techniques to detect fire in images using `object detection` models. The primary focus is on training and evaluating models for efficient fire detection.

## Overview

This project utilizes the `IceVision` library and various object detection models to detect fire in images. The dataset used for training and validation is the FireNET dataset. Two models, `Faster R-CNN` and `Deformable DETR`, are implemented to compare their performance in fire detection tasks. 

## Dependencies

install IceVision and Sahi using the following commands:
  ```bash
    !wget https://raw.githubusercontent.com/airctic/icevision/master/icevision_install.sh
    !bash icevision_install.sh cuda11 master
    !pip install sahi<0.10
  ```

## Dataset

  The model was trained on the FireNET dataset. You can download it from here: <a href="https://github.com/OlafenwaMoses/FireNET/releases/download/v1.0/fire-dataset.zip">Link to the dataset</a>

## Models

Two models were trained and saved along with their artifacts in this notebook. here is the link to both models: <a href="https://drive.google.com/drive/folders/13Sl069By28B6G7w5v3P217b0IyW2LSNK?usp=sharing">Link to both models</a>

## Steps to training the model

1. **Set Up Environment**: Installed necessary libraries, including IceVision and SAHI.
2. **Download Dataset**: Retrieved the FireNET dataset and extracted it.
3. **Prepare Data**: Organized images and annotations for training and validation.
4. **Parse Annotations**: Created a parser to read VOC-format annotations and generate records.
5. **Data Augmentation**: Defined transformation pipelines for training and validation datasets.
6. **Create Datasets**: Applied transformations to create training and validation datasets.
7. **Select Model**: Chose the Faster R-CNN model with a ResNet-101 FPN backbone.
8. **Initialize Model**: Instantiated the model with the chosen backbone and set up the data loaders.
9. **Train Model**: Fine-tuned the model with learning rate scheduling and specific epoch settings.
10. **Evaluate Model**: Assessed model performance using COCOMetric and visualized results.
11. **Save Model**: Saved the trained model and its metadata for future inference.

## Results

The Deformable DETR model with a Two-Stage Refine R50 backbone had the best results with a COCO metric of approximately 0.31. You can see the results of the models in the table below.

| Model Type        | Backbone                | Number of Epochs | Training Loss | Validation Loss | COCO Metric |
|-------------------|-------------------------|------------------|---------------|-----------------|-------------|
| Faster R-CNN      | ResNet-101 FPN          | 6                | 0.210372      | 0.282582        | 0.281485    |
| Deformable DETR   | Two-Stage Refine R50    | 8                | 9.311149      | 9.808652        | 0.312269    |

here is also an example of how the two models performed on a set of images.

| Faster R-CNN | Deformable DETR |
|--------------|-----------------|
| <img src="https://github.com/SaharM80/fire-detector/assets/130160952/02165846-38f9-42c7-8a5e-00153edc9668" alt="Faster R-CNN" width="400"/>| <img src="https://github.com/SaharM80/fire-detector/assets/130160952/02165846-38f9-42c7-8a5e-00153edc9668" alt="Faster R-CNN" width="400"/>|





