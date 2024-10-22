

# Iris Classification Web Application - Flask Deployment

## Table of Contents
1. [Introduction](#introduction)
2. [Key Features](#key-features)
3. [Project Structure](#project-structure)
4. [Technologies Used](#technologies-used)
5. [How to Use](#how-to-use)
6. [Installation and Setup](#installation-and-setup)
7. [Model Training](#model-training)
8. [API Endpoints](#api-endpoints)
9. [Contributing](#contributing)
10. [License](#license)

---

## Introduction

This project demonstrates how to deploy a machine learning model for **Iris species classification** using **Flask**. The Iris dataset contains measurements of sepal length, sepal width, petal length, and petal width of three different Iris species (Setosa, Versicolor, Virginica). The model predicts the species based on these measurements.

The Flask application serves a web interface and REST API, allowing users to input features and get predictions from the deployed model.

## Key Features

- **Model Training**: The Iris dataset is used to train a classification model.
- **Web Interface**: A simple UI where users can input features (sepal and petal dimensions) and receive predictions of the Iris species.
- **REST API**: Accepts input as JSON and returns predictions in real-time.
- **Model Deployment**: The trained model is saved and loaded for future predictions using Flask.

## Project Structure

```
├── app.py                     # Main Flask application file
├── iris_model.pkl              # Pre-trained model saved using pickle
├── templates/                  # HTML templates for the web interface
│   └── index.html              # Main page where users can input Iris features
├── static/                     # CSS or JS files (if required)
├── requirements.txt            # Python dependencies for the project
├── README.md                   # Project documentation (this file)
└── model_training.py           # Script to train and save the Iris classification model
```

## Technologies Used

- **Flask**: Python web framework for deploying the model.
- **Scikit-learn**: For building and training the classification model.
- **Pandas and NumPy**: For data handling and preprocessing.
- **Pickle**: For saving and loading the trained model.
- **HTML/CSS**: To create a simple web interface.

## How to Use

1. **Web Interface**: 
   - Navigate to the homepage.
   - Input the sepal and petal measurements.
   - Click the "Predict" button to receive the predicted Iris species.

2. **API**:
   - Send a POST request to `/predict` endpoint with JSON input containing the features.
   - Receive a JSON response with the predicted species.

Example API Input:
```json
{
    "sepal_length": 5.1,
    "sepal_width": 3.5,
    "petal_length": 1.4,
    "petal_width": 0.2
}
```

Example API Output:
```json
{
    "species": "Setosa"
}
```

## Installation and Setup

To run this project locally:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/iris-flask-app.git
   cd iris-flask-app
   ```

2. **Install dependencies**:
   Use `pip` to install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Train the model (if needed)**:
   If you need to train the model, run the `model_training.py` script:
   ```bash
   python model_training.py
   ```

   This will generate a `iris_model.pkl` file that the Flask app will use for predictions.

4. **Run the Flask application**:
   Start the Flask app by running:
   ```bash
   python app.py
   ```

5. **Access the web app**:
   Open your browser and go to `http://127.0.0.1:5000/` to use the web interface.

## Model Training

The machine learning model is trained using the classic Iris dataset. The following steps are performed:

1. **Data Loading**: The Iris dataset is loaded from Scikit-learn's built-in datasets.
2. **Preprocessing**: The dataset is preprocessed, including splitting into training and test sets.
3. **Model Building**: A classification model (e.g., Logistic Regression, SVM, or Random Forest) is trained.
4. **Model Saving**: The trained model is saved as `iris_model.pkl` using the `pickle` library for later use in the Flask app.

The model training script (`model_training.py`) allows you to retrain the model at any time.

## API Endpoints

- **`/` (GET)**: 
   - Serves the main web interface for inputting Iris features and getting predictions.

- **`/predict` (POST)**: 
   - Accepts JSON input with the Iris features (sepal length, sepal width, petal length, petal width) and returns the predicted Iris species in JSON format.

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

