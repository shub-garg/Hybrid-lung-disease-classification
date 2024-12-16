# Project Name: A Hybrid Multi-stage Network for Lung Segmentation, Disease Classification and Severity Localization from X-ray Images

## GitHub Folder Structure

- `segmentation-notebook.ipynb` - Contains the code and implementation of lung image segmentation.
- `classification-and-localisation-notebook.ipynb` - Contains the code and implementation of lung disease classification and localalisation.

## How to run the notebook

### Prerequisites
Before starting, ensure you have a Kaggle account or access to Google Colab, and Python 3 installed if running locally.

- **Step 1: Download the Dataset**
  - Download the [COVID-19 Radiography Database](https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database).
  - The dataset should include images and masks for COVID-19, Lung Opacity, Normal, and Viral Pneumonia.

- **Step 2: Setup Your Environment**
  - **Kaggle**: Upload the dataset to your Kaggle account and use it in a new notebook.
  - **Google Colab**: Upload the dataset to Google Drive, mount the drive in Colab, and update paths accordingly:
  
- **Step 3: Update the paths to the dataset in your notebook based on your environment setup.**
- **Step 4: Run all the cells**

## DATASET

For our project, we are using the [COVID-19 Radiography Database](https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database). This comprehensive database contains chest X-ray images for three distinct classes: COVID-19, normal, and viral pneumonia. Specifically, the dataset comprises 3616 images of COVID-19 positive cases, 10,192 images categorized as normal, and 1345 images identified as viral pneumonia. This extensive collection allows us to train our diagnostic models effectively, ensuring robust performance in identifying and classifying these conditions.

## ABOUT
Accurate and rapid diagnosis of respiratory diseases such as COVID-19 and viral pneumonia using chest X-rays (CXRs) is crucial for timely treatment and containment efforts. However, traditional diagnostic approaches often struggle with high variability in image quality and the subtlety of disease manifestations, leading to a significant rate of diagnostic errors. To address these challenges, this report presents a novel hybrid multi-stage network that initially segments the lung region in the CXR images, followed by classification and subsequent localization of the disease using Grad-CAM. This approach allows for focused analysis on relevant lung areas, enhancing the model's accuracy and reliability in diagnosing respiratory conditions

## METHODOLOGY
Our approach involves a systematic progression through three stages: segmentation, classification, and localization. This structured workflow allows us to precisely isolate and analyze lung regions, identify pathological conditions, and visually highlight critical areas influencing diagnostic outcomes, thereby facilitating a comprehensive examination of CXR images.

<p align="center">
  <img src="Images/arch.jpg" alt="Architecture Image">
</p>

## RESULTS

### Segmentation Models Experiment Results

# Segmentation Models Performance Table

| **Base Model** | **Backbone**      | **Binary Accuracy** | **Dice Coefficient** | **IoU Score** |
|----------------|-------------------|----------------------|-----------------------|---------------|
| **U-Net**      | ResNet50          | 0.9844              | 0.9664               | 0.9916        |
|                | SEResNeXt50       | 0.9833              | 0.9658               | 0.9913        |
|                | **InceptionV3**   | **0.9867**          | **0.9727**           | **0.9928**    |
|                | MobileNetV2       | 0.7445              | 0.6346               | 0.7682        |
| **LinkNet**    | ResNet50          | 0.9826              | 0.9644               | 0.9907        |
|                | SEResNeXt50       | 0.9826              | 0.9635               | 0.9905        |
|                | **InceptionV3**   | **0.9839**          | **0.9671**           | **0.9914**    |
|                | MobileNetV2       | 0.7472              | 0.6583               | 0.7928        |
| **FPN**        | **ResNet50**      | **0.9840**          | **0.9683**           | **0.9917**    |
|                | SEResNeXt50       | 0.9825              | 0.9653               | 0.9909        |
|                | InceptionV3       | 0.9838              | 0.9656               | 0.9916        |
|                | MobileNetV2       | 0.7474              | 0.7050               | 0.8037        |
| **PSPNet**     | ResNet50          | 0.9835              | 0.9658               | 0.9912        |
|                | SEResNeXt50       | 0.9828              | 0.9644               | 0.9909        |
|                | **InceptionV3**   | **0.9840**          | **0.9668**           | **0.9915**    |
|                | MobileNetV2       | 0.7916              | 0.7439               | 0.8569        |



### Classification Models Experiment Results and graphs:


# Performance Comparison on Validation and Test Sets

| **Model**           | **Val Loss** | **Val Acc.**    | **Test Loss** | **Test Acc.**    |
|----------------------|--------------|-----------------|---------------|------------------|
| **CoAtNet0**         | **0.159**    | **95.80%**      | **0.144**     | **95.49%**       |
| Xception            | 0.182        | 95.63%          | 0.220         | 93.80%           |
| ResNet50            | 0.182        | 93.11%          | 0.220         | 92.64%           |
| InceptionResNet50   | 0.193        | 94.81%          | 0.197         | 93.87%           |
| ViT                 | 0.165        | 95.78%          | 0.178         | 95.27%           |

