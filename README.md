# MLflow Demo

A hands-on demonstration of **MLflow** for tracking machine learning experiments, logging metrics and parameters, and managing model lifecycle — all in a single self-contained Python script.

---

## 📌 Overview

This project showcases how to integrate [MLflow](https://mlflow.org/) into a typical ML workflow. It covers:

- **Experiment Tracking** – log parameters, metrics, and artifacts for every run
- **Model Logging** – save trained models directly to the MLflow tracking store
- **Run Comparison** – use the MLflow UI to compare experiments side-by-side
- **Local Tracking Store** – persists all run data to a local SQLite database (`mlflow.db`)

---

## 🗂️ Project Structure

```
ML_Flow_Demo/
├── ML_Flow.py       # Main script: model training + MLflow tracking
├── mlflow.db        # SQLite tracking store (auto-generated)
└── .gitattributes
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip

### Installation

```bash
# Clone the repository
git clone https://github.com/Minhaj078/ML_Flow_Demo.git
cd ML_Flow_Demo

# Install dependencies
pip install mlflow scikit-learn pandas numpy
```

### Run the Demo

```bash
python ML_Flow.py
```

This will train the model, log all parameters and metrics, and store results in `mlflow.db`.

---

## 📊 Viewing Results in the MLflow UI

```bash
mlflow ui --backend-store-uri sqlite:///mlflow.db
```

Then open your browser at **http://127.0.0.1:5000** to explore all tracked runs.

---

## 🔧 What's Being Tracked

| Item | Description |
|------|-------------|
| `params` | Hyperparameters (e.g., `n_estimators`, `max_depth`) |
| `metrics` | Model performance scores (e.g., accuracy, RMSE) |
| `artifacts` | Saved model files and plots |
| `tags` | Run metadata (e.g., author, dataset version) |

---

## 🧰 Tech Stack

- [MLflow](https://mlflow.org/) – Experiment tracking & model registry
- [scikit-learn](https://scikit-learn.org/) – ML algorithms
- [SQLite](https://www.sqlite.org/) – Local tracking backend
- Python 3.8+

---

## 📖 Key Concepts Demonstrated

### Starting a Run
```python
import mlflow

with mlflow.start_run():
    mlflow.log_param("n_estimators", 100)
    mlflow.log_metric("accuracy", 0.93)
    mlflow.sklearn.log_model(model, "model")
```

### Setting a Tracking URI
```python
mlflow.set_tracking_uri("sqlite:///mlflow.db")
mlflow.set_experiment("my_experiment")
```

---

## 📚 Resources

- [MLflow Documentation](https://mlflow.org/docs/latest/index.html)
- [MLflow Tracking Guide](https://mlflow.org/docs/latest/tracking.html)
- [MLflow Model Registry](https://mlflow.org/docs/latest/model-registry.html)

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

*Built as a learning demo for MLflow experiment tracking best practices.*
