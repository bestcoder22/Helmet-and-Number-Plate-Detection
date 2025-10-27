# Helmet-and-Number-Plate-Detection

## 🧠 Description
This project focuses on detecting traffic violations by identifying motorbike riders who are not wearing helmets and extracting their license plate information.  
It integrates three key models:
1. **Moto_Detect_Model** – Detects motorcycles in traffic images.
2. **Helmet_LP_Detect_Model** – Detects helmets, no-helmet cases, and license plates.
3. **ReadLP_Model** – Reads license plate text using OCR techniques.

These models are combined in a logical pipeline to enable real-time helmet violation detection from videos.

---

## ⚙️ Overview and Explanation

### **Model 1: Detect Motorcycle using YOLOv8**
- **Input:** Traffic images containing multiple vehicles.  
- **Output:** Bounding boxes around motorcycles.  
- **Implementation Approach:**  
  - Dataset collected via personal cameras and processed into frames.
  - Labeled using **Roboflow** to create a clean motorcycle dataset.
  - Trained with **YOLOv8**, achieving strong motorcycle detection accuracy.
  - Added a screen threshold to filter out motorcycles too far from the camera for reliable plate recognition.

---

### **Model 2: Detect Helmet and License Plate using YOLOv8**
- **Input:** Cropped motorcycle images from Model 1 output.  
- **Output:** Bounding boxes for **Helmet**, **No-Helmet**, and **License Plate**.  
- **Implementation Approach:**  
  - Extracted motorcycles using bounding box coordinates.
  - Created a helmet dataset by combining back-head images and manually labeled helmet/no-helmet examples.
  - Used **Roboflow** for labeling and trained YOLOv8 to detect helmets and license plates effectively.

---

### **Model 3: Read License Plate using VGG16 (OCR Process)**
- **Input:** Cropped license plate images.  
- **Output:** Alphanumeric text of the license plate.  
- **Implementation Approach:**  
  - Used a custom character dataset (A–Z, 0–9) for training.
  - Applied preprocessing (contrast enhancement, noise reduction, contour extraction).
  - Segmented license plate characters and passed them through **VGG16** for recognition.

---

## 💻 GUI Design
A simple GUI was developed using **PyQt5**, allowing users to:
- Upload traffic videos.
- Detect helmet violations in real time.
- Display detected violations and corresponding license plates.
- Generate reports and statistics based on time and location.

---

## 📂 Project and Dataset Information
- **Traffic Dataset:** [MotoBike Detection Dataset](https://universe.roboflow.com/cdio-zmfmj/motobike-detection)  
- **Helmet and License Plate Dataset:** [Helmet & LP Detection Dataset](https://universe.roboflow.com/cdio-zmfmj/helmet-lincense-plate-detection-gevlq)

---

## 🧰 Key Technologies Used
- **YOLOv8**
- **VGG16**
- **Python**
- **Roboflow**
- **PyQt5**
- **OpenCV**
- **TensorFlow**

---

## 🚀 Features
- Real-time helmet and license plate detection.
- Automatic recognition of license plate text.
- GUI for easy user interaction and monitoring.
- Scalable and efficient pipeline using YOLOv8 and VGG16.

---
