# 🧠 PulseAI – Control Robots with Muscle Signals

Transform EMG muscle activity into real-time robotic arm control using AI.

[![License](https://img.shields.io/badge/License-MIT-blue)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8+-yellow)](https://www.python.org)

---

## 📌 What is PulseAI?

**PulseAI** is a smart tool that reads **EMG signals** from human muscles and uses **AI** to control robotic arms. Originally built as a graduation project, PulseAI makes medical robotics more accessible for assistive tech applications.

---

## 🚀 Features

- 🎯 **AI Classifiers** – SVM, KNN, MLP, LDA, Logistic Regression  
- 🧼 **Signal Preprocessing** – Filters, normalization, and segmentation  
- 🧪 **Feature Extraction** – Extract key metrics from EMG data  
- 📈 **Data Visualization** – View signals and model performance  
- 🤖 **Robot Control** – Real-time robotic arm control  
- 🔧 **Custom Pipelines** – Easily configurable via `config.yaml`  
- 📂 **Multi-format Data Loader** – Supports CSV and more  

---

## 🛠️ Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Clone the Repo
```bash
git clone https://github.com/hussienmohaemd/PulseAI.git
cd PulseAI
```

### 3. Run the Full System
```bash
python src/core/application.py --config=config.yaml
```

---

## 👨‍💻 Code Snippets

**Load EMG Data**
```python
from src.preprocessing.load_data import LoadData
data = LoadData('data/', 'csv').extractdata(0)
```

**Preprocess & Normalize**
```python
from src.preprocessing.filters import FilterBank
filtered = FilterBank(50, 250, 50, 20).apply_filters(data)
```

**Extract Features & Train**
```python
from src.core.feature_extraction import FeatureExtractor
from src.core.classifiers import train_model
features = FeatureExtractor.extract_features(filtered)
model, acc = train_model(features, labels)
```

**Control the Robot**
```python
from src.core.application import control_robotic_arm
control_robotic_arm(classified_emg_signals)
```

---

## 📁 Project Structure
```
PulseAI/
├── src/
│   ├── core/            # Classification, features, control logic
│   ├── preprocessing/   # Filters, normalization, data loader
│   ├── visualization/   # Plotting tools
│   └── utils/           # Helper functions
├── docs/                # Documentation
├── tests/               # Unit tests
├── config.yaml          # Pipeline config
├── requirements.txt     # Python dependencies
└── README.md            # This file
```

---

## 📚 Documentation

- Full details in `docs/documentation.pdf`
- API reference (in progress): `docs/api_reference.md`

---

## 📬 Contact

- **Author**: Hussein Mohamed  
- **Issues**: [GitHub Issues](https://github.com/hussienmohaemd/PulseAI/issues)  
- **Facebook**: [facebook.com/hussein.mohamed](https://www.facebook.com/hussein.mohamed)

---

## 📄 License

MIT License © 2025 Hussein Mohamed

---

> ⚡ *PulseAI bridges human intention and machine action — one signal at a time.*
