# 🧠 ASL Alphabet Classification with ResNet-50

## Overview

This project implements a deep learning classifier for the American Sign Language (ASL) alphabet using **MATLAB** and its **Deep Learning Toolbox™**. The model leverages **transfer learning** with a pre-trained **ResNet-50** network to distinguish between 24 ASL letters (excluding 'J' and 'Z'). The workflow covers data loading, preprocessing, model training, evaluation, and prediction on new, unlabeled images.

-----

## 💡 Features

  - Classifies **24 ASL alphabet signs** from images.
  - Utilizes **transfer learning** with the powerful **ResNet-50** architecture.
  - Automates data loading and preprocessing using `imageDatastore`.
  - Splits data into training, validation, and test sets for robust evaluation.
  - Evaluates model performance using **accuracy** metrics and a **confusion matrix**.
  - Predicts labels for a set of new, unlabeled images.

-----

## 🧱 Pipeline Structure

The classification pipeline is executed in three main parts within the `ASLAlphabetClassificationResNet50.mlx` script:

### 1\. **Data Preparation and Exploration**

  - Loads the training, testing, and unlabeled image datasets using `imageDatastore`.
  - Splits the training data into an 80% training set and a 20% validation set.
  - Prepares a **ResNet-50** model for transfer learning by modifying its final layers for 24 classes.
  - Resizes all images to match the network's input size (`224x224x3`) using `augmentedImageDatastore`.

### 2\. **Model Training and Evaluation**

  - Defines training options, including the `adam` optimizer and enabling GPU acceleration.
  - Trains the network on the augmented training data while monitoring performance on the validation set.
  - Evaluates the final model's accuracy on the held-out test set.
  - Generates a **confusion matrix** to visualize classification performance across all classes.

### 3\. **Prediction on New Images**

  - Uses the trained model (`newNet`) to predict the classes of new, unlabeled images.
  - Displays the predicted labels in the MATLAB command window.

-----

## 📂 File Structure

```
📁 ASL_Alphabet_Classification/
├── 📄 ASLAlphabetClassificationResNet50.mlx   # Main MATLAB script for the project
└── 📁 Data/
    ├── 📁 Train/
    │   ├── 📁 A/
    │   ├── 📁 B/
    │   └── 📁 ... (folders for each letter)
    ├── 📁 Test/
    │   ├── 📁 A/
    │   ├── 📁 B/
    │   └── 📁 ...
    └── 📁 Unlabeled/
        └── 📄 (unlabeled images)
```

-----

## 📊 Input Data Schema

The model is trained on image data with the following structure and format:

### 📁 `Train/` and `Test/` Folders

  - **Format:** Image files (e.g., `.jpg`, `.png`).
  - **Structure:** Images are organized into subfolders, where each subfolder's name corresponds to the class label (e.g., `A`, `B`, `C`).
  - **Content:** Contains images of hand signs for the 24 ASL alphabet letters used for training and evaluation.

### 📁 `Unlabeled/` Folder

  - **Format:** Image files (e.g., `.jpg`, `.png`).
  - **Structure:** All images are placed directly inside this folder without any class subfolders.
  - **Content:** Contains new hand sign images for which the model will generate predictions.

-----

## 🔧 Requirements

  - **MATLAB** (R2024b or newer recommended)
  - **Deep Learning Toolbox™**
  - **Computer Vision Toolbox™**
  - A CUDA-enabled NVIDIA GPU is recommended for faster training.

-----

## ⚙️ Installation

Unlike Python projects that use `requirements.txt`, MATLAB project dependencies are managed through **Toolboxes**. Ensure you have the required toolboxes installed.

1.  Open MATLAB.
2.  Run the following commands in the MATLAB Command Window to verify your installation:
    ```matlab
    % Check for Deep Learning Toolbox
    ver('deeplearning')

    % Check for Computer Vision Toolbox
    ver('vision')
    ```
3.  If either toolbox is missing, you can install it using the **Add-On Explorer** in the MATLAB Home tab.

-----

## 🛠️ Setup Instructions

1.  **Clone the repository** or download the `ASLAlphabetClassification.m` script.
2.  **Organize your dataset** according to the `File Structure` shown above. Create `Train`, `Test`, and `Unlabeled` folders.
3.  **Update file paths** in `ASLAlphabetClassification.m`. Modify the `filenameTrain`, `filenameTest`, and `filenameUnlabeled` variables to point to the correct locations on your machine.
    ```matlab
    % Part 1: Data Preparation and Exploration
    filenameTrain = "path/to/your/Data/Train";
    filenameTest = "path/to/your/Data/Test";
    filenameUnlabeled = "path/to/your/Data/Unlabeled";
    ```

-----

## 🚀 Usage

1.  Open **MATLAB**.
2.  Navigate to the project directory and open the `ASLAlphabetClassification.m` script.
3.  Click the **Run** button in the MATLAB editor or type `ASLAlphabetClassification` in the Command Window and press Enter.
4.  After the script runs, check the outputs:
      - **Command Window:** View the final validation and test accuracy percentages, along with the predicted classes for the unlabeled images.
      - **Figure Windows:** Two plots will be generated: a **Training Progress** plot and a **Confusion Matrix** for the test set.

-----

## 🔍 Pipeline Monitoring

While this script doesn't use a formal orchestration tool, monitoring is achieved through MATLAB's built-in features:

  - **Real-time Training Progress:** The script generates a live plot during training (`'Plots', 'training-progress'`). This window displays the model's accuracy and loss on both the training and validation sets in real-time.
  - **Command Window Logging:** Key metrics are printed to the MATLAB Command Window upon completion for final review.
  - **Visual Evaluation:** The final **confusion matrix** plot provides a detailed visual breakdown of the model's performance on the test set.

-----

## 🎓 Course Attribution

This project was inspired by and developed for the **"Deep Learning for Computer Vision"** course provided by **MathWorks**. It demonstrates the practical application of transfer learning for image classification tasks using MATLAB's powerful toolboxes.

---

## 👤 Author

**Kirubhakaran Meenakshi Sundaram**

📧 Email: km1079@g.rit.edu  
💼 LinkedIn: https://www.linkedin.com/in/kirubhakaranm/

---

## 🤝 Contributing

This is an educational project designed to demonstrate deep learning concepts. If you have suggestions for improvements or find any issues, please feel free to open an issue on the project's repository.

-----

## ⚖️ License

The dataset used in this project is provided by The MathWorks, Inc. and is subject to the following license terms:

```text
License for Deep Learning for Computer Vision Data Set
Copyright 2024 The MathWorks, Inc.

Redistribution and use of this dataset, with or without modification, are permitted provided that the following conditions are met:

1. Redistribution in any form must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistribution and use in any form must be accompanied by the following citation: 

          Data Set provided by The MathWorks, Inc. (www.mathworks.com).

THIS DATASET IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DATASET, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

-----

## 📚 Additional Resources

  - [MATLAB Deep Learning Toolbox Documentation](https://www.mathworks.com/help/deeplearning/)
  - [Transfer Learning with `trainnet`](https://www.mathworks.com/help/deeplearning/ref/trainnet.html)
  - [Pre-trained ResNet-50 Model](https://www.mathworks.com/help/deeplearning/ref/resnet50.html)
  - [Managing Image Datasets with `imageDatastore`](https://www.mathworks.com/help/matlab/ref/matlab.io.datastore.imagedatastore.html)