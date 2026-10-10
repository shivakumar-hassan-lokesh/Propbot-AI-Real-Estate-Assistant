<div align="center">

# 🏠 PropBot – AI Real Estate Assistant for Boston

**An intelligent real estate chatbot powered by GPT-4o-mini and RAG, designed to help users find properties in Boston.**

MLOps Course Final Project – Group 18 · IE 7374 – Northeastern University<br>
**Milestone 1: Data Pipeline Submission**

<br>

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-412991?style=flat-square&logo=openai&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector%20DB-FF6F00?style=flat-square)
![Sentence Transformers](https://img.shields.io/badge/Sentence%20Transformers-Embeddings-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
<br>
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![DVC](https://img.shields.io/badge/DVC-13ADC7?style=flat-square&logo=dvc&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Google Cloud](https://img.shields.io/badge/Google%20Cloud%20Run-4285F4?style=flat-square&logo=googlecloud&logoColor=white)

</div>

---

## 📑 Table of Contents

- [Team Members](#-team-members)
- [Demo](#-demo)
- [Overview](#-overview)
- [Features](#-features)
- [Architecture](#%EF%B8%8F-architecture)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Testing](#-testing)
- [Monitoring & MLOps](#-monitoring--mlops)
- [CI/CD Pipeline](#-cicd-pipeline)
- [Deployment](#-deployment)
- [Data Version Control (DVC)](#-data-version-control-dvc)
- [API Endpoints](#-api-endpoints)
- [Technologies](#%EF%B8%8F-technologies)
- [Environment Variables](#-environment-variables)
- [Contributing](#-contributing)
- [Known Issues & Limitations](#%EF%B8%8F-known-issues--limitations)
- [Future Improvements](#-future-improvements)
- [Acknowledgments](#-acknowledgments)
- [License](#-license)

---

## 👥 Team Members

- Shivakumar Hassan Lokesh
- Nishchay Linge Gowda
- Dhanush Manoharan
- Pranav Rangbulla
- Gayatri Nair
- Priyanka Raj Rajendran

---

## 🎬 Demo

<p align="center">
  <img src="assets/images/propbot1-ezgif.com-video-to-gif-converter.gif" alt="PropBot Demo" width="800">
</p>
<p align="center">
  <i>PropBot in action at Google Cambridge MLOps Innovation Expo</i>
</p>
<p align="center">
  <a href="https://www.linkedin.com/posts/shivakumar-hassan-lokesh-8b65ab365_mlops-northeasternuniversity-googlecambridge-ugcPost-7406438397210382336-co-q/">
    <img src="https://img.shields.io/badge/LinkedIn-Photos%20from%20the%20Expo-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn Post">
  </a>
</p>

---

## 📖 Overview

**PropBot – Boston Real Estate Chatbot with MLOps Pipeline**

PropBot is an intelligent real estate chatbot powered by GPT-4o-mini and RAG (Retrieval-Augmented Generation) technology, designed to help users find properties in Boston. This project implements a complete MLOps pipeline with automated monitoring, drift detection, and model retraining.

---

## 🎯 Features

### Core Functionality

| Feature | Description |
|---|---|
| **Intelligent Property Search** | RAG-powered chatbot using ChromaDB and OpenAI GPT-4o-mini |
| **Real-time Property Data** | Integration with Zillow and Boston property listings |
| **Semantic Search** | Advanced embedding-based retrieval using Sentence Transformers |
| **Interactive UI** | Streamlit-based frontend with a real-time chat interface |
| **FastAPI Backend** | High-performance REST API with monitoring endpoints |

### MLOps Features

| Feature | Description |
|---|---|
| **Automated Model Monitoring** | Real-time metrics collection and performance tracking |
| **Data Drift Detection** | Jensen-Shannon divergence-based drift detection |
| **Automated Retraining** | Trigger-based model retraining pipeline |
| **Cloud Logging** | Structured logging to Google Cloud Platform |
| **CI/CD Pipeline** | GitHub Actions workflow with automated testing and deployment |
| **DVC Integration** | Data version control for model and dataset versioning |
| **Health Monitoring** | Deployment verification and smoke testing |

---

## 🏗️ Architecture

```text
┌─────────────┐         ┌──────────────┐         ┌─────────────┐
│  Streamlit  │ ──────> │   FastAPI    │ ──────> │  ChromaDB   │
│  Frontend   │ <────── │   Backend    │ <────── │  (Vector)   │
└─────────────┘         └──────────────┘         └─────────────┘
                               │
                               ├──> OpenAI GPT-4o-mini
                               ├──> Monitoring System
                               ├──> Drift Detector
                               └──> Retraining Pipeline
```

---

## 📁 Project Structure

```text
project_mlops/
├── backend/
│   ├── main.py                    # FastAPI application
│   ├── requirements.txt           # Python dependencies
│   ├── dockerfile                 # Backend container
│   ├── startup.sh                 # Cloud Run startup script
│   ├── src/
│   │   └── rag_pipeline.py        # RAG implementation
│   ├── monitoring/
│   │   ├── metrics.py             # Metrics collection
│   │   ├── drift_detector.py      # Data drift detection
│   │   └── cloud_logger.py        # Cloud logging
│   ├── retraining/
│   │   └── trigger.py             # Retraining triggers
│   ├── scripts/
│   │   ├── retrain_model.py       # Automated retraining pipeline
│   │   └── verify_monitoring.py   # Dependency verification
│   ├── notifications/
│   │   └── alerts.py              # Notification system
│   └── mlflow_tracking/
│       └── tracker.py             # MLflow experiment tracking
├── frontend/
│   ├── app.py                     # Streamlit application
│   └── Dockerfile                 # Frontend container
├── .github/
│   └── workflows/
│       └── ci-cd.yml              # CI/CD pipeline
├── tests/                         # Unit and integration tests
└── dvc.yaml                       # DVC pipeline configuration
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.11+
- OpenAI API Key
- Google Cloud Platform account (for deployment)
- Git with DVC

### Local Development Setup

<details open>
<summary><b>Step-by-step setup</b></summary>

<br>

1. **Clone the repository**

   ```bash
   git clone https://github.com/YOUR_USERNAME/project_mlops.git
   ```

2. **Set up environment variables**

   ```bash
   # Backend
   cd backend

   export OPENAI_API_KEY="your-openai-api-key"
   export CHROMA_PATH="chroma_data"
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Verify the monitoring system**

   ```bash
   python scripts/verify_monitoring.py
   ```

5. **Start the backend**

   ```bash
   # Windows
   start.bat

   # Linux/Mac
   python main.py
   ```

   The backend will be available at `http://localhost:8080`.

6. **Start the frontend** (in a new terminal)

   ```bash
   cd frontend
   streamlit run app.py
   ```

   The frontend will be available at `http://localhost:8501`.

</details>

---

## 🧪 Testing

**Run Unit Tests**

```bash
pytest tests/ -v
```

**Run Monitoring Verification**

```bash
cd backend
python scripts/verify_monitoring.py
```

**Test Health Endpoint**

```bash
curl http://localhost:8080/health
```

**Test Chat Endpoint**

```bash
curl -X POST http://localhost:8080/chat \
  -H "Content-Type: application/json" \
  -d '{"query": "Show me properties in Back Bay", "conversation_id": "test123"}'
```

---

## 📊 Monitoring & MLOps

| Metrics Collection | Drift Detection | Automated Retraining |
|---|---|---|
| The system automatically collects: | Data drift is monitored using: | Retraining triggers when: |
| • Query response times<br>• Number of documents retrieved<br>• User satisfaction scores<br>• System resource utilization | • Jensen-Shannon divergence on query embeddings<br>• Performance metric degradation detection<br>• Threshold-based alerting | • Data drift exceeds threshold (0.1)<br>• Performance drops below baseline<br>• Manual trigger via API endpoint |

<details>
<summary><b>Retraining Pipeline</b></summary>

<br>

```bash
# Manual trigger
curl -X POST http://localhost:8080/api/monitoring/trigger-retraining
```

The pipeline executes:

1. Pull latest data from DVC
2. Retrain RAG model with updated data
3. Validate new model performance
4. Compare with baseline metrics
5. Deploy if better than current model

</details>

---

## 🔄 CI/CD Pipeline

### GitHub Actions Workflow

Triggered on push to the `main` branch:

| Stage | Steps |
|---|---|
| **Test Stage** | Install dependencies → Run unit tests → Continue on test failures (for demo) |
| **Deploy Backend** *(Currently disabled)* | Pull latest models from DVC → Build Docker container → Deploy to Cloud Run → Health check verification → Smoke testing |
| **Deploy Frontend** *(Currently disabled)* | Build Streamlit container → Deploy to Cloud Run |

<details>
<summary><b>Enable Deployment</b></summary>

<br>

To enable automatic deployment, update `.github/workflows/ci-cd.yml`:

```yaml
# Change from:
if: false

# To:
if: github.ref == 'refs/heads/main'
```

</details>

### Required GitHub Secrets

| Secret | Description |
|---|---|
| `GCP_SA_KEY` | Google Cloud service account JSON key |
| `OPENAI_API_KEY` | OpenAI API key |

---

## 🌐 Deployment

### Google Cloud Run Deployment

**Prerequisites:**

- GCP project created
- Cloud Run API enabled
- Service account with Cloud Run permissions

<details>
<summary><b>Deploy Backend</b></summary>

<br>

```bash
gcloud run deploy propbot-backend \
  --source backend/ \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated \
  --memory 4Gi \
  --cpu 2 \
  --set-env-vars OPENAI_API_KEY=$OPENAI_API_KEY,MONITORING_ENABLED=true
```

</details>

<details>
<summary><b>Deploy Frontend</b></summary>

<br>

```bash
gcloud run deploy propbot-frontend \
  --source frontend/ \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated \
  --set-env-vars BACKEND_API_URL=$BACKEND_URL
```

</details>

---

## 📈 Data Version Control (DVC)

### DVC Pipeline Stages

| Stage | Description |
|---|---|
| **Data Acquisition** | Collect properties from Zillow |
| **Preprocessing** | Clean and normalize datasets |
| **ChromaDB Ingestion** | Embed and store in vector database |

**Pull Latest Data**

```bash
dvc pull
```

**Update Data**

```bash
dvc repro
dvc push
```

---

## 🔧 API Endpoints

| Endpoint | Method | Path | Body |
|---|---|---|---|
| Health Check | `GET` | `/health` | — |
| Chat | `POST` | `/chat` | `{"query": "string", "conversation_id": "string"}` |
| Monitoring Metrics | `GET` | `/api/monitoring/metrics` | — |
| Drift Detection | `GET` | `/api/monitoring/drift` | — |
| Trigger Retraining | `POST` | `/api/monitoring/trigger-retraining` | — |

---

## 🛠️ Technologies

| Category | Technologies |
|---|---|
| **Backend** | FastAPI, ChromaDB, OpenAI GPT-4o-mini, Sentence Transformers, MLflow, Google Cloud Logging |
| **Frontend** | Streamlit, Python Requests |
| **MLOps** | GitHub Actions, DVC (Data Version Control), Docker, Google Cloud Run, Google Cloud Storage |
| **Monitoring** | Custom metrics collection, Jensen-Shannon divergence for drift, Cloud logging and monitoring |

---

## 📝 Environment Variables

**Backend**

```bash
OPENAI_API_KEY=your-api-key
CHROMA_PATH=chroma_data
ENVIRONMENT=production
MONITORING_ENABLED=true
```

**Frontend**

```bash
BACKEND_API_URL=http://localhost:8080
```

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## ⚠️ Known Issues & Limitations

| Issue | Details |
|---|---|
| **API Rate Limits** | Some data sources have rate limits; the pipeline includes retry logic |
| **Large File Size** | ChromaDB backup is 3.8GB; requires DVC for versioning |
| **Processing Time** | Full pipeline takes ~45 minutes on standard hardware |

---

## 🔮 Future Improvements

1. Implement real-time data streaming
2. Add more sophisticated bias mitigation techniques
3. Expand to more Boston neighborhoods
4. Add data quality dashboards
5. Implement automated retraining pipeline

---

## 🙏 Acknowledgments

- Boston Open Data for property datasets
- OpenAI for GPT-4o-mini API

---

## 📄 License

This project is part of an MLOps course submission.

MIT License – Academic Project
