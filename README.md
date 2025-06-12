# Facial Emotion Recognition using MobileNet

This project presents a lightweight real-time **Facial Emotion Recognition (FER)** system using **MobileNetV2**. It applies transfer learning for emotion classification and benchmarks performance against a basic CNN model, with optimizations for mobile deployment.

---

## 📌 Objective

- Leverage MobileNet for real-time FER on mobile/edge devices
- Apply transfer learning for better performance
- Address dataset imbalance using augmentation
- Compare performance with a custom CNN

---

## 📂 Dataset

- **Source**: Kaggle
- **Input**: 224×224 grayscale PNG images of human faces
- **Original Classes**: `anger`, `contempt`, `disgust`, `fear`, `happiness`, `neutral`, `sad`, `surprise`
- **Final Classes Used**: 5 (underrepresented classes like `contempt` removed)

---

## 🧪 Methodology

### 🖼 Preprocessing
- Convert grayscale → RGB
- Resize to 224×224 (MobileNetV2 input size)
- Normalize pixel values
- Convert to PyTorch tensors

### 🧬 Data Augmentation
- Augmented samples to handle class imbalance (target ~1000 per class)
- Removed classes that performed poorly even after augmentation

### 🤖 Models

#### 🔹 MobileNetV2
- Pretrained on ImageNet
- Final classifier layer modified to 5 classes
- Fine-tuned only the top classifier layers
- Optimizer: **Adam**
- Loss Function: **CrossEntropy**

#### 🔸 CNN (Custom)
- 2 Convolutional layers (32 & 64 filters)
- MaxPooling, Flattening, and Fully Connected layers
- Output: 5 emotion categories
- Trained on the same dataset as MobileNetV2

---

## 📊 Results

| Model                  | Accuracy | Training Time |
|------------------------|----------|---------------|
| CNN (Custom)           | 51%      | ~60 mins      |
| MobileNetV2 (Baseline) | 49%      | ~34 mins      |
| MobileNetV2 (Fine-Tuned) | 48%    | ~36 mins      |

- **MobileNetV2** is preferred in real-time applications for its **faster training/inference**
- Metrics used: **Accuracy**, **Precision**, **Recall**, **F1-Score**

---

## 🚀 Applications

- **Mental Health Monitoring**: Mood analysis over time
- **Accessibility Tools**: Emotion recognition support for neurodiverse individuals
- **Driver Monitoring**: Drowsiness/distraction detection
- **Interactive Mobile Apps**: Emotion-aware user interfaces

---

## 🔭 Future Scope

1. **Expand Dataset**  
   Include diverse demographics and nuanced emotions

2. **Optimize for Edge Devices**  
   Use quantization, pruning, and TPU acceleration

3. **Multimodal Emotion Recognition**  
   Integrate audio, text, or physiological signals with FER

4. **Adaptive Learning Techniques**  
   Apply online/federated learning to update models dynamically

---

## 📚 References

- Jenisha A, Aleesha Livingston, *EPRA IJRD*, Vol. 8, Issue 7, July 2023
- [MobileNets: Efficient CNNs for Mobile Vision Applications (arXiv:1704.04861)](https://arxiv.org/abs/1704.04861)

---
