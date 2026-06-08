DermaScanX 🔬
An AI-powered skin disease screening web application that combines deep learning, a 3-tier inference pipeline, symptom-based diagnosis quiz, an AI doctor chatbot, and real-time dermatologist discovery — all in one platform.
🌐 Live Demo: skinai-cnn-detection.vercel.app

Demo credentials — User: user / user  |  Admin: admin / admin


What is DermaScanX?
DermaScanX is a full-stack medical AI web application that helps users screen for skin diseases by uploading or capturing an image of the affected area. The app runs the image through a 3-tier AI inference pipeline, asks targeted diagnostic questions, generates a detailed medical report, and connects users with real nearby dermatologists — all within a single seamless workflow.
Built as a final year academic project using Flask, TensorFlow, EfficientNetV2B0, HuggingFace Transformers, SQLite and deployed on Vercel.

Screenshots
Login Page

Scan Page — Upload or Capture Image

Diagnosis Quiz — Symptom Verification

Results Page — Full AI Medical Report

Results Page — Detailed Insights

AI Doctor Chatbot

Nearby Dermatologist Finder with Live Map

User Dashboard

Admin Command Center


Key Results
MetricValueOverall Test Accuracy (Top-1)75.82%Overall Test Accuracy (Top-3)96.72%Training StrategyFeature Extraction + Head TrainingBackboneEfficientNetV2B0 (ImageNet)OptimizerAdamW (lr=1e-3, weight_decay=1e-4)Loss FunctionCategorical Cross-Entropy (label smoothing=0.1)Head Epochs200 (with early stopping)Image Size224 × 224 pixels
Per-Class Accuracy


System Architecture

The system consists of a Flask backend handling all requests, a SQLite database for storing users, predictions and feedback, a 3-tier AI inference pipeline, and supporting features including the AI chat assistant, symptom quiz generator and doctor referral system.

3-Tier AI Inference Pipeline

The prediction system uses a cascading fallback strategy to ensure maximum reliability:

NVIDIA Nemotron-Nano-12B-V2-VL — Primary cloud inference
HuggingFace ViT (LaurianeMD/vit-skin-disease) — Secondary vision transformer
Local TFLite/Keras CNN (EfficientNetV2B0) — Final on-device fallback


CNN Model Architecture

The model uses EfficientNetV2B0 as a frozen backbone with ImageNet weights, followed by a custom classification head with batch normalization, dropout regularization and dense layers outputting 7 class probabilities.

Tech Stack


Database Schema

The database has 4 entities: USER, PREDICTION, DOCTOR and FEEDBACK, with proper relationships and foreign key constraints.

Dataset — HAM10000
The model was trained on the HAM10000 dataset (Human Against Machine with 10,000 training images). The dataset has extreme class imbalance which was addressed using oversampling.


Training Results
Training vs Validation Accuracy over 80 Epochs

Training vs Validation Loss over 80 Epochs

Confusion Matrix on HAM10000 Test Set


User Flow


Training Algorithm


Prediction Algorithm


Features
Image Upload & Scanning — Upload, drag-drop or capture via live camera
Diagnosis Quiz — 5 mandatory symptom questions + open-ended description fields, disease-specific based on what the model detects
Detailed Medical Report — Top matches with probabilities, visible signs, verification summary, evidence supporting/against, red flags, assurance and calibration, common symptoms, likely cause, contagiousness, common locations, similar diseases, care options, what to avoid, prevention tips, how doctors confirm it, when to see a doctor
AI Doctor Chatbot — Context-aware chatbot that knows your diagnosed condition and answers questions about causes, treatment, medication and next steps
Nearby Dermatologist Finder — Live location-based map showing nearby hospitals, dermatologists and clinics with directions, call and OSM links
Doctor Enrollment & Reviews — Doctors can register on the platform with specialization, hospital, availability and contact info; patients can leave ratings and reviews
Admin Panel — Full platform oversight with registered users, doctors, total scans, feedback, scan result distribution pie chart and condition counts bar chart

How to Use

Visit skinai-cnn-detection.vercel.app
Login or create a new account
Upload, capture or drag and drop a skin image
Complete the diagnosis quiz
View your full AI medical report
Chat with the AI doctor for more information
Find nearby dermatologists using your location


Disclaimer
DermaScanX is an academic project built for educational purposes only. It is not a substitute for professional medical advice, diagnosis or treatment. Always consult a qualified dermatologist for medical concerns.

Developer
Deepak Dubey
B.Tech Computer Science, DY Patil International University, Pune (2022–2026)
📧 dubeydeepak0707@gmail.com
🔗 LinkedIn
🐙 GitHub
