# AI-Driven Mid-Air Collision Avoidance System

## Table of Contents
- [Introduction](#introduction)
- [Team Contributions](#team-contributions)
- [Key Features](#key-features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Trustworthiness Evaluation](#trustworthiness-evaluation)
- [How to Run](#how-to-run)
- [References](#references)
- [Important Notes](#important-notes)

---

## Introduction

With growing air traffic, the need for smarter, adaptable mid-air collision avoidance is critical. Traditional systems like TCAS and ADS-B are limited in scope—they’re rule-based and reactive.

Our project introduces an AI-driven approach that combines **reinforcement learning (DQN & PPO)** with **LLM-based explanations**, allowing the system to learn safe maneuver strategies and explain them in human-readable language. The system is tested in real-time and simulated environments using flight telemetry data from the OpenSky Network.

---

## Team Contributions

- **Nehan – Data Pipeline & Feature Engineering**  
  Processed real-world flight data, extracted key features (e.g., TTC, vertical rate), and handled noisy/missing data simulation.

- **Sai Krishna – Model Development & Training**  
  Built and trained PPO and DQN models, tuned hyperparameters, and implemented reward strategies.

- **Radha – System Integration & LLM Explainability**  
  Integrated environment, models, and UI. Connected LLM to generate action explanations and built real-time feedback logic.

---

## Key Features

- **Real-Time Flight Data + Simulated Backup** via OpenSky API
- **Custom RL Environment** with collision-specific observations & rewards
- **Explainable AI** using Google Gemini for action interpretation
- **Multiple Scenarios** tested: normal, noisy, missing features
- **Interactive Dashboard UI** (Flask + JS + Collapsible Modules)
- **Model Comparison:** PPO vs DQN under different airspace conditions

---

## Technologies Used

- **Reinforcement Learning**: PPO, DQN (Stable-Baselines3)
- **Environment**: OpenAI Gymnasium
- **Explainability**: Google Gemini 1.5 Pro
- **Web UI**: Flask, Chart.js, HTML/CSS
- **Data Handling**: Pandas, NumPy
- **Training Platform**: Google Colab & Local

---

## Project Structure
```
📁 AI_MidAir_Collision_Avoidance/
├── app.py
├── requirements.txt
├── README.md
│
├── data/
│   ├── clean_data.csv
│   ├── noisy_data.csv
│   ├── missing_features_data.csv
│
├── models/
│   ├── dqn_model.zip
│   └── ppo_model.zip
│
├── env/
│   └── collision_env.py
│
├── utils/
│   ├── data_utils.py
│   ├── llm_explainer.py
│   └── risk_assessment.py
│
├── scripts/
│   ├── train_models.py
│   └── testfile.py
│
├── static/
│   ├── flight.png
│   └── style.css
│
└── templates/
    └── dashboard.html
```


---

## ⚙️ Installation & Setup

### 📦 Requirements
- Python 3.10 or higher (Python 3.13 recommended)
- Git
- Internet connection (for Gemini API access)

---

### 🔹 1. Clone the Repository
```bash
git clone https://github.com/your-username/AI_MidAir_Collision_Avoidance.git
cd AI_MidAir_Collision_Avoidance
```

---

### 🔹 2. Create and Activate Virtual Environment

#### Windows:
```bash
python -m venv .venv
.\.venv\Scripts\activate
```

#### macOS/Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

### 🔹 3. Install Required Dependencies
```bash
pip install -r requirements.txt
```

---

### 🔹 4. Set Gemini API Key

#### Option 1: Using a `.env` file
Create a file named `.env` in the project root with the following line:
```
GOOGLE_API_KEY=your_actual_api_key_here
```

#### Option 2: Export manually

- **Windows (PowerShell):**
```bash
$env:GOOGLE_API_KEY="your_actual_api_key_here"
```

- **macOS/Linux:**
```bash
export GOOGLE_API_KEY="your_actual_api_key_here"
```

---

### 🔹 5. Launch the Application
```bash
python app.py
```

Then visit [http://127.0.0.1:5000](http://127.0.0.1:5000) in your browser.

---

## 🧪 Trustworthiness Evaluation

We focused on **robustness** and **generalization**, using the following strategies:

- **Noisy Data Testing**: Introduced Gaussian noise to altitude, velocity, and heading values.
- **Missing Feature Simulation**: Randomly removed critical fields (e.g., altitude, velocity) to simulate real-world data loss.
- **Fairness Checks**: Verified that model actions varied with context and did not overfit to specific types of aircraft or altitude.
- **Generalization**: Evaluated model behavior on unseen simulated airspaces.

Results showed that **PPO was more stable**, and the LLM provided clear explanations even under degraded inputs.

---
## ▶️ How to Run the Application

Once you've completed the setup, follow these steps to run the system:

```bash
# Activate your virtual environment
# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate

# Start the Flask server
python app.py
```

After running the above command, the system will start on your local machine.  
Open your browser and visit:

```
http://127.0.0.1:5000
```

You’ll see the AI-powered mid-air collision avoidance dashboard where you can:
- Select different test scenarios (Normal, Noisy, Missing Features)
- Choose between PPO and DQN models
- View observations, actions, rewards, and natural language explanations

---
## 📚 References

- "Optimizing the Next Generation Collision Avoidance System for Safe, Suitable, and Acceptable Operational Performance"  
  *Authors: M. A. Vivona, R. J. Moss, and J. Kuchar*
- PPO Algorithm: Schulman et al. — *"Proximal Policy Optimization Algorithms" (2017)*
- DQN Algorithm: Mnih et al. — *"Playing Atari with Deep Reinforcement Learning" (2015)*

---

## 💻 Code Sources

This project was fully developed by our team, including custom data pipelines, collision avoidance environments, reward functions, and integration of PPO/DQN models using **Stable-Baselines3**.  
We also implemented an **LLM-based explanation system** using **Google Gemini 1.5 Pro**, and built a web-based interactive dashboard using **Flask**.

While we relied on open-source libraries such as Stable-Baselines3, Gymnasium, Optuna, and the OpenSky Network API, all implementations followed official documentation and were customized for our specific use case.

---

## 📌 Important Notes

To ensure stable, controlled, and reproducible testing during the demonstration phase, we used structured simulated datasets derived from real flight telemetry.  
This approach enabled consistent evaluation of the AI models under clean, noisy, and missing-data conditions.

- ✅ Preserved the goal of showcasing how reinforcement learning can optimize mid-air collision avoidance.
- ✅ Delivered a professional, consistent demo highlighting the power of AI and **LLM-based explainability**.

---

## 🤖 LLM Explainability

- Integrated **Gemini AI** to explain reinforcement learning decisions.
- Helps improve **AI transparency**, **safety assurance**, and builds **trust** with human operators.





