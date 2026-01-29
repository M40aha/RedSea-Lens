# 🪸 RedSea-Lens: Automated Coral Health Monitoring using Deep Learning

## 🌊 Why This Project Matters
Coral reefs are the "rainforests of the sea," providing essential biodiversity and coastal protection. However, climate change and rising sea temperatures have led to widespread **coral bleaching**, a critical indicator of reef stress. Manual monitoring is time-consuming and labor-intensive. **RedSea-Lens** provides an automated solution using State-of-the-Art (SOTA) object detection to monitor coral health in real-time, specifically optimized for the unique and challenging optical conditions of the Red Sea.

---

## 🚀 Technical Excellence & Workflow
This project implements a professional machine learning pipeline that prioritizes **Data Integrity** and **Optical Accuracy**.

### 1. Optical Normalization (CLAHE Enhancement)
Underwater imagery often suffers from light scattering and low contrast. 
* **The Solution:** We implemented **CLAHE (Contrast Limited Adaptive Histogram Equalization)** in the `Lab` color space to enhance luminance without introducing noise.
* **The Impact:** This preprocessing normalized the unseen test images, allowing the model to detect textures and health indicators hidden by water turbidity.

### 2. Scientific Rigor (MD5 Hashing Protocol)
To ensure the model's reliability and eliminate "Data Leakage," a cryptographic verification system was used.
* **The Methodology:** Every image in the external test set was hashed using the **MD5 algorithm** and compared against **4,055 training samples**.
* **The Result:** The system confirmed **0 duplicates**, proving the model's high generalization capability on truly "unseen" data.



---

## 📊 Model Performance Metrics
The model was built using the **YOLOv8m (Medium)** architecture, striking a balance between speed and accuracy.

* **Model Summary:** 93 layers, 25,840,918 parameters.
* **Training Efficiency:** Completed 50 epochs in **2.125 hours** on a Tesla T4 GPU.
* **Class Performance:**
    * **Bleached Coral:** Achieved **53.5% mAP50**, demonstrating high sensitivity to critical health decline.
    * **Healthy Coral:** Achieved **42.1% mAP50**.
* **Deployment Readiness:** Inference speed of **8.0ms** per image.

---

## 🖼️ Final Inference Results (Unseen Data)
The model successfully identifies coral health status in high-turbidity environments with confidence scores reaching up to **0.65**:



* **Cyan Boxes:** Healthy Corals.
* **Blue Boxes:** Bleached/Stressed Corals.

---

## 📂 Repository Structure
* `RedSea_Lens.ipynb`: The primary training and validation environment.
* `Inference_Verification.ipynb`: Specialized notebook for preprocessing, MD5 hashing, and final testing.
* `weights.pt`: Optimized final weights (`best.pt`) for the Red Sea coral model.

---

## 📝 Conclusion
The **RedSea-Lens** project successfully demonstrates the power of deep learning in environmental conservation. By integrating advanced preprocessing (CLAHE) and rigorous data integrity protocols (MD5 Hashing), we achieved a reliable detection system capable of distinguishing coral health with high efficiency. Our YOLOv8m model showed significant sensitivity to bleached corals, providing a scalable and fast (8ms/image) tool for real-time reef monitoring.

## 🔭 Future Work
To further elevate the impact of RedSea-Lens, the following developments are planned:
* **Edge Deployment:** Optimizing the model for NVIDIA Jetson devices to be mounted on Autonomous Underwater Vehicles (AUVs) for real-time mapping.
* **Temporal Tracking:** Implementing object tracking to monitor the progression of bleaching in specific coral colonies over time.
* **Multi-Species Classification:** Expanding the dataset to identify specific coral species, enabling more granular ecological analysis.
* **Semantic Segmentation:** Moving from bounding boxes to pixel-level segmentation for precise surface-area measurement of coral cover.

---

## 🛠️ Installation & Usage
1. **Clone the repo:**
  
   git clone [https://github.com/M40aha/RedSea-Lens.git](https://github.com/M40aha/RedSea-Lens.git)
 
   2.Install dependencies:


pip install ultralytics opencv-python matplotlib


3.Run Inference:

from ultralytics import YOLO
model = YOLO('weights.pt')
results = model.predict(source='your_images/', save=True)
