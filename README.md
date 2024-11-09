# 🏠 Advanced End-to-End House Price Predictor with ZenML and MLflow

This project is an **Advanced End-to-End House Price Predictor** that uses **ZenML** for orchestrating machine learning pipelines and **MLflow** for experiment tracking and model deployment. The pipeline covers all steps from data processing, model training, and evaluation to deployment, making it a comprehensive solution for predicting house prices based on various features.

---

## 📋 Prerequisites

Ensure you have the following installed:
- **Python**: Version 3.7 or higher
- **Pip**: Version 20 or higher

---

## ⚙️ Setup Instructions

### 1. Install ZenML

To install ZenML, you can use pip or follow the [ZenML Installation Guide](https://docs.zenml.io/getting-started/installation).

```bash
pip install zenml
```

### 2. Create and Activate a Virtual Environment

Setting up a virtual environment helps to isolate project dependencies. You can follow this [tutorial](https://youtu.be/GZbeL5AcTgw?si=uj7B8-10kbyEytKo) if you need guidance.

- **Windows (Command Prompt)**:
  ```bash
  python -m venv venv
  .\venv\Scripts\activate
  ```

- **Windows (PowerShell)**:
  ```bash
  python -m venv venv
  .\venv\Scripts\Activate.ps1
  ```

- **Linux/macOS**:
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

### 3. Install Project Dependencies

Once the virtual environment is activated, install the required dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

### 4. Install ZenML MLflow Integration

To use MLflow for model deployment, install the ZenML MLflow integration:

```bash
zenml integration install mlflow -y
```

### 5. Configure the ZenML Stack with MLflow

The project requires a ZenML stack with an MLflow experiment tracker and model deployer. Register these components and create the stack by running:

```bash
zenml experiment-tracker register mlflow_tracker --flavor=mlflow
zenml model-deployer register mlflow --flavor=mlflow
zenml stack register local-mlflow-stack -a default -o default -d mlflow -e mlflow_tracker --set
```

---

## 🚀 Running the Pipeline

To execute the ML pipeline, run the `run_pipeline.py` script. This will process data, train the model, and evaluate it as per the pipeline setup.

```bash
python run_pipeline.py
```

## 🌐 Deploying the Model

To deploy the model using MLflow, run the `run_deployment.py` script. Ensure the ZenML stack is configured and MLflow is running.

```bash
python run_deployment.py
```

---

## 🗂 Project Structure

```plaintext
/project
│
├── requirements.txt         # Project dependencies
├── run_pipeline.py          # Script to run the ZenML pipeline
├── run_deployment.py        # Script to deploy the model with MLflow
├── /data                    # Directory for data files (if applicable)
├── /notebooks               # Jupyter notebooks (if applicable)
├── /src                     # Source code for models, pipeline, etc.
└── /logs                    # Logs and experiment tracking (if applicable)
```

---

## 📜 License

This project is licensed under **Devaraj Veeravel**.

---

Feel free to reach out if you encounter any issues or need further help. Happy coding! 🚀


