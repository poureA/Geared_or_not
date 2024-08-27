# 🦺 Is an Employee Wearing Safety Gear?  
### A Computer Vision Project for Safety Compliance

---

## 🚀 Project Overview  
This project focuses on building a classification model that can automatically determine whether an employee is wearing the necessary safety gear. The dataset consists of images showing people either equipped with a helmet and vest or not. This model is a valuable tool for improving workplace safety, ensuring compliance, and reducing potential risks.

## 📊 Dataset Information  
The dataset is divided into two categories:  
- ❌ **Not Wearing Safety Gear**: 195 images  
- ✅ **Wearing Safety Gear**: 161 images  

The images are organized into labeled folders, making it easy to train and evaluate the model effectively.

### 🖼️ Sample Images:  
Here are a few examples from each class to visualize the data distribution:

---

## 🛠️ Data Loading and Preprocessing  
```python
# Import necessary packages
from os import listdir, mkdir
from shutil import rmtree, copyfile
from random import sample, seed
from numpy import expand_dims
from skimage.io import imread_collection, imshow_collection, imread
from tensorflow.keras.preprocessing.image import ImageDataGenerator, load_img, img_to_array
from tensorflow.keras.applications import InceptionV3
from tensorflow.keras.layers import Flatten, Dense
from tensorflow.keras.models import Model
```

The data is loaded and preprocessed using an `ImageDataGenerator` for scaling and augmentation. The directory structure is created to split the data into training, validation, and testing sets.

## 🧰 Custom Directory Structure Creation  
A function is provided to create the necessary folders for training, validation, and testing. The dataset is split accordingly:
- 📂 **Train Set (80%)**  
- 📂 **Validation Set (10%)**  
- 📂 **Test Set (10%)**

```python
# Function to create directories
def Make_dirs(main_path) -> tuple:
    # Function code here...
```

## 📸 Data Splitting and Image Generation  
Images are randomly sampled for training, validation, and testing, ensuring the data is split evenly. The dataset is then processed through the `ImageDataGenerator` for efficient loading and scaling during training.

## 🧑‍💻 Model Training and Evaluation  
We used a pre-trained **InceptionV3** model, fine-tuning it for binary classification. The top layers are replaced with a Flatten and Dense layer with a sigmoid activation for binary output.

### 🧠 Model Architecture  
- **Base Model**: InceptionV3 (Pre-trained)
- **Top Layers**:  
  - Flatten  
  - Dense (1 unit, Sigmoid)

The model is compiled using the RMSprop optimizer and binary crossentropy loss. Below is a summary of the model:

```python
model.summary()
```

### 🎯 Performance Results  
The model achieves excellent performance on the test set:  
- **Accuracy**: 94.6%  
- **Loss**: 0.381

---

## 📈 Visualization of Training Results  
The following plots illustrate the model's accuracy and loss trends over the epochs for both training and validation sets:

- **Accuracy vs. Epochs**  
- **Loss vs. Epochs**

```python
# Visualization code here...
```

## 🧪 Real-World Testing  
We tested the model on two random images from the internet. The model successfully predicted whether the person is wearing safety gear or not.

```python
# Example predictions
for test in ['test1.jpg', 'test2.jpg']:
    # Prediction code here...
```

## 🎉 Conclusion  
This project demonstrates the successful application of deep learning in ensuring workplace safety. The model can be further enhanced with a larger dataset and additional augmentation techniques.

---
