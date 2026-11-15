Prism AI: Real-Time Assistive Object Detection 👁️

📌 Project Overview
Prism AI is a computer vision-based assistive technology designed for real-world object recognition. The system leverages a custom-trained deep learning model to accurately detect specific everyday objects in real-time, aiming to aid visually impaired individuals in navigating their surroundings safely and independently.

⚙️ Tech Stack
* **Language:** Python
* **Deep Learning Framework:** PyTorch, Ultralytics (YOLOv11)
* **Data Annotation:** Label Studio
* **Environment & Hardware:** Google Colab, Cloud-based Tesla T4 GPU

📊 Dataset & Classes
A custom dataset was curated and manually annotated using **Label Studio** to generate precise YOLO-format bounding boxes. The model is trained to detect 5 specialized classes:
1. `Fire` (Hazard detection)
2. `Candle` (Hazard/Utility)
3. `Lipstick` (Personal care)
4. `Comb` (Personal care)
5. `Slippers` (Navigation/Obstacles)

🚀 Model Training & Performance
* **Architecture:** Trained a custom **YOLO11s** architecture from scratch to stabilize learning on a constrained dataset.
* **Epochs & Resolution:** Trained for **100 epochs** at 640px image resolution.
* **Accuracy:** Delivered robust performance with an **85-89% detection accuracy** across varied lighting and background conditions.
* **Speed:** Achieved a highly efficient inference speed of **~15ms per image**, ensuring seamless real-time video stream processing.

🛠️ How to Run

1. Install Dependencies:
```bash
pip install ultralytics torch torchvision

2. Run Inference using custom weights (best.pt):

Python
from ultralytics import YOLO

Load the custom-trained model
model = YOLO("best.pt")

Perform object detection on an image
results = model.predict(source="candle.jpg", show=True, save=True)
