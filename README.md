# Customer Churn Prediction ML Project

A comprehensive machine learning project for predicting customer churn using advanced ML techniques and MLOps best practices.

## 🚀 Features

- **ML Pipeline**: Complete data processing, feature engineering, and model training pipeline
- **FastAPI API**: Production-ready REST API for model predictions
- **MLflow Integration**: Experiment tracking and model versioning
- **Monitoring**: Real-time model performance monitoring with Evidently
- **CI/CD**: Automated testing, linting, and deployment pipeline

## 🧪 Testing & Quality

### Test Execution
```bash
# Run all tests
pytest

# Run tests in parallel (faster CI)
pytest -n auto

# Run with coverage
pytest --cov=src --cov-report=html

# Run specific test categories
pytest -m unit      # Unit tests only
pytest -m integration  # Integration tests only
pytest -m "not slow"   # Exclude slow tests
```

### Code Quality
```bash
# Format code
black src/ tests/ api/

# Sort imports
isort src/ tests/ api/

# Lint code
flake8 src/ tests/ api/

# Type checking
mypy src/
```

## 📊 Coverage & CI

### Codecov Integration
- **Coverage Threshold**: 80% minimum
- **Quality Gates**: Fails CI if coverage drops below threshold
- **PR Comments**: Automatic coverage reports on pull requests
- **Coverage Badges**: Real-time coverage status

### CI Pipeline Features
- **Parallel Testing**: Uses pytest-xdist for faster execution
- **Smart Caching**: Caches pytest results and pip dependencies
- **Coverage Reports**: XML, HTML, and terminal output
- **Quality Checks**: Black, isort, flake8, mypy
- **Security Audit**: pip-audit for vulnerability scanning

## 🏗️ Project Structure

```
customer_churn_prediction/
├── api/                    # FastAPI application
├── src/                    # Source code
│   ├── data/              # Data loading & preprocessing
│   ├── features/          # Feature engineering
│   ├── models/            # ML model training & prediction
│   └── utils/             # Utility functions
├── tests/                  # Test suite
├── config/                 # Configuration files
├── models/                 # Trained models
├── monitoring/             # Model monitoring
└── deployment/             # Deployment configurations
```

## 🚀 Quick Start

1. **Clone & Setup**
   ```bash
   git clone <repository-url>
   cd customer_churn_prediction
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

2. **Run Tests**
   ```bash
   pytest
   ```

3. **Start API**
   ```bash
   cd api
   uvicorn app:app --reload
   ```

## 📈 Coverage Status

[![codecov](https://codecov.io/gh/yourusername/customer_churn_prediction/branch/main/graph/badge.svg)](https://codecov.io/gh/yourusername/customer_churn_prediction)

> **Note**: Replace `yourusername` with your actual GitHub username in the badge URL above.

## 🚀 **CI/CD Status: Active!**
- ✅ Automated testing with pytest
- ✅ Code coverage tracking with Codecov
- ✅ Quality checks (Black, isort, flake8, mypy)
- ✅ Security auditing with pip-audit

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Ensure all tests pass and coverage is maintained
6. Submit a pull request

## 📝 License

This project is licensed under the MIT License.