# 🏗️ Phishing Defender Architecture & Design

## 🖥️ System Design
Phishing Defender is designed as a **Hybrid Threat Analysis Engine**.

### 1. The Orchestration & ML Core (Python)
- Uses `imaplib` for real-time monitoring of incoming email traffic.
- Manages the analysis pipeline, extracting features and using a Machine Learning Classifier (Random Forest) for predictive phishing classification.
- Handles UI interaction and asynchronous alert generation.

### 2. The High-Performance Engine (C)
- Accelerates the most computationally intensive tasks like Shannon Entropy calculation and domain similarity checking.
- Analyzes URLs in parallel, skipping Python's overhead.
- Compiled as `.pyd` libraries and loaded seamlessly via Python extensions.

### 3. Visual Identity
- The dashboard uses a modern, dark-themed palette built with CustomTkinter.
- High-contrast alert badges for critical phishing detections.
- Interactive reporting format generated dynamically in HTML and PDF.
