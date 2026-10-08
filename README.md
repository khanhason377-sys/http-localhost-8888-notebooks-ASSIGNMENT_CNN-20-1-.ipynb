# CNN Fruits & Vegetables Image Classification

## 📌 Project Overview

This project implements a **Convolutional Neural Network (CNN)** using **TensorFlow/Keras** to classify images of different fruits and vegetables.

The model is trained on a dataset containing **36 different classes** of fruits and vegetables. The images are resized to **228 × 228 pixels** and processed using TensorFlow's image dataset utilities.

The project includes:
- Dataset loading and extraction
- Image preprocessing
- Training and validation dataset creation
- CNN model building
- Model training
- Accuracy and loss visualization
- Image prediction using the trained CNN model

---

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Google Colab

---

## 📂 Dataset

The project uses the **Fruits & Vegetables dataset** stored as:

```text
Fruits_Vegetables.zip
```

The dataset contains **36 classes** of fruits and vegetables.

The images are loaded from:

```text
classdataset/Fruits_Vegetables/
```

The notebook uses the test directory for creating the training and validation datasets.

---

## ⚙️ Image Configuration

The images are resized to:

```text
228 × 228 pixels
```

Batch size:

```text
32
```

Number of classes:

```text
36
```

The images are loaded in RGB format.

---

## 🧹 Data Preprocessing

The dataset is loaded using TensorFlow's:

```python
tf.keras.utils.image_dataset_from_directory()
```

The data is divided into:

- **80% Training Data**
- **20% Validation Data**

The dataset is also optimized using:

```python
cache()
shuffle()
prefetch()
```

This helps improve the data pipeline and training performance.

---

## 🔄 Data Augmentation

The notebook defines data augmentation techniques including:

```python
RandomFlip
RandomRotation
RandomZoom
```

These techniques can help the model generalize better and reduce overfitting when applied during training.

---

## 🧠 CNN Model Architecture

The CNN model contains the following major layers:

```text
Input Layer
     ↓
Rescaling
     ↓
Conv2D (16 filters)
     ↓
MaxPooling2D
     ↓
Conv2D (32 filters)
     ↓
MaxPooling2D
     ↓
Conv2D (64 filters)
     ↓
MaxPooling2D
     ↓
Flatten
     ↓
Dense (128 neurons)
     ↓
Dense (36 classes)
```

The convolutional layers use **ReLU activation**, while the final layer uses **Softmax** for multi-class classification.

---

## ⚡ Model Compilation

The model is compiled using:

```python
optimizer = "adam"
loss = "sparse_categorical_crossentropy"
metrics = ["accuracy"]
```

`Sparse Categorical Crossentropy` is used because the problem contains multiple image classes with integer class labels.

---

## 🚀 Model Training

The model is trained for:

```text
15 Epochs
```

Validation data is also provided during training to monitor the model's performance.

Example:

```python
history = model.fit(
    train_ds,
    validation_data=val_ds,
    epochs=epochs
)
```

---

## 📊 Performance Visualization

The notebook generates graphs for:

### Training & Validation Accuracy

The accuracy graph helps compare the model's performance on training and validation data.

### Training & Validation Loss

The loss graph helps monitor how the model's error changes during training.

These graphs can also help identify possible overfitting or underfitting.

---

## 🔮 Image Prediction

A custom prediction function is created:

```python
def predict_image(img_path):
```

The function:

1. Loads an image.
2. Resizes it to 228 × 228.
3. Converts it into an array.
4. Adds the batch dimension.
5. Sends the image to the trained CNN.
6. Finds the predicted class.
7. Displays the prediction confidence.

Example:

```python
predict_image("path/to/image.jpg")
```

The output provides the predicted fruit/vegetable and its confidence percentage.

---

## 📁 Project Structure

```text
CNN-Fruits-Vegetables/
│
├── ASSIGNMENT_CNN (1
