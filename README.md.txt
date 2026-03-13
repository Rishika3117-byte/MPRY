# Offroad Semantic Scene Segmentation

Github Link: "https://github.com/Rishika3117-byte/MPRY/tree/main"
HuggingFace Link: "https://huggingface.co/rishika3117/Team_Web-Buddies_Segmentation_Model/tree/main"

### Import Paradox Hackathon – Duality AI

## Project Overview

This project focuses on **semantic segmentation for off-road environments** using synthetic desert data generated from a digital twin simulation platform.
The goal is to train a deep learning model that can **identify and classify terrain elements at the pixel level** to assist autonomous ground vehicles in navigation and obstacle avoidance.

The model was trained using the provided dataset and evaluated on unseen images to measure its **generalization capability in new desert environments**.

---
## Model Performance

IoU Score: 0.9796
Training Images: 1088
Model: DeepLabV3 (ResNet50)
---
# Model Information

**Model Architecture:** DeepLabV3
**Backbone:** ResNet-50
**Framework:** PyTorch

DeepLabV3 was selected due to its strong performance in **semantic segmentation tasks**, using atrous convolution to capture multi-scale contextual information.

---
## Model Weights

The trained model weights are available here:

Hugging Face:
https://huggingface.co/rishika3117/Team_Web-Buddies_Segmentation_Model/tree/main

Model size: 160 MB
Architecture: DeepLabV3 + ResNet50
Framework: PyTorch
---
# Dataset

The dataset consists of **synthetic desert environment images** generated from a digital twin platform.

### Dataset Structure

```
Offroad_Segmentation_Training_Dataset/

train/
    Color_Images/
    mask/

val/

testImages/
```

### Classes Included

| Class ID | Class Name     |
| -------- | -------------- |
| 100      | Trees          |
| 200      | Lush Bushes    |
| 300      | Dry Grass      |
| 500      | Dry Bushes     |
| 550      | Ground Clutter |
| 600      | Flowers        |
| 700      | Logs           |
| 800      | Rocks          |
| 7100     | Landscape      |
| 10000    | Sky            |

Each image has a corresponding **segmentation mask** representing ground truth labels.

---

# Project Workflow

The workflow followed these major stages:

1. Dataset Preparation
2. Data Loading and Preprocessing
3. Model Training
4. Performance Evaluation
5. Visualization of Segmentation Results

---

# Environment Setup

### Requirements

Python 3.8+
PyTorch
Torchvision
OpenCV
Matplotlib
NumPy

### Install Dependencies

```
pip install torch torchvision opencv-python matplotlib numpy
```
## How to Run

1. Clone the repository

git clone https://github.com/Rishika3117-byte/MPRY/tree/main

2. Install dependencies

pip install -r requirements.txt

3. Run training

python train.py

4. Run inference

python test.py
---

# Training the Model

Run the training notebook or script.

```
python train.py
```

Training steps:

1. Load dataset and masks
2. Initialize DeepLabV3 model
3. Replace classifier for custom segmentation classes
4. Train using CrossEntropyLoss
5. Optimize with Adam optimizer

Example training parameters:

| Parameter     | Value |
| ------------- | ----- |
| Epochs        | 5     |
| Batch Size    | 4     |
| Learning Rate | 0.001 |

---

# Model Evaluation

The model performance was evaluated using **Intersection over Union (IoU)**.

IoU measures how well predicted segmentation overlaps with ground truth masks.

### Result

**Dataset IoU Score:**

```
0.9796
```

This indicates **very strong segmentation accuracy** on the dataset.

---

# Running Inference

To test the trained model on images:

```
python test.py
```

This will generate segmentation predictions for new input images.

Output includes:

* Predicted segmentation masks
* Visualization comparisons
* Performance metrics

---

# Segmentation Results

Each result visualization contains:

1. Original Image
2. Ground Truth Mask
3. Model Prediction

Example output files:

```
segmentation_5.png
segmentation_20.png
segmentation_50.png
segmentation_100.png
```

These images demonstrate the model’s ability to correctly identify terrain classes.

---

# Folder Structure

```
Hackathon_Project/

model/
    offroad_model.pth

results/
    segmentation_results.zip
    results.txt

code/
    train.ipynb

README.md
report.pdf
```

---

# Challenges Faced

Some challenges during the project included:

* Handling segmentation masks with multiple class IDs
* Dataset preprocessing and matching image-mask pairs
* Class imbalance between terrain categories
* GPU limitations during training

These were addressed through preprocessing validation and optimized training settings.

---

# Possible Improvements

Future improvements could include:

* Training for more epochs
* Using advanced backbones such as ResNet-101
* Applying data augmentation
* Implementing class balancing techniques
* Testing on larger real-world datasets

---

# Applications

Semantic segmentation for off-road environments can support:

* Autonomous ground vehicles
* Agricultural robotics
* Disaster response robots
* Terrain navigation systems

---

# Authors

Team Members:
Manisha Sirvi
Preethi Biradar
Rishika Hanchate
Yashasvi Yadav

Institution:
Bankatlal Badruka College for Information Technology

---

# Acknowledgements

This project was completed as part of the **Import Paradox Hackathon** using synthetic data provided by Duality AI.

Special thanks to the organizers for providing the dataset and challenge environment.

---

# License

This project is intended for **educational and research purposes only**.





