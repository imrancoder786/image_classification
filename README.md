# Image Classification using CNN (CIFAR-10)

This project implements a **Convolutional Neural Network (CNN)** using **PyTorch** to classify images into 10 different categories.  
The model is trained and evaluated on the standard **CIFAR-10 dataset**.

---

## Dataset

The model uses the **CIFAR-10 dataset**, which contains:

- 60,000 color images  
- Image size: **32 × 32 pixels**  
- 10 classes (6,000 images per class)

### Classes:
```
['plane', 'car', 'bird', 'cat', 'deer', 'dog', 'frog', 'horse', 'ship', 'truck']
```

---

## Project Structure

```
├── image_classfication.ipynb   # Main notebook (training + evaluation + inference)
├── first_classification_model.pth  # Saved trained model
├── 11.png, 22.png, 33.png, image.png  # Sample test images
```

---

## Requirements

Make sure you have the following installed:

- Python 3.x  
- PyTorch  
- Torchvision  
- NumPy  
- Pillow (PIL)  

###  Install dependencies:
```bash
pip install torch torchvision numpy pillow
```

---

## Model Architecture

The CNN model (`Neural_Net`) is built using **PyTorch `nn.Module`**.

### 🔹 Layers:

- **Conv Layer 1**
  - Input: 3 channels  
  - Output: 12 channels  
  - Kernel: 5×5  

- **Max Pooling**
  - Kernel: 2×2  
  - Stride: 2  

- **Conv Layer 2**
  - Input: 12 channels  
  - Output: 24 channels  
  - Kernel: 5×5  

- **Fully Connected Layers**
  - FC1: 24 × 5 × 5 → 120  
  - FC2: 120 → 84  
  - FC3 (Output): 84 → 10  

 **Activation Function:** ReLU (used after conv + FC layers)

---

## Training Details

- **Loss Function:** CrossEntropyLoss  
- **Optimizer:** SGD  
  - Learning Rate: 0.001  
  - Momentum: 0.9  
- **Batch Size:** 32  
- **Epochs:** 30  

---

##  Results

After training for **30 epochs**, the model achieved:

👉 **Accuracy: 68.73% on CIFAR-10 test dataset**

  *(Note: This is a simple baseline project. You can increase the accuracy by adding data augmentation, increasing the number of convolutional layers, adding Dropout/Batch Normalization, or training for more epochs!)*

---

##  Custom Image Inference

The notebook supports testing on your own images.

###  Preprocessing:
- Resize to **32×32**
- Convert to tensor
- Normalize

###  Example Predictions:

| Image        | Description        | Prediction |
|--------------|------------------|------------|
| 11.png       | Cat image         | cat        |
| 22.png       | Cartoon ship      | ship       |
| 33.png       | Cruise ship       | ship       |
| image.png    | Airplane          | plane      |

---

##  How to Run

1. Clone this repository:
```bash
git clone https://github.com/imrancoder786/image_classification
```

2. Open the notebook:
```
image_classfication.ipynb
```

3. Run all cells:
- Dataset download  
- Model training  
- Evaluation  

---

## ⚡ Using Pretrained Model (Skip Training)

If you want to skip training:

- Load the pretrained model:
```python
model.load_state_dict(torch.load("first_classification_model.pth"))
```

- Run evaluation or inference directly

---

## 🎯 Key Highlights

✔️ Simple CNN architecture  
✔️ End-to-end pipeline (training → evaluation → inference)  
✔️ Custom image prediction support  
✔️ Beginner-friendly deep learning project  
