🪸 RedSea-Lens: Advanced Coral Reef Health Detection
RedSea-Lens is an end-to-end computer vision pipeline designed to monitor and classify coral reef health in the Red Sea. Leveraging the YOLOv8m architecture, the project focuses on identifying Healthy vs. Bleached corals with high precision, even in challenging underwater optical conditions.

🚀 Key Technical Highlights
Unlike standard detection projects, this repository implements a rigorous data science workflow:

Image Enhancement Layer: Integration of CLAHE (Contrast Limited Adaptive Histogram Equalization) to normalize underwater light scattering.

Data Integrity Protocol: A custom MD5 Hashing system to verify the uniqueness of test data and prevent "Data Leakage".

Symmetric Preprocessing: Applied identical enhancement parameters to both training and inference sets for maximum consistency.

🛠️ The Pipeline Architecture
1. Preprocessing & Contrast Enhancement
Underwater imagery often suffers from low contrast and blue-green color casts. We implemented a CLAHE-based pipeline in the Lab color space to:

Enhance the visibility of coral textures without amplifying noise.

Standardize inputs for the YOLOv8 model, leading to better feature extraction.

2. Rigorous Validation (The Hashing Step)
To ensure the model’s reliability, every image in the external test set was hashed using the MD5 algorithm.

Integrity Check: Hashes of unseen images were compared against the training database.

Result: Confirmed 0% overlap, proving the model's ability to generalize to truly new environments.

📊 Model Training & Performance
Architecture: YOLOv8m (Medium).

Training Duration: 2.125 hours on Tesla T4 GPU.

Dataset: 4,000+ localized coral images.

Key Metrics (at 50 Epochs):

Overall mAP50: 47.8%.

Bleached Coral Precision: 53.5% (High sensitivity to critical health indicators).

Inference Speed: ~8.0ms per image.

🖼️ Inference Results
The following results demonstrate the model's performance on the unseen, enhanced test set:

The model successfully identifies coral clusters with confidence scores up to 65%, effectively distinguishing between healthy (cyan) and bleached (blue) colonies despite the presence of biological noise (fish, shadows).

📂 Project Structure
Model_Training.ipynb: The primary training environment.

Inference_Verification.ipynb: Dedicated notebook for CLAHE enhancement, Hashing, and final testing.

weights/: Contains the optimized best.pt model file.

💡 Conclusion
This project demonstrates that health monitoring of Red Sea corals can be automated with high reliability through strategic preprocessing and state-of-the-art object detection models.
