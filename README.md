# 🤖 Distributed Transformers Training on Azure ML with Accelerate

This repository contains a full **distributed training pipeline** for transformer models using **Hugging Face Accelerate**, **PyTorch**, and **Azure Machine Learning Pipelines**.  
The pipeline performs training and evaluation on datasets stored in **Azure Blob Storage**, using a custom Docker image and CPU compute cluster.

---

## 🚀 Features

- Training with Hugging Face `accelerate` and `transformers.Trainer`  
- Evaluation with `scikit-learn`'s classification report (pre & post training)  
- Datasets stored in **Azure Blob Storage** and mounted via `URI_FOLDER`  
- Containerized logic using `Dockerfile` + `train.py`  
- Executed on Azure ML with a CPU-based compute cluster  
- Outputs saved to `output_dir`, including the trained model and tokenizer  
- Compatible with extension to GPU clusters and multi-node execution

---

## ☁️ Azure ML Deployment

### 1. Configure the Datastore

Create a YAML file for your datastore (`pipeline_blobstore_2.yml`) and register it:

```bash
az ml datastore create \
  --file pipeline_blobstore_2.yml \
  --resource-group rg-proyecto1 \
  --workspace-name ws-proyecto1-v2
```

### 2. Launch the pipeline

```bash
python run_pipeline.py
```

---
