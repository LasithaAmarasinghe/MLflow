# MLflow Guide

## 1. Introduction to MLflow
MLflow is an open-source platform used to manage the machine learning lifecycle, including experimentation, reproducibility, and deployment.

### Components of MLflow:
- **Tracking**: Tracks and logs metrics, parameters, and models.
- **Projects**: Packages data science code in a reusable and reproducible form.
- **Models**: Manages and stores models in various formats.
- **Registry**: A central repository for managing the lifecycle of ML models.

## 2. Getting Started with MLflow
To get started with MLflow, first install it using `pip`:
```bash
pip install mlflow
```
Set up a simple experiment:
```python
import mlflow

mlflow.start_run()

# Log parameters, metrics, and model during an experiment
mlflow.log_param("param1", 5)
mlflow.log_metric("accuracy", 0.95)
mlflow.log_artifact("model.pkl")

mlflow.end_run()
```

## 3. Model Registration
This feature is useful for storing and managing versions of your models.

![Screenshot 2025-06-08 192411](https://github.com/user-attachments/assets/5f859172-6962-4283-9be7-578a1e32307d)


### How to Register a Model:
After training a model, you can register it in the **MLflow Model Registry**.

- From the **Models** tab, you can create a versioned model.
- Each model version can be associated with specific metrics and parameters, and tracked through different stages (e.g., Staging, Production).

#### Example:
```python
mlflow.register_model("runs:/<run_id>/model", "Model Name")
```

## 4. Experiment Tracking
MLflow allows to log and compare different models and their respective metrics across experiments.

![Screenshot 2025-06-08 192341](https://github.com/user-attachments/assets/4f683340-7c2c-4207-a429-54858bbd0d83)

## 5. Run Comparison
MLflow allows to compare runs by different parameters.

![Screenshot 2025-06-08 192359](https://github.com/user-attachments/assets/3f14390c-d85c-464b-acba-9e35e262b4c5)

## 6. Viewing Metrics and Parameters
MLflow logs various types of metrics (e.g., accuracy, precision) for each run, which can be viewed and compared in real-time.

![Screenshot 2025-06-08 192430](https://github.com/user-attachments/assets/803ae855-6cbf-4fa0-a9c4-77301fd2f364)

### How to View Metrics:
- After running an experiment, go to the **Experiments** tab and click on a specific run to view its detailed metrics and parameters.
- MLflow stores parameters, metrics, and even artifacts (like models) associated with each run.

## 7. Versioning Models
Versioning is crucial when models undergo changes, as it allows you to manage and roll back to previous versions.

![Screenshot 2025-06-09 072904](https://github.com/user-attachments/assets/2af279e6-c654-46bc-a638-586a9f944b08)

### How to Create and Track Model Versions:
- MLflow automatically version controls models, and each time you update or re-register a model, a new version is created.
- You can set an alias for the model version (e.g., `@champion`) to easily refer to specific versions.
