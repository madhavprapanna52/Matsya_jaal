🕸️ Matsya_Jaal — A Machine Learning-based Phishing Email Detection System
“Where Dharma is protected, Victory is assured.”
A project that stands as the Matsya Avatār against the rising ocean of scam and phishing attacks. Developed with the intent to protect digital users by identifying and filtering malicious content using machine learning.

📂 Project Structure
markdown
Copy
Edit
/Scam_detection_system
│
├── /Dataset
│   ├── cleaned_dataset.csv
│   └── Phishing_Email.csv
│
├── /Project_files
│   ├── __pycache__/
│   ├── Data_preprocessing_unit.py
│   ├── Feature_extraction_unit.py
│   ├── Model_train.py
│   ├── My_basic_tool.py
│   ├── Pramukh_cli.py
│   ├── logistic_model.pkl
│   ├── logistic_vectorizer.pkl
│   └── Development_documentation.txt
│
└── Data_set.csv
🧠 Functional Overview
1. Data_preprocessing_unit.py
Cleans the dataset: tokenizes text, stems words, and removes irrelevant data. This process reduces noise and improves the quality of inputs, resulting in better computational efficiency and meaningful mathematical interpretations for model training.

2. Model_train.py
Trains a Logistic Regression model using a Bag-of-Words vectorization technique.

Utilizes Scikit-learn for auto-optimization.

Achieves 95% accuracy on test data (20% split).

Saves both model and vectorizer using pickle.

3. Pramukh_cli.py
Your divine console — the Command Line Interface for real-time predictions.

Takes user input (email text)

Passes it through the vectorizer and model

Predicts whether the content is phishing or not

⚙️ Setup & Usage
🔧 Environment Setup
bash
Copy
Edit
python3 -m venv matsyajaal_env
source matsyajaal_env/bin/activate  # On Windows use `.\matsyajaal_env\Scripts\activate`
python --version  # Ensure it's Python 3.9.10
📦 Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
🚀 Run the Project
Option 1: Use Pre-trained Model
bash
Copy
Edit
python Project_files/Pramukh_cli.py
Option 2: Train on New Data
bash
Copy
Edit
# Step-by-step
from Project_files.My_basic_tool import clean_dataset
from Project_files import Data_preprocessing_unit
from Project_files import Model_train

# Now run CLI
python Project_files/Pramukh_cli.py
🔮 Potential Upgrades & Vision
✅ Integrate larger and multilingual datasets
✅ Add a deep NLP engine for emotion/sentiment-based detection
✅ Introduce Reinforcement Learning to allow feedback-driven personalization
✅ Move to TensorFlow/Keras for stacked model performance
✅ CUDA-powered neural training for speed and efficiency

⚠️ Challenges & Immediate Improvements
Improve feature extraction with advanced NLP libraries like spaCy, BERT, or FastText

Implement neural networks to detect complex and context-aware phishing attempts

Build GUI and API integrations for wide usability

Test on multilingual datasets to increase coverage

✨ Contribution & Future Plan
This project is a starting point. Soon, we aim to:

Integrate this system into a secure application

Offer public access to real-time phishing detection

Enable user feedback loops for improvement

Collaborate with cyber security and digital safety campaigns

“May Matsya Jaal be the first ripple that becomes a wave of safe digital evolution.”
