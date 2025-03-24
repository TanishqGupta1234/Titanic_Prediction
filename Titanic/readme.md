
# 🚢 Titanic Survival Predictor: Containerized Streamlit App

## 📌 Overview

The Titanic Survival Prediction Model is an interactive web application that predicts whether a passenger would have survived the Titanic disaster based on input features like age, gender, and class. The model is built using Python, trained with scikit-learn, and deployed using Streamlit. The entire application is containerized with Docker, ensuring seamless deployment and portability.

## 📂 Project Structure

```bash
Titanic-Prediction-Model/
│── Dockerfile
│── requirements.txt
│── main.py
│── titanic_model.py
│── titanic_model.pkl
```

## 📜 Description of Files:

* main.py → Streamlit application to interact with users.

* titanic_model.py → Script to train and save the prediction model.

* titanic_model.pkl → Pre-trained machine learning model for predictions.

* requirements.txt → Dependencies required to run the application.

* Dockerfile → Instructions to containerize the app using Docker.

## 🤖 Model Training (titanic_model.py)

The model is trained using a Random Forest Classifier, leveraging Titanic dataset features. After training, it is saved as titanic_model.pkl for easy reusability.

Steps in Model Training:

1. Load and preprocess the Titanic dataset.

2. Handle missing values and encode categorical features.

3. Train a Random Forest Model.

4. Save the trained model for deployment.

## 🎨 Streamlit Application (main.py)

The Streamlit web application allows users to input passenger details and get real-time survival predictions.

✨ Features:

✔️ Simple & Interactive UI

✔️ Real-time prediction updates

✔️ Intuitive dropdowns and sliders for input selection

## 🐳 Docker Setup

The application is containerized using Docker to ensure smooth deployment.

# 📄 Dockerfile

```bash
# Use Python 3.12 slim as base image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy necessary files
COPY requirements.txt requirements.txt
COPY main.py main.py
COPY titanic_model.pkl titanic_model.pkl

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose the application port
EXPOSE 8501

# Run the Streamlit app
CMD ["streamlit", "run", "main.py", "--server.port=8501",
```

## 🚀 Running the Application with Docker

Follow these steps to build and run the Dockerized application:

1️⃣ Navigate to the Project Directory

```bash
cd Titanic
```

2️⃣ Build the Docker Image

```bash
docker build -t titanic-prediction .
```

3️⃣ Run the Docker Container

```bash
docker run -p 8501:8501 titanic-prediction
```

4️⃣ Access the Application

Open your browser and visit:

```bash
http://localhost:8501
```

![Streamlit App Screenshot](https://github.com/vidhi-jaju/DockSpace/blob/503edea0a8d31ac50889f767b41cfc13cfd07b51/3.Titanic%20Survival%20Predictor%20Containerized%20Streamlit%20App/img2.png)

# 🎯 Conclusion

This project demonstrates how to deploy a machine learning model using Streamlit and Docker. The model predicts survival chances on the Titanic based on user input, and the Dockerized setup ensures easy portability and deployment.

🔥 Next Steps:

🌍 Deploy the app on AWS, GCP, or Vercel.

🎨 Improve UI with enhanced Streamlit components.

📊 Improve model accuracy with advanced feature engineering.

⚡ Happy Coding & Containerizing! 🐳🚢


