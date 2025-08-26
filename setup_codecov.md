# 🚀 Codecov Integration Setup Guide

## 📋 Prerequisites
- GitHub repository with CI/CD pipeline
- Python project with pytest and coverage
- Admin access to repository settings

## 🔗 Step 1: Connect to Codecov

### 1.1 Sign Up/Login
- Go to [https://codecov.io](https://codecov.io)
- Click "Sign in with GitHub"
- Authorize Codecov access to your repositories

### 1.2 Add Repository
- Click "Add New Repository"
- Select `customer_churn_prediction`
- Choose your GitHub account
- Click "Add Repository"

### 1.3 Get Upload Token
- After adding, you'll see setup instructions
- Copy the upload token (looks like: `12345678-1234-1234-1234-123456789abc`)

## 🔐 Step 2: Add GitHub Secret

### 2.1 Repository Settings
- Go to your GitHub repository
- Click "Settings" tab
- In left sidebar: "Secrets and variables" → "Actions"

### 2.2 Create Secret
- Click "New repository secret"
- **Name**: `CODECOV_TOKEN`
- **Value**: Paste your Codecov token
- Click "Add secret"

## 🧪 Step 3: Test Locally

### 3.1 Install Dependencies
```bash
pip install pytest-xdist pytest-cov
```

### 3.2 Run Tests with Coverage
```bash
# Basic coverage
pytest --cov=src --cov-report=html

# Parallel execution (like CI)
pytest -n auto --dist=loadfile tests/ --cov=src --cov-report=xml --cov-report=html
```

### 3.3 Verify Coverage Files
- Check that `coverage.xml` is generated
- Verify `htmlcov/` directory exists

## 🚀 Step 4: Push and Test

### 4.1 Commit Changes
```bash
git add .
git commit -m "Add Codecov integration and pytest caching"
git push origin main
```

### 4.2 Monitor CI Pipeline
- Go to GitHub Actions tab
- Watch the CI workflow run
- Check for Codecov upload step

### 4.3 Verify Codecov
- Visit your Codecov dashboard
- Check that coverage data appears
- Verify the 80% threshold is enforced

## 📊 Step 5: Customize Coverage

### 5.1 Update Badge URL
In `README.md`, replace:
```markdown
[![codecov](https://codecov.io/gh/YOUR_USERNAME/customer_churn_prediction/branch/main/graph/badge.svg)](https://codecov.io/gh/YOUR_USERNAME/customer_churn_prediction)
```

### 5.2 Adjust Coverage Threshold
In `codecov.yml`:
```yaml
coverage:
  status:
    project:
      default:
        target: 80%  # Adjust as needed
```

## 🔧 Troubleshooting

### Common Issues:

#### 1. Coverage Too Low
- Current coverage: ~14%
- Target: 80%
- **Solution**: Add more tests to cover missing code paths

#### 2. Token Not Found
- **Error**: "CODECOV_TOKEN not found"
- **Solution**: Check GitHub secrets are properly set

#### 3. Coverage Files Missing
- **Error**: "No coverage files found"
- **Solution**: Ensure pytest generates coverage.xml

#### 4. Parallel Test Issues
- **Error**: "Worker crashed"
- **Solution**: Use `--dist=loadfile` for file-based distribution

## 📈 Next Steps

### 1. Improve Test Coverage
```bash
# Run tests and see what's missing
pytest --cov=src --cov-report=term-missing

# Focus on specific modules
pytest --cov=src.data --cov-report=term-missing
```

### 2. Add Test Categories
```python
# In your test files
import pytest

@pytest.mark.unit
def test_data_loading():
    pass

@pytest.mark.integration
def test_full_pipeline():
    pass
```

### 3. Monitor Coverage Trends
- Check Codecov dashboard regularly
- Set up coverage alerts
- Review PR coverage reports

## 🎯 Success Criteria

✅ **Codecov connected and uploading**
✅ **Coverage threshold enforced (80%)**
✅ **Parallel testing working**
✅ **Coverage badges displaying**
✅ **PR comments with coverage info**

## 📞 Support

- **Codecov Docs**: [https://docs.codecov.io](https://docs.codecov.io)
- **GitHub Actions**: [https://docs.github.com/en/actions](https://docs.github.com/en/actions)
- **Pytest-xdist**: [https://pytest-xdist.readthedocs.io](https://pytest-xdist.readthedocs.io)

---

**Note**: This guide assumes you're using GitHub Actions. For other CI platforms, refer to Codecov's platform-specific documentation.
