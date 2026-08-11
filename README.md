# 🧠 Brain MRI Tumor Classification

A deep learning project for classifying brain MRI images into four categories using a custom Convolutional Neural Network (CNN).

---

## 📌 Project Overview

Brain tumors are abnormal growths of cells in the brain that can be identified and analyzed using medical imaging techniques such as Magnetic Resonance Imaging (MRI).

This project applies image preprocessing, data augmentation, and deep learning techniques to classify brain MRI images into four categories:

* **Glioma**
* **Meningioma**
* **No Tumor**
* **Pituitary**

The project includes image preprocessing, dataset exploration, data augmentation, CNN model training, and model evaluation using a confusion matrix.

---

## 🎯 Objectives

The main objectives of this project are to:

* Preprocess brain MRI images to improve their quality.
* Enhance local image contrast using CLAHE.
* Reduce image noise using Gaussian Blur.
* Resize images to a fixed size of **224 × 224**.
* Normalize pixel values to the range **0–1**.
* Apply data augmentation to improve model generalization.
* Build and train a CNN for multi-class brain tumor classification.
* Evaluate the trained model using test data and a confusion matrix.

---

## 🗂️ Dataset

The dataset used in this project is the **Brain Tumor MRI Dataset** from Kaggle.

It contains brain MRI images categorized into four classes:

* **Glioma**
* **Meningioma**
* **No Tumor**
* **Pituitary**

🔗 **[Brain Tumor MRI Dataset – Kaggle](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)**

> The dataset images are not included in this repository due to their size. Please download the dataset directly from Kaggle to reproduce the project.

---

## 🔧 Image Preprocessing

Each MRI image goes through the following preprocessing pipeline:

```text
Original MRI
     ↓
Grayscale Conversion
     ↓
CLAHE
     ↓
Gaussian Blur
     ↓
Resize to 224 × 224
     ↓
Normalization (0–1)
     ↓
Processed Image
```

### Preprocessing Techniques

#### 1. Grayscale Conversion

The MRI images are converted to grayscale before further processing.

#### 2. CLAHE

**Contrast Limited Adaptive Histogram Equalization (CLAHE)** is applied to enhance local contrast and improve the visibility of image details.

Configuration used:

```text
clipLimit = 2.0
tileGridSize = (8, 8)
```

#### 3. Gaussian Blur

Gaussian Blur is applied to reduce image noise before resizing.

```text
Kernel Size = (3, 3)
```

#### 4. Resizing

All images are resized to:

```text
224 × 224
```

#### 5. Normalization

Pixel values are normalized from:

```text
0–255 → 0–1
```

---

## 🔄 Data Augmentation

Data augmentation is applied to the training images using:

* Rotation
* Zoom
* Shearing
* Brightness adjustment
* Horizontal flipping
* Vertical flipping

These transformations increase the variety of training samples and help the model generalize to different image variations.

---

## 🧠 CNN Architecture

A custom Convolutional Neural Network (CNN) is used for the classification task.

```text
Input
224 × 224 × 1
      │
      ▼
Conv2D (32 filters)
      │
Batch Normalization
      │
Max Pooling
      │
      ▼
Conv2D (64 filters)
      │
Batch Normalization
      │
Max Pooling
      │
      ▼
Conv2D (128 filters)
      │
Batch Normalization
      │
Max Pooling
      │
      ▼
Flatten
      │
Dense (256)
      │
Dropout (0.5)
      │
      ▼
Softmax
      │
      ▼
4 Classes
```

### Model Configuration

| Parameter         | Value                     |
| ----------------- | ------------------------- |
| Input Shape       | 224 × 224 × 1             |
| Batch Size        | 32                        |
| Optimizer         | Adam                      |
| Loss Function     | Categorical Cross-Entropy |
| Maximum Epochs    | 30                        |
| Dropout           | 0.5                       |
| Output Activation | Softmax                   |
| Number of Classes | 4                         |

---

## 📊 Model Evaluation

The model is evaluated using the testing dataset.

A **confusion matrix** is used to analyze the model's predictions across the four classes:

* Glioma
* Meningioma
* No Tumor
* Pituitary

The confusion matrix provides an overview of the correctly and incorrectly classified MRI images for each class.

> Evaluation results can be reproduced by downloading the dataset from Kaggle and running the project.

---

## 🛠️ Technologies & Libraries

* **Python**
* **TensorFlow / Keras**
* **OpenCV**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **Seaborn**
* **Google Colab**

---

## 📁 Project Structure

```text
Brain-MRI-Tumor-Classification/
│
├── brain_tumor.py
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/balsamkhaleel/Brain-MRI-Tumor-Classification.git
```

### 2. Navigate to the Project Directory

```bash
cd Brain-MRI-Tumor-Classification
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

The original implementation was developed using **Google Colab** and Google Drive for dataset storage.

### Step 1 — Download the Dataset

Download the dataset from Kaggle:

**[Brain Tumor MRI Dataset – Kaggle](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)**

### Step 2 — Configure the Dataset Path

Place the dataset in your Google Drive and update the dataset paths in `brain_tumor.py` according to your local Google Drive structure.

### Step 3 — Run the Project

The project can be executed using Google Colab or a compatible Python environment.

```bash
python brain_tumor.py
```

---

## 📈 Workflow

The overall workflow of the project is:

```text
Dataset
   ↓
Image Preprocessing
   ↓
Grayscale Conversion
   ↓
CLAHE
   ↓
Gaussian Blur
   ↓
Resize
   ↓
Normalization
   ↓
Data Augmentation
   ↓
CNN Training
   ↓
Testing
   ↓
Confusion Matrix
   ↓
Classification Results
```

---

## 🔮 Future Improvements

Possible improvements for future versions of the project include:

* Comparing the custom CNN with pretrained models such as VGG16, ResNet, and EfficientNet.
* Adding a dedicated validation dataset.
* Using additional evaluation metrics such as Precision, Recall, and F1-Score.
* Applying Grad-CAM for model interpretability and visualization.
* Performing hyperparameter optimization.
* Deploying the trained model as a web application or API.

---


⭐ If you find this project useful, feel free to star the repository.

