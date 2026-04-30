# Rice Leaf Disease Classification using Deep Learning

## Project Overview
This project focuses on detecting and classifying rice leaf diseases using deep learning and transfer learning techniques. The goal is to build an accurate and efficient model that can classify rice leaf images into three disease categories:

- Bacterial Leaf Blight  
- Brown Spot  
- Leaf Smut  

The project compares multiple CNN architectures and demonstrates that transfer learning significantly outperforms training from scratch on small datasets.

---

## Key Highlights
- Used Transfer Learning on pre-trained ImageNet models  
- Compared 5 models:
  - MobileNetV3Large (Best)
  - ResNet50V2
  - EfficientNetV2B0
  - DenseNet121
  - Custom CNN (baseline)
- Achieved 95.83% accuracy with MobileNetV3Large  
- Applied data augmentation to handle small dataset  
- Implemented two-phase training strategy  

---

## Dataset Information
- Total Images: 120  
- Classes: 3 (40 images each)  
- Train Split: 80% (96 images)  
- Validation Split: 20% (24 images)  

### Data Augmentation Techniques
- Random Flip (Horizontal & Vertical)
- Rotation (±10°)
- Zoom
- Contrast Adjustment

---

## Models Used

| Model              | Type      | Accuracy | Parameters |
|--------------------|----------|----------|------------|
| MobileNetV3Large   | Transfer | 95.83%   | 3.12M      |
| ResNet50V2         | Transfer | 91.67%   | 23.83M     |
| EfficientNetV2B0   | Transfer | 91.67%   | 6.08M      |
| DenseNet121        | Transfer | 87.50%   | 7.17M      |
| Custom CNN         | Scratch  | 45.83%   | 2.52M      |

---

## Methodology

### Training Strategy (2-Phase)
1. Phase 1 (Warm-up)
   - Freeze backbone
   - Train classifier head
   - Learning Rate: 1e-3

2. Phase 2 (Fine-tuning)
   - Unfreeze top layers
   - Fine-tune model
   - Learning Rate: 1e-5

---

### Model Architecture
- Pre-trained CNN backbone
- Global Average Pooling
- Dense Layer (128 units, ReLU)
- Dropout (0.3)
- Softmax Output (3 classes)

---

## Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score

---

## Best Model: MobileNetV3Large
- Accuracy: 95.83%
- F1 Score: 95.86%
- Lightweight and efficient (3.12M parameters)
- Best performance vs complexity trade-off

---

## Key Observations
- Transfer learning models performed significantly better
- Custom CNN failed due to small dataset (underfitting)
- MobileNetV3Large showed:
  - Fast convergence
  - Stable validation performance
  - High generalization

---

## Limitations
- No separate test set (validation used for evaluation)
- Small dataset size
- No "Healthy" class included

---

## Future Improvements
- Add more data (including healthy leaves)
- Use test dataset for unbiased evaluation
- Apply test-time augmentation
- Deploy model on mobile devices
- Use model compression techniques

---

## Tech Stack
- Python 3.10
- TensorFlow / Keras
- NumPy, Matplotlib
- Scikit-learn

---

## Workflow
Data Collection → Preprocessing → Augmentation → Training → Evaluation

---

## Contributors
- Mukul Ghai  
- Lakshita Gupta  
- Saarthi Arora  
- Ishaan Sharma  

---

## References
- ImageNet CNN Paper (Krizhevsky et al.)
- ResNet (He et al.)
- MobileNet (Howard et al.)
- Deep Learning for Plant Disease Detection

---

## Conclusion
Transfer learning is the most effective approach for small-scale agricultural datasets.  
MobileNetV3Large provides the best balance between accuracy, speed, and efficiency, making it suitable for real-world deployment.
