# Day 29 - Deep Learning Basics

## Overview
On Day 29, we delved into the foundational concepts of Deep Learning, exploring various neural network architectures and their applications. Through practical examples, we built and trained models to solve regression and classification problems, solidifying our understanding of key deep learning techniques.

## Topics Covered

### 1. Introduction to Deep Learning
- **Neural Network Types:**
  - **Feed Forward Neural Networks (FFNNs):** Used for regression and classification tasks.
  - **Convolutional Neural Networks (CNNs):** Specialized for image-related tasks like classification and object detection.
  - **Recurrent Neural Networks (RNNs):** Designed for sequential data such as language modeling and speech recognition.
  - **Encoder-Decoder Architectures:** Applied in tasks like machine translation and semantic segmentation.
  - **Autoencoders:** Utilized for unsupervised learning tasks like dimensionality reduction and denoising.
  - **Generative Adversarial Networks (GANs):** Focused on generating realistic data, such as images.
  - **Deep Reinforcement Learning:** Combines deep learning with reinforcement learning for applications in robotics and game playing.

### 2. Practical Applications

#### Part 1: Boston Housing Price Prediction with FFNN
- **Dataset Overview:**
  - **Boston Housing Dataset:** 506 samples with 13 features each.
  - **Objective:** Predict the median value of owner-occupied homes.
- **Data Preprocessing:**
  - Normalization using training set statistics (mean and standard deviation).
- **Model Building:**
  - FFNN architecture with one hidden layer (20 neurons, ReLU activation).
  - Compiled with Adam optimizer and Mean Squared Error (MSE) loss function.
- **Model Training:**
  - Implemented early stopping to prevent overfitting.
  - Trained for up to 1000 epochs with a validation split of 10%.
- **Evaluation:**
  - Calculated Root Mean Square Error (RMSE) on both validation and test sets.
  - Achieved an RMSE of ~2.651 on the test set, placing 5th on the Kaggle leaderboard.

#### Part 2: Classification of MNIST Digits with CNNs
- **Dataset Overview:**
  - **MNIST Dataset:** 70,000 grayscale images of handwritten digits (28x28 pixels).
  - **Objective:** Classify each image into one of the 10 digit categories (0-9).
- **Data Preprocessing:**
  - Reshaped images to include channel dimension.
  - Scaled pixel values to the range [0, 1].
- **Visualization:**
  - Displayed sample images to verify data integrity.
- **Model Building:**
  - (Details to be covered in subsequent sessions.)

## Tools and Technologies
- **Frameworks:** TensorFlow, Keras
- **Libraries:** NumPy, Pandas, Matplotlib, Seaborn, OpenCV
- **Environment:** Google Colab recommended for ease of access and setup

## Key Takeaways
- **Neural Network Architectures:** Understanding the strengths and applications of different types of neural networks.
- **Model Training and Evaluation:** Importance of data preprocessing, model tuning, and using appropriate metrics to evaluate performance.
- **Practical Implementation:** Gained hands-on experience in building, training, and evaluating models for real-world datasets.

## Next Steps
- **We'll be preparing for the biggest challenge *200daysofDS***