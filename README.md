# Image Classification Hackathon: Predicting Icon Types from 32x32 Grayscale Images

This project involves developing a deep learning model to predict icon types based on 32x32 grayscale images. Using PyTorch, a Convolutional Neural Network (CNN) model was designed and trained, and the model's performance was evaluated using K-Fold cross-validation, achieving a high accuracy of 0.992.

## Model Design
- After experimenting with **EfficientNet** and **ResNet**, the **CNN model** was chosen for optimization based on performance and training speed.
- The model consists of 4 **Conv2D** layers, **LeakyReLU** activation functions, and **Dropout** to prevent overfitting and to efficiently extract features.

## Performance Optimization Attempts
- **Data Augmentation**:
  - **CutMix** and **Mixup**: These techniques were used to mix images, helping the model learn to be **robust** to various transformations.
  - **SWA (Stochastic Weight Averaging)**: The model's final performance was improved by averaging the weights from multiple epochs.
  - **TTA (Test Time Augmentation)**: Data augmentation was applied during testing to further improve prediction performance.
- **K-Fold Cross Validation**: **Stratified K-Fold** was used for 10-fold repeated training to enhance the model's stability and performance, with the final predictions being aggregated using the hard voting method.
- **Model Ensemble**: **CNN**, **EfficientNet**, and **ResNet** were experimented with for performance and speed tradeoffs, but the optimized **CNN model** proved to be the most effective.
- **Handling Confused Classes**: For classes the model struggled with (e.g., airplane and police car), a separate **binary classifier** was trained to recheck predictions for those specific classes, improving accuracy.

## Final Results
- **Accuracy**: 0.992
- The optimized CNN model demonstrated high performance and stability, maximizing generalization performance through various augmentation techniques and ensemble strategies.

![image](https://github.com/user-attachments/assets/a79b42ed-71ac-4d02-85f4-32cd4dfef47a)
