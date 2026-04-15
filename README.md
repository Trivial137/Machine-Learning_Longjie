# Machine Learning

This repo serves as a project of the Lecture **Machine Learning**. 

---

## Getting Started

This project is designed to be run in a Google Colab.

### Prerequisites
- A Google Account to use Google Colab.
- A Kaggle Account to download the dataset via their API.

### Execution

1.  **Open in Google Colab**
    - Go to [Google Colab](https://colab.research.google.com/).
    - Click `File > Upload notebook`.
    - Upload the file.

2.  **Configure Kaggle API**
    - The notebook requires a Kaggle API token to download the dataset.
    - Run the first code cell in the notebook. It will prompt you to **upload the `kaggle.json` file**.

3.  **Run the Notebook**
    - Execute the cells sequentially from top to bottom.
    - Make sure to set the runtime type to **GPU**.

---

## Project Details

### Dataset
The project utilizes the "Chest X-Ray Images (Pneumonia)" dataset available on Kaggle.
*   **Link:** [https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)
*   **Contents:** 5,863 JPEG images of chest X-rays.
*   **Classes:** `PNEUMONIA` and `NORMAL`.

### Methodology
The core of this project is **transfer learning**.
1.  **Pre-trained Base:** We use the `ResNet50` model & `Adam` optimizer.
2.  **Freezing Layers:** The convolutional base of ResNet50 is "frozen" to preserve its learned feature representations.
3.  **Custom Classifier:** A new classifier "head" is added on top of the ResNet50 base. Only the weights of this new classifier are trained.
4.  **Data Augmentation:** To prevent overfitting, the training images are artificially augmented with random rotations, zooms, shifts, and flips.

### Tech Stack
- TensorFlow / Keras
- Scikit-learn
- NumPy
- Matplotlib & Seaborn
- Google Colab

---

## Results

After training, the model was evaluated on the unseen test set.

#### Performance Metrics

| Metric     | Score      |
| :--------- | :--------- |
| Test Accuracy   | **72.28%**   |
| Test Precision  | **71.23%**   |
| Test Recall     | **93.33%**   |
| Test Loss       | **0.5185**  |

#### Visualizations
The notebook generates key visualizations to interpret model performance.

**Confusion Matrix:** Shows the breakdown of correct and incorrect predictions.
![Confusion Matrix](./confusion_matrix.png)

**Training History:** Plots the accuracy and loss curves over epochs to check for overfitting.
![Training History](./training_history.png)


---

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![Keras](https://img.shields.io/badge/Keras-2.x-red.svg)](https://keras.io/)

</div>
