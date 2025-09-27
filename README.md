# MNIST Model Iterations – ERA v4 S6

This repository documents the iterative development of a CNN-based model for the MNIST dataset.  
The goal was to progressively reduce parameters while maintaining or improving accuracy, and to experiment with techniques such as Batch Normalization, Global Average Pooling (GAP), and Learning Rate Scheduling.  

---

## Iteration 1
- **Target**:  
  - Build the initial model skeleton.  
  - Stay below **60k parameters**.  
  - Achieve ~**98% train/test accuracy** consistently.  
  - Avoid Fully Connected layers.  

- **Results**:  
  - Parameters: **53,000**  
  - Train Accuracy: **99.3%**  
  - Test Accuracy: **98.9%**

- **Analysis**:  
  - Train accuracy still has scope for improvement.  
  - Signs of **overfitting** (train > test accuracy).  

- **Notebook**: [NN_Basic_Structure.ipynb](https://github.com/nitin-vig/ERAv4S6/blob/main/NN_Basic_Structure.ipynb)

---

## Iteration 2
- **Target**:  
  - Reduce parameters to **<12k**.  
  - Push **Test Accuracy → 99%**.  
  - Narrow the gap between train and test accuracy.  

- **Results**:  
  - Parameters: **7,070** (achieved mainly via **Global Average Pooling**)  
  - Accuracy: **>99.2%** after 10 epochs  
  - Overfitting largely resolved  

- **Analysis**:  
  - **Batch Normalization** boosted early accuracy (high accuracy from the first epoch).  
  - **Dropout** worsened both train and test accuracy → removed.  
  - Added an extra Conv layer in Block 2, which improved accuracy.  

- **Notebook**: [MNIST_Reduced_size_After_Basic_Structure.ipynb](https://github.com/nitin-vig/ERAv4S6/blob/main/MNIST_Reduced_size_After_Basic_Structure.ipynb)

---

## Iteration 3
- **Target**:  
  - Push accuracy to **99.4%** while keeping parameters low.  

- **Results**:  
  - Parameters: **7,070**  
  - Accuracy: **>99.4%** (train & test) after 11 epochs  

- **Analysis**:  
  - Strong structure, but **overfitting visible**.  
  - The key change from Iteration 2 → **Learning Rate Scheduler**.  
  - Since Iteration 2 stabilized around 99.2% after 10 epochs, lowering LR after 10 epochs fine-tuned the model for higher accuracy.  

- **Notebook**: [MNIST_Final_Version.ipynb](https://github.com/nitin-vig/ERAv4S6/blob/main/MNIST_Final_Version.ipynb)

---

## Summary
- Iteration 1: **53k params**, ~**98.9% test accuracy**  
- Iteration 2: **7k params**, ~**99.2% test accuracy**  
- Iteration 3: **7k params**, ~**99.4% test accuracy**  

The project demonstrates how careful architectural choices (GAP, BN, reduced parameterization) and optimization strategies (scheduler tuning) can yield compact yet highly accurate CNN models for MNIST.  

---

