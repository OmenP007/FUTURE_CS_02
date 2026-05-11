# 📜 Tech Manifest: Scripts & Modules

The scanning process is orchestrated by a hybrid architecture combining the flexibility of Python with the raw speed of C.

## 🐍 Python Modules (Orchestration & ML)
- **`live_protection.py`**: The central orchestrator for IMAP monitoring and real-time threat detection.
- **`main_detector.py`**: Coordinates the different scanning engines and aggregates results.
- **`ml_classifier.py`**: Implements the Machine Learning logic (Random Forest) for predictive phishing classification.
- **`threat_intel.py`**: Manages the local database of known phishing URLs and domain signatures.

## ⚡ C Modules (Performance)
- **`url_analyser.c`**: Implements high-performance Shannon Entropy and typosquatting detection for URLs.
- **`emails_scanner.c`**: High-speed, multi-threaded C engine for parsing and analyzing email payloads.
- **`c_url_analyzer.pyd` / `c_email_scanner.pyd`**: Compiled C extensions used by Python.

## 📊 Reporting
- **HTML/PDF Reports**: Dynamic generation of detailed, professional security audits based on scan results.
