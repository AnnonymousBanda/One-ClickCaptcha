
# One-ClickCaptcha

## Overview

**One-ClickCaptcha** is a project designed to create a seamless CAPTCHA experience. It involves a frontend (HTML, CSS, JavaScript) that interacts with a backend powered by Flask. The frontend collects user interaction data, such as mouse movement metrics, to determine user authenticity. When a user interacts with the CAPTCHA, this data is sent to the backend, which predicts whether the user is human or a bot and responds in JSON format.

---

## Features

1. **Frontend:**
   - Built using HTML, CSS, and JavaScript.
   - Captures mouse movement data, including:
     - Velocities (max, min, average).
     - Acceleration (max, min, average).
     - Jerk (max, min, average).
     - Other metrics related to mouse behavior.

2. **Backend:**
   - Developed with Flask.
   - Accepts mouse movement data from the frontend.
   - Uses machine learning or heuristic algorithms to predict if the user is a human or bot.
   - Sends a JSON response indicating the result.

3. **Real-Time Interaction:**
   - User-friendly interface for checking CAPTCHA.
   - Lightweight and efficient communication between frontend and backend.

---

## Project Structure

```
One-ClickCaptcha/
├── frontend/
│   ├── index.html               # Main HTML file for the CAPTCHA interface
│   ├── styles.css               # CSS file for styling the frontend
│   ├── script.js                # JavaScript file for capturing mouse movement and interaction
├── backend/
│   ├── app.py                   # Flask application entry point
│   ├── model/                   # Directory for ML or heuristic models
│   │   ├── predictor.py         # Prediction logic for identifying bots
│   └── utils/                   # Helper functions for data processing
│       ├── physics.py           # Data preprocessing functions
│       └── example.csv          # Example csv file of the data extracted in Frontend
├── ml/
│   └── One-ClickCaptcha.ipynb   # Helper functions for data processing
├── README.md                    # Project documentation
└── requirements.txt             # Python dependencies for the backend
```

---

## Getting Started

### Prerequisites

1. **Frontend Requirements:**
   - A modern web browser.
   - No additional installations are required.

2. **Backend Requirements:**
   - Python 3.8 or later.
   - Install dependencies from `requirements.txt`:
     ```bash
     pip install -r requirements.txt
     ```

---

### Running the Project

1. **Start the Backend:**
   - Navigate to the `backend` directory:
     ```bash
     cd backend
     ```
   - Run the Flask app:
     ```bash
     python app.py
     ```
   - By default, the backend will be available at [http://127.0.0.1:5000](http://127.0.0.1:5000).

2. **Start the Frontend:**
   - Open `index.html` in your preferred web browser.

3. **Test the CAPTCHA:**
   - Interact with the CAPTCHA button on the frontend.
   - The frontend will collect mouse data and send it to the backend for prediction.

---

## API Details

### Endpoint: `/predict`
- **Method**: `POST`
- **Request Body**:
  - Mouse movement data in JSON format, e.g.:
    ```json
    {
      "velocities": { "max": 25, "min": 5, "avg": 15 },
      "accelerations": { "max": 30, "min": 10, "avg": 20 },
      "other_metrics": { "example_metric": 12.5 }
    }
    ```
- **Response**:
  - JSON response indicating if the user is human or bot:
    ```json
    {
      "is_human": true,
      "confidence_score": 0.92
    }
    ```

---

## License

This project is licensed under the MIT License
---
