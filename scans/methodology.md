# Phishing Detection Methodology

## 1. Data Collection
- **IMAP Integration**: The system connects to the user's email inbox using the `imaplib` library. It monitors for `UNSEEN` messages in real-time.
- **Threat Intelligence**: A local database (`threat_intel.json`) is maintained, containing known phishing URLs and domain signatures.

## 2. Analysis Pipeline
The analysis follows a hybrid approach:
1. **Heuristic Analysis (C Engine)**:
    - Rapidly checks URLs against the local bitset and blacklists.
    - Calculates Shannon Entropy to detect obfuscated or generated domains.
    - Identifies typosquatting by comparing against common legitimate brands.
2. **Machine Learning (Python Engine)**:
    - Extracts features from the email body and headers (e.g., urgency, sender mismatch, suspicious attachments).
    - Uses a Random Forest classifier to determine the probability of phishing.

## 3. Reporting & Mitigation
- **Real-time Alerts**: The GUI notifies the user immediately upon detection.
- **Detailed Audits**: Generates HTML reports summarizing the evidence (entropy scores, ML confidence, blacklisted status).
- **Remediation**: Recommends marking the email as spam or blocking the sender domain.
