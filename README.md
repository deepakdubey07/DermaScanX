# DermaScanX 🔬

An AI-powered skin disease screening web app combining deep learning, a 3-tier inference pipeline, symptom-based diagnosis, an AI doctor chatbot and real-time dermatologist discovery, all in one platform.

🌐 **Live Demo:** [skinai-cnn-detection.vercel.app](https://skinai-cnn-detection.vercel.app)

> Demo credentials: User: `user` / `user` | Admin: `admin` / `admin`

## What is DermaScanX?

DermaScanX is a full-stack medical AI web application that helps users screen for skin diseases by uploading or capturing an image of the affected area. The app runs the image through a 3-tier AI inference pipeline, asks targeted diagnostic questions, generates a detailed medical report and connects users with real nearby dermatologists, all within a single seamless workflow.

Built as a final year academic project using Flask, TensorFlow, EfficientNetV2B0, HuggingFace Transformers, SQLite and deployed on Vercel.

## Screenshots

**Login Page**
![Login Page](image015.png)

**Scan Page**
![Scan Page](image016.png)

**Diagnosis Quiz**
![Diagnosis Quiz](image017.png)

**Results Page**
![Results Page](image018.png)

**Results Page Continued**
![Results Detail](image019.png)

**AI Doctor Chatbot**
![AI Doctor Chat](image020.png)

**Nearby Dermatologist Finder**
![Nearby Doctors](image021.png)

**User Dashboard**
![Dashboard](image022.png)

**Admin Panel**
![Admin Panel](image023.png)

## Key Results

| Metric | Value |
|---|---|
| Overall Test Accuracy Top-1 | **75.82%** |
| Overall Test Accuracy Top-3 | **96.72%** |
| Training Strategy | Feature Extraction and Head Training |
| Backbone | EfficientNetV2B0 ImageNet |
| Optimizer | AdamW |
| Loss Function | Categorical Cross-Entropy with label smoothing |
| Head Epochs | 200 with early stopping |
| Image Size | 224 x 224 pixels |

**Per-Class Accuracy**
![Per Class Accuracy](image011.png)

## System Architecture

![System Architecture](image001.png)

The system consists of a Flask backend handling all requests, a SQLite database for storing users, predictions and feedback, a 3-tier AI inference pipeline and supporting features including the AI chat assistant, symptom quiz generator and doctor referral system.

## 3-Tier AI Inference Pipeline

![Inference Pipeline Flow](image006.png)

The prediction system uses a cascading fallback strategy. NVIDIA Nemotron-Nano-12B-V2-VL runs as the primary model, HuggingFace ViT runs as the secondary model and the local TFLite EfficientNetV2B0 CNN acts as the final fallback to ensure the app always returns a result.

## CNN Model Architecture

![CNN Architecture](image002.png)

EfficientNetV2B0 frozen backbone with ImageNet weights, followed by a custom classification head with batch normalization, dropout regularization and dense layers outputting 7 class probabilities.

## Tech Stack

![Tech Stack](image003.png)

## Database Schema

![Database Schema](image004.png)

Four entities, USER, PREDICTION, DOCTOR and FEEDBACK, with proper relationships and foreign key constraints.

## Dataset

Trained on the HAM10000 dataset containing 10,015 dermatoscopic images across 7 classes. Extreme class imbalance was addressed using oversampling before training.

![Class Distribution](image009.png)

## Training Results

**Training vs Validation Accuracy over 80 Epochs**
![Training Accuracy](image014.png)

**Training vs Validation Loss over 80 Epochs**
![Training Loss](image013.png)

**Confusion Matrix on HAM10000 Test Set**
![Confusion Matrix](image012.png)

## User Flow

![User Flow](image005.png)

## Training Algorithm

![Training Pseudocode](image007.png)

## Prediction Algorithm

![Prediction Pseudocode](image008.png)

## Features

**Image Upload and Scanning** - Upload, drag and drop or capture via live camera

**Diagnosis Quiz** - 5 mandatory symptom questions plus open-ended description fields, customized based on what the model detects

**Detailed Medical Report** - Top matches with probabilities, visible signs, verification summary, supporting and opposing evidence, red flags, assurance and calibration, common symptoms, likely cause, contagiousness, common locations, similar diseases, care options, things to avoid, prevention tips, how doctors confirm the disease and when to see a doctor

**AI Doctor Chatbot** - Context-aware chatbot that knows your diagnosed condition and answers questions about causes, treatment and medication

**Nearby Dermatologist Finder** - Live location based map showing nearby hospitals, dermatologists and clinics with directions and contact options

**Doctor Enrollment and Reviews** - Doctors can register on the platform with their specialization, hospital, availability and contact info and patients can leave ratings and reviews

**Admin Panel** - Full platform oversight with registered users, doctors, total scans, feedback, scan result distribution pie chart and condition counts bar chart

## How to Use

1. Visit [skinai-cnn-detection.vercel.app](https://skinai-cnn-detection.vercel.app)
2. Login or create a new account
3. Upload, capture or drag and drop a skin image
4. Complete the diagnosis quiz
5. View your full AI medical report
6. Chat with the AI doctor for more information
7. Find nearby dermatologists using your location

## Disclaimer

DermaScanX is an academic project built for educational purposes only. It is not a substitute for professional medical advice, diagnosis or treatment. Always consult a qualified dermatologist for medical concerns.

## Developer

**Deepak Dubey**
B.Tech Computer Science, DY Patil International University, Pune (2022 to 2026)

📧 dubeydeepak0707@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/deepakdubey07)
🐙 [GitHub](https://github.com/deepakdubey07)
