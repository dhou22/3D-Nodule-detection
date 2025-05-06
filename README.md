# 🫁 Lung Nodule Detection System

Welcome to the **Lung Nodule Detection System**, an advanced deep learning-based framework for detecting and classifying pulmonary nodules in CT scans. This system leverages the 3D Dual Path Network (DPN) architecture, inspired by the DeepLung framework detailed in ["DeepLung: Deep 3D Dual Path Nets for Automated Pulmonary Nodule Detection and Classification"](https://arxiv.org/abs/1801.09555).
![image](https://github.com/user-attachments/assets/3140d0d4-41d8-4c92-82c5-c373a481a717)


---

## 🚀 Project Overview

This repository provides a comprehensive pipeline for automating lung nodule detection and classification, encompassing:

1. **Nodule Detection** 🔍: Using a 3D Faster R-CNN with dual path blocks for identifying lung nodules in CT scans.
2. **Nodule Classification** 🔬: Leveraging a 3D DPN combined with Gradient Boosting Machines (GBM) for malignancy prediction.

### 🧠 Key Features

✅ **3D Dual Path Networks**: Combines residual learning and dense connections for efficient feature extraction.  
✅ **Modular Codebase**: Clean structure for preprocessing, model loading, and inference.  
✅ **Web Application**: Flask-based UI for uploading scans and viewing predictions.  
✅ **Monitoring & Observability**: Prometheus and Grafana for performance tracking.  
✅ **Containerization**: Dockerized deployment for consistent runtime environments.  
✅ **Comprehensive Testing**: Includes unit and integration tests for reliability.  

---

## 🏗️ Project Architecture

```plaintext
📂 lung-nodule-detection/
├── 📂 app/                # Main application code
│   ├── 📂 static/         # Static assets (CSS, JS)
│   ├── 📂 templates/      # HTML templates for web UI
│   ├── 📂 models/         # Trained model storage
│   ├── 📂 utils/          # Utility scripts (preprocessing, inference)
│   ├── 📂 monitoring/     # Monitoring and metrics
│   ├── 📜 __init__.py     # Flask app initialization
│   ├── 📜 routes.py       # API routes and logic
├── 📂 tests/              # Unit and integration tests
├── 📜 requirements.txt    # Python dependencies
├── 📜 Dockerfile          # Container definition
├── 📜 docker-compose.yml  # Multi-service orchestration
├── 📜 Makefile            # Automation commands
├── 📜 README.md           # Project documentation
```

---

## 📌 Project Phases

### 1️⃣ Environment Setup

#### Project Initialization
```bash
# Create project directory and virtual environment
mkdir lung-nodule-detection
cd lung-nodule-detection
python -m venv venv
source venv/bin/activate
```

#### Install Dependencies
```bash
pip install flask torch torchvision numpy pandas matplotlib scikit-image scipy opencv-python prometheus-client gunicorn flask-wtf flask-cors
pip install -U mlflow tensorboard pytest pytest-cov
pip freeze > requirements.txt
```

---

### 2️⃣ Model Handling

#### Model Loading
- Utility to load the 3D DPN model from `.pth` files.
- Ensures compatibility with the model architecture.

#### Preprocessing CT Scans
- Steps include:
  - **Normalization**: Adjust pixel intensity to a standard scale.
  - **Resizing**: Ensure input dimensions match the model's expected size.
  - **Dimensionality Addition**: Add batch and channel dimensions.

#### Inference
- Run predictions on preprocessed scans to classify nodules as benign or malignant.

---

### 3️⃣ Web Application

#### Flask-based UI
- **File Uploads**: Upload `.raw` CT scan files for analysis.
- **Results Visualization**: View predictions, confidence levels, and download detailed reports.

![image](https://github.com/user-attachments/assets/e75df5f1-40ae-4255-8e9d-991a8a10ac24)


---

### 4️⃣ Monitoring & Observability

#### Prometheus & Grafana Integration
- **Metrics Tracked**:
  - Total inference requests.
  - Inference duration and errors.
  - Active requests and model load time.
- **Dashboards**: Visualize system performance and application health.

![Monitoring Dashboard](https://github.com/user-attachments/assets/cfb919a0-e4e9-4155-b9f0-fd1f83f91298)

---

### 5️⃣ Containerization

#### Dockerized Deployment
- **Dockerfile**: Encapsulates the application and dependencies.
- **docker-compose.yml**: Orchestrates multi-container setups (web app, Prometheus, Grafana).

![Docker Deployment](https://github.com/user-attachments/assets/6ae5d485-b98b-4d1d-a983-8cac76c298c9)

---

### 6️⃣ Testing

#### Unit Tests
- Verify preprocessing utilities and model loading.

#### Integration Tests
- Validate API endpoints and end-to-end workflows.

---

## 📦 Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/dhou22/Lung-Nodule-Detection.git
cd lung-nodule-detection
```

### 2️⃣ Environment Setup
```bash
# Create and activate virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 3️⃣ Run Flask App
```bash
# Start the Flask application
python app/__init__.py
```

Visit the web app at [http://localhost:5000](http://localhost:5000).

### 🧪 Run Tests
```bash
pytest tests/
```

---

## 🐳 Docker Deployment

### Build and Run Containers
```bash
docker-compose up --build
```

- Web App: [http://localhost:5000](http://localhost:5000)
- Monitoring Dashboard: [http://localhost:3000](http://localhost:3000)

---

## 📡 API Endpoints

| Method | Endpoint       | Description                   |
|--------|----------------|-------------------------------|
| GET    | `/health`      | Check API status              |
| POST   | `/upload`      | Upload CT scan for prediction |
| GET    | `/report/<id>` | Download prediction report    |

---

## 🛠️ Makefile Commands

| Command           | Description                        |
|--------------------|------------------------------------|
| `make install`     | Install dependencies              |
| `make test`        | Run unit tests                    |
| `make run`         | Start Flask app                  |
| `make docker-build`| Build Docker image                |
| `make docker-run`  | Run Docker container              |
| `make monitor`     | Start monitoring services         |

---

## 📈 Model Performance

- **Accuracy**: Achieves radiologist-level detection rates.
- **Efficiency**: Optimized for high-resolution CT scans with reduced computational overhead.

![Model Metrics Dashboard](https://github.com/user-attachments/assets/4bc0340f-5af5-428d-a965-0dd1fdb3c789)

---

## 📜 License

Licensed under **MIT License**.  
© 2025 **Dhouha Meliane**  
Email: [dhouhameliane@esprit.tn](mailto:dhouhameliane@esprit.tn)
