# Emotion Detection Model

This repository contains a deep learning model for emotion detection based on the MobileNetV2 architecture.

## 🚀 Features
- Emotion classification using a pre-trained and fine-tuned MobileNetV2 model.
- Efficient inference for real-time emotion detection.

## 📂 Project Structure
- `models/`: Contains the trained model weights (`best_mobilenetv2.pth`).
- `requirements.txt`: List of dependencies needed to run the model.
- `README.md`: Project documentation.

## 🛠️ Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/emotion-detection.git
   cd emotion-detection
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## 💻 Usage

To use the model for emotion detection, load the weights from the `models/` directory into your MobileNetV2 architecture implementation.

```python
import torch
from torchvision import models

# Load MobileNetV2
model = models.mobilenet_v2(pretrained=False)
# Adjust final layer to match the number of emotion classes
model.classifier[1] = torch.nn.Linear(model.last_channel, num_classes)

# Load trained weights
model.load_state_dict(torch.load('models/best_mobilenetv2.pth'))
model.eval()
```

## 📝 License
This project is licensed under the MIT License.
