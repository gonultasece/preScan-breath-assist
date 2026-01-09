# Literature Review: Breath-Hold Detection from Front-View Video

## Introduction

This document provides a literature review for the "Breath-Hold Detection from Front-View Video" project. The project aims to develop an offline, video-based system that uses a temporal deep learning pipeline to detect and analyze breath-hold events. This review covers key research areas relevant to the project, including video-based respiratory analysis, motion-based analysis, and spatio-temporal deep learning techniques.

## Video-Based Respiratory Analysis

The non-invasive nature of video-based respiratory analysis has made it a growing field of research, with applications ranging from meditation assistance to remote health monitoring. These methods can be broadly categorized based on the imaging modality (RGB or thermal) and the specific techniques used for signal extraction.

### RGB Video Analysis

Standard RGB cameras, such as those found in smartphones, offer an accessible way to capture respiratory information. Kashevnik et al. (2021) developed a system for meditation evaluation that uses a smartphone camera to detect chest keypoints. By applying an optical flow algorithm, they calculate the displacement between frames, which is then filtered and de-noised to create a chest movement signal. The respiratory rate is determined by identifying the peaks in this signal. This approach highlights the potential of using common consumer devices for respiratory analysis. Another technique involves analyzing intensity variations in specific facial regions, such as the chin, to estimate the respiratory rate, demonstrating that even subtle changes in video data can be leveraged for this purpose.

### Thermal Video Analysis

Thermal imaging provides an alternative, privacy-preserving modality for respiratory analysis. Mozafari et al. (2024) introduced an end-to-end deep learning approach that uses thermal video to estimate the respiratory rate. Their method employs a Detection Transformer (DeTr) to identify the facial region of interest, followed by 3D Convolutional Neural Networks (CNNs) and bi-directional Long Short-Term Memory (LSTM) networks to process the video data. A key innovation in their work is a novel loss function based on negative maximum cross-correlation, which accounts for the phase shift between the respiratory signal measured by a respiratory effort belt and the signal extracted from the video.

## Motion-Based Analysis

Motion-based analysis is a critical component of video-based respiratory monitoring, as it allows for the detection of the subtle movements associated with breathing. Two key techniques in this area are optical flow and keypoint detection.

### Optical Flow

Optical flow algorithms are used to estimate the motion of objects between consecutive frames of a video. In the context of respiratory analysis, optical flow can be used to track the movement of the chest and abdomen. Kashevnik et al. (2021) use the SelFlow convolutional neural network to estimate optical flow, which is then used to calculate the displacement of the chest. This approach allows for the detection of even small, pixel-scale movements, which is essential for accurate respiratory monitoring.

### Keypoint Detection

Keypoint detection, also known as pose estimation, is the process of identifying the locations of specific anatomical points on the human body. These keypoints can then be tracked across frames to analyze movement. The use of neural networks for keypoint detection has become increasingly common. For example, the system developed by Kashevnik et al. (2021) uses a neural network to identify the coordinates of various body parts, including the thorax. This information is then combined with optical flow data to calculate the absolute displacement of the chest.

## Spatio-Temporal Deep Learning

Spatio-temporal deep learning models are designed to process data that has both spatial and temporal dimensions, making them well-suited for video analysis. These models are capable of learning features from both the content of individual frames (spatial) and the way the content changes over time (temporal).

### 3D Convolutional Neural Networks (3D CNNs)

3D CNNs are an extension of traditional 2D CNNs that are commonly used for image analysis. Instead of operating on 2D images, 3D CNNs use 3D kernels to process video data, allowing them to simultaneously capture both spatial and temporal information. Mozafari et al. (2024) use a shallow 3D CNN in their thermal video-based respiratory analysis system to extract short-term spatio-temporal features. The use of a shallow network helps to keep the computational complexity low, which is important for real-time applications.

### Long Short-Term Memory (LSTM) Networks

LSTM networks are a type of recurrent neural network (RNN) that is specifically designed to handle long-term dependencies in sequential data. In the context of video analysis, LSTMs can be used to model the temporal relationships between frames. Mozafari et al. (2024) use a bi-directional LSTM to process the output of their 3D CNN, which allows their model to capture both forward and reverse temporal relationships in the video data. This combination of a 3D CNN and a bi-directional LSTM allows the model to effectively learn both short-term and long-term spatio-temporal features.
