# RedSea-Lens
Automated Coral Health Monitoring using Deep Learning


🌊 Overview
RedSea-Lens is a computer vision-based project designed to automate the detection and monitoring of coral bleaching in the Red Sea. Leveraging state-of-the-art Deep Learning architectures, this project aims to support marine biologists and environmental researchers in assessing coral reef health with high precision and efficiency.

This initiative aligns with the goals of Saudi Vision 2030 and the Saudi Green Initiative, focusing on the preservation of marine biodiversity and sustainable ecosystem management.

🔬 Methodology
1. Data Preprocessing & Enhancement
To overcome the challenges of underwater imaging—such as light scattering and low contrast—the project implements CLAHE (Contrast Limited Adaptive Histogram Equalization). This technique enhances local contrast and brings out fine textures in coral tissues, significantly improving the model's feature extraction capabilities.

2. Model Architecture
The project utilizes the YOLOv8m (Medium) architecture from Ultralytics. The "Medium" variant was selected to provide an optimal balance between:

Inference Speed: Essential for potential real-time field deployment.

Detection Accuracy (mAP): Crucial for distinguishing between healthy corals and early-stage bleaching.

3. Hyperparameter Optimization
To achieve superior results, the model was trained with the following configurations:

Input Resolution: 640x640 pixels.

Training Duration: 50 Epochs.

Optimization: Stochastic Gradient Descent (SGD) with a dynamic learning rate.

📊 Evaluation & Results
The model's performance is evaluated using standard Computer Vision metrics:

mAP@50: Measures the mean Average Precision at a 0.5 Intersection over Union (IoU) threshold.

Precision & Recall Curves: Used to analyze the trade-off between false positives and false negatives.

Confusion Matrix: Provides insights into the classification performance for the classes: Healthy and Bleached.

🛠 Tech Stack
Language: Python 3.10+

Frameworks: PyTorch, Ultralytics YOLOv8

Image Processing: OpenCV, Matplotlib

Data Management: Roboflow

🚀 Future Work
Integration with Autonomous Underwater Vehicles (AUVs) for automated reef surveying.

Expanding the dataset to include diverse Red Sea coral species.
