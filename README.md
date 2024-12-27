# DatathonAI: Geolocation Prediction for ITU Ayazağa Campus

This repository contains our solution for the **DatathonAI Competition**, hosted by the ITU AI Club. The goal is to predict the geographic coordinates (latitude and longitude) of images taken within the ITU Ayazağa Campus using machine learning.

## Dataset

The dataset is available on Kaggle: [DatathonAI Dataset](https://www.kaggle.com/datasets/ardaarslan10/aidataton/data).

### Structure
- **Training Data**: Images and a CSV file (`train.csv`) with corresponding latitude and longitude.
- **Test Data**: Images to predict coordinates.

All images are resized to **299x299 pixels** 

## Solution Overview

- **Model**: We used **EfficientNet-B2** for its efficiency and performance in image-based tasks.
- **Preprocessing**:
  - Applied data augmentation (rotations, flips, brightness adjustments).
- **Training**:
  - Loss: Custom Haversine distance-based loss function.
  - Optimizer: Adam with a learning rate scheduler.
- **Evaluation**: Predictions are evaluated using the **Root Mean Square Error (RMSE)** of the Haversine distance.

## Submission Format

The predictions are in a CSV file with the following structure:
| row_id | latitude | longitude |
|--------|----------|-----------|
| 1      | 41.12345 | 29.98765  |
| 2      | 41.54321 | 29.87654  |
