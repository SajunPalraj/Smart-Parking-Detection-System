
# 🚗 **SMART PARKING DETECTION SYSTEM**

An AI-based solution to monitor parking availability using a static image. This project utilizes Python and OpenCV to detect free and occupied parking spots with high accuracy.

---

## 📚 **TABLE OF CONTENTS**

- 📌 [**Introduction**](#-introduction)
- ⚙️ [**Installation & Dependencies**](#-installation--dependencies)
- 💡 [**Usage Instructions**](#-usage-instructions)
- 🔍 [**Code Description**](#-code-description)
- 🔧 [**Working Mechanism**](#-working-mechanism)
- 📦 [**File Structure**](#-file-structure)
- 🎯 [**Use Cases**](#-use-cases)
- 🧪 [**Testing**](#-testing)
- 🔒 [**Limitations & Future Enhancements**](#-limitations--future-enhancements)
- ✅ [**Conclusion**](#-conclusion)
- 🧠 [**Contributors**](#-contributors)
- 📝 [**License**](#-license)

---

## 📌 **INTRODUCTION**

The **Smart Parking Detection System** aims to simplify the process of identifying empty and occupied parking spaces from an image. Unlike real-time systems that rely on video, this project is designed to work with single images, making it ideal for research and cloud environments like Google Colab. The application detects spots using computer vision techniques, displaying them with red and green indicators.

---

## ⚙️ **INSTALLATION & DEPENDENCIES**

### 🛠️ **Step-by-Step Setup in Google Colab**
1. Upload the main `.ipynb` notebook.
2. Upload:
   - A parking lot image (JPEG/PNG).
   - A Pickle file containing coordinates: `CarParkPos.pkl`.

### 📦 **Install Dependencies**
Use the following command in a Colab cell:
```bash
!pip install opencv-python-headless cvzone numpy

💻 Run Locally (Optional)

If running on a local machine:

pip install opencv-python cvzone numpy


---

💡 USAGE INSTRUCTIONS

1. Open the notebook in Google Colab.


2. Run all setup cells.


3. Upload your parking lot image.


4. Upload the CarParkPos.pkl file (generated manually or via setup tool).


5. Run the detection cell to display the image with status boxes.


6. Green = Free, Red = Occupied.




---

🔍 CODE DESCRIPTION

cv2.VideoCapture() was replaced with image upload logic.

pickle is used to store and retrieve slot coordinates.

The checkParkingSpace() function:

Crops and processes each slot area.

Uses adaptive thresholding to segment features.

Applies pixel counting to determine occupancy.

Draws rectangles and overlays occupancy status.



if count < 900:
    color = (0, 255, 0)  # Free
else:
    color = (0, 0, 255)  # Occupied


---

🔧 WORKING MECHANISM

1. Image Preprocessing:

Convert to grayscale.

Apply Gaussian blur and adaptive thresholding.

Remove noise with median blur and dilation.



2. Slot Analysis:

Loop through all parking slots using saved coordinates.

Count non-zero pixels (white pixels after thresholding).

Determine status based on a pixel threshold (e.g., 900).



3. Display Output:

Overlay colored rectangles and slot indexes.

Show total free slots in the top-left corner.





---

📦 FILE STRUCTURE

SmartParking/
│
├── SmartParking.ipynb        # Main notebook
├── CarParkPos.pkl            # Pickle file with parking coordinates
├── test_parking_lot.jpg      # Sample parking image
└── README.md                 # Project documentation


---

🎯 USE CASES

🅿️ Shopping Malls – Help users quickly identify vacant spots.

🛫 Airports – Manage large-scale parking lots with accuracy.

🏢 Offices – Monitor daily usage and optimize space.

🚗 Smart Cities – Integrate with IoT for automated parking management.

🧪 Academic Projects – Great base for CV/ML education.



---

🧪 TESTING

Multiple images tested with different lighting and orientations.

Accuracy improves when:

Image is captured top-down or with a known perspective.

Parking slots are clearly separated.

Green/Red color thresholds are calibrated.




---

🔒 LIMITATIONS & FUTURE ENHANCEMENTS

❗ Limitations:

Requires predefined slot coordinates (manual setup).

Accuracy depends on lighting and image quality.

Limited to static images (not live feeds).


🚀 Future Enhancements:

Integrate automatic slot detection using contour analysis.

Extend to real-time video input with YOLO or SSD.

Host on a cloud service for web-based deployment.

Add mobile responsiveness or integration into a mobile app.



---

✅ CONCLUSION

This project delivers an efficient and modular solution for detecting parking slot availability using computer vision. Built with simplicity and modularity in mind, it is an excellent starting point for real-time smart parking systems.

