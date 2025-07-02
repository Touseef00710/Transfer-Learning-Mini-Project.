# 🧠 Transfer Learning Showdown: MobileNetV2 vs ResNet50

## 📌 Objective
The objective of this mini project is to compare two popular pre-trained CNN architectures and apply transfer learning on a small image classification task using one of them.

---

## 📊 Model Comparison

| Feature               | MobileNetV2      | ResNet50          |
|-----------------------|------------------|-------------------|
| Input Image Size      | 224×224×3        | 224×224×3         |
| Parameters            | ~3.5 million     | ~25.6 million     |
| Layers / Depth        | ~53              | 50                |
| ImageNet Accuracy     | ~71.8%           | ~76.0%            |
| Model Size (MB)       | ~14 MB           | ~98 MB            |
| Inference Speed (CPU) | ~75 ms/image     | ~100–120 ms/image |

---

## ✅ Selected Model: MobileNetV2

### 📌 Justification
MobileNetV2 was selected for its efficiency in small-scale image classification tasks. It has significantly fewer parameters compared to heavier models like ResNet50, resulting in faster training and inference. Despite being lightweight, it still offers competitive ImageNet accuracy (~71.8%).

---

## 📦 Dataset Used
- **CIFAR-10**
- Contains 60,000 32×32 color images in 10 classes, with 6,000 images per class.
- Resized to **224×224** for compatibility with pre-trained models.

---

## 🔁 Transfer Learning Workflow

1. **Data Preprocessing**
   - Resize images to 224×224
   - Normalize images (0–1 scale)

2. **Load Pretrained Model**
   - MobileNetV2 from `tf.keras.applications` (without top layer)
   - Freeze base layers

3. **Custom Classifier Head**
   - `GlobalAveragePooling2D` → `Dropout` → `Dense(10, softmax)`

4. **Training**
   - 30 epochs initial training with `EarlyStopping`, `ReduceLROnPlateau`
   - Fine-tuned last ~50 layers with reduced learning rate

5. **Evaluation**
   - Final accuracy: **~43%** on test data
   - Confusion matrix & training/validation plots generated

---

## 📈 Results

- **Initial Accuracy**: **~10%**
- **After Fine-Tuning**: **~43%**
- Good generalization with minimal overfitting
- Lightweight model suitable for deployment

---


## 🚀 Requirements

- Python 3.8+
- TensorFlow 2.10+
- tensorflow-datasets
- matplotlib, seaborn

Install with:

```bash
pip install tensorflow tensorflow-datasets matplotlib seaborn


## Contact @ TouseefAhmed00710@gmail.com
