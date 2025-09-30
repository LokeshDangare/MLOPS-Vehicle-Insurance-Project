# 🚗 Vehicle MLOps Project

## 🌟 Overview

This project demonstrates a **complete MLOps workflow** for an end-to-end Machine Learning system on vehicle insurance system related data.
It covers everything from **data ingestion** → **validation** → **transformation** → **model training & evaluation** → **deployment on AWS with CI/CD**.

The goal is to **showcase modern MLOps practices** with cloud integration, automated pipelines, monitoring, and scalable deployment.

---

## 🔑 Key Features

* 📦 **Project Template Automation** with Python scripts (`template.py`)
* 🧩 **Local Package Management** via `setup.py` & `pyproject.toml`
* 🐍 **Virtual Environment & Dependencies** management with Conda + pip
* 🍃 **MongoDB Atlas** integration for scalable cloud database storage
* 📝 **Logging & Exception Handling** modules
* 📊 **EDA & Feature Engineering Notebooks** for exploration
* 📥 **Data Ingestion Pipeline** connected to MongoDB
* ✅ **Data Validation & Transformation** with schema checks
* 🤖 **Model Training, Evaluation, and Registry**
* ☁️ **AWS S3 Integration** for model storage and versioning
* 🐳 **Dockerized Application** ready for deployment
* 🔄 **CI/CD Pipeline** with GitHub Actions + Self-Hosted Runner on EC2
* 🌍 **Deployed Flask App** accessible via public IP on port 5000

---

## 🛠️ Tech Stack

* **Programming Language**: Python 3.11
* **Database**: MongoDB Atlas
* **Machine Learning**: Scikit-learn, Pandas, NumPy
* **Cloud**: AWS (IAM, S3, ECR, EC2)
* **Containerization**: Docker
* **Orchestration & CI/CD**: GitHub Actions, Self-Hosted Runner
* **App Framework**: Flask
* **Version Control**: Git + GitHub

---

## 📂 Project Structure

```
├── .github/workflows/        # GitHub Actions CI/CD workflows
├── artifacts/                # Generated artifacts (ignored in git)
├── notebook/                 # EDA, MongoDB demo notebooks
├── src/                      # Source code
│   ├── components/           # ML pipeline components
│   ├── configuration/        # DB & AWS configuration
│   ├── data_access/          # Data ingestion from MongoDB
│   ├── entity/               # Config & artifact entities
│   ├── aws_storage/          # S3 push/pull utilities
│   └── utils/                # Helper functions
├── static/                   # Web app static files
├── templates/                # HTML templates for Flask app
├── app.py                    # Flask application entry point
├── setup.py                  # Local package setup
├── pyproject.toml            # Dependency/project metadata
├── requirements.txt          # Python dependencies
├── Dockerfile                # Docker image definition
└── template.py               # Auto-create project structure
```

---

## ⚙️ Workflow

### 1. **Environment Setup**

```bash
conda create -n vehicle python=3.11 -y
conda activate vehicle
pip install -r requirements.txt
```

### 2. **MongoDB Integration**

* Setup **MongoDB Atlas** cluster & user
* Connect using environment variable:

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster-url"
```

### 3. **Pipeline Stages**

* **Data Ingestion** → Fetch from MongoDB, store as DataFrame
* **Data Validation** → Schema checks (`schema.yaml`)
* **Data Transformation** → Feature engineering & preprocessing
* **Model Training** → Train ML model
* **Model Evaluation** → Evaluate with drift detection
* **Model Pusher** → Upload best model to AWS S3

### 4. **Deployment**

* Build Docker image & push to AWS ECR
* Deploy container on AWS EC2 instance
* Expose Flask app on port 5000

---

## 🚀 CI/CD Pipeline

* **GitHub Actions** → Triggers on every push/commit
* **Self-Hosted Runner on EC2** → Runs jobs in AWS
* **Secrets Management** → AWS keys stored in GitHub Secrets
* **ECR + Docker** → Stores container images
* **EC2 Deployment** → App served at `<public-ip>:5000`

---

## 📊 Architecture Diagram

```mermaid
flowchart LR
    A[MongoDB Atlas] -->|Data Ingestion| B[Data Pipeline]
    B --> C[Data Validation]
    C --> D[Data Transformation]
    D --> E[Model Training]
    E --> F[Model Evaluation]
    F --> G[AWS S3 - Model Registry]
    G --> H[Dockerized App]
    H --> I[CI/CD with GitHub Actions]
    I --> J[Deployment on AWS EC2]
```

---

✨ This project is built to **showcase modern MLOps practices** and demonstrate real-world deployment of ML pipelines with scalable cloud integration.

---

