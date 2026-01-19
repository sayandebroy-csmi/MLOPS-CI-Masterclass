# MLOPS-CI-Masterclass

A demonstration project for implementing end-to-end Continuous Integration (CI) in MLOps workflows.

## Overview

This project showcases a simple **Power Calculator** application built with Streamlit, featuring automated testing with pytest. It serves as a practical example of CI best practices in machine learning operations.

## Features

- **Power Calculator**: Calculate square, cube, and fifth power of any number
- **Interactive UI**: Built with Streamlit for easy user interaction
- **Automated Testing**: Comprehensive test suite using pytest
- **CI Pipeline Ready**: Structured for seamless CI/CD integration

## Project Structure

```
MLOPS-CI-Masterclass/
├── app.py              # Streamlit application
├── _test.py            # pytest test suite
├── requirements.txt    # Python dependencies
├── LICENSE             # Project license
└── README.md           # This file
```

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/MLOPS-CI-Masterclass.git
   cd MLOPS-CI-Masterclass
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Running the Application

```bash
streamlit run app.py
```

The app will open in your browser where you can:
- Enter any integer
- View the calculated square, cube, and fifth power

### Running Tests

```bash
pytest
```

This will run all test cases including:
- `test_square`: Validates square calculations
- `test_cube`: Validates cube calculations
- `test_fifth_power`: Validates fifth power calculations
- `test_invalid_input`: Ensures proper error handling for invalid inputs

## Dependencies

- **pytest** (9.0.2): Testing framework
- **streamlit** (1.53.0): Web application framework

## CI Integration

This project is designed to work with popular CI/CD platforms:

- **GitHub Actions**: Add workflow files to `.github/workflows/`
- **GitLab CI**: Configure `.gitlab-ci.yml`
- **Jenkins**: Use `Jenkinsfile` for pipeline definition

Example GitHub Actions workflow:
```yaml
name: CI Pipeline

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'
      - name: Install dependencies
        run: pip install -r requirements.txt
      - name: Run tests
        run: pytest _test.py -v
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Open a Pull Request

## License

See the [LICENSE](LICENSE) file for details.
