import os
import joblib
from fastapi import FastAPI
from pydantic import BaseModel
from sklearn.feature_extraction.text import CountVectorizer
from datetime import datetime
import uvicorn

# === Define paths ===
MODEL_PATH = "/home/madhavr/Desktop/Yantragya_project_1.0/Scam_detection_system/Project_files/logistic_model.pkl"
VECTORIZER_PATH = MODEL_PATH.replace("model", "vectorizer")

# === Load model and vectorizer ===
if not (os.path.exists(MODEL_PATH) and os.path.exists(VECTORIZER_PATH)):
    raise FileNotFoundError("Error: Model or vectorizer file not found. Check paths.")

model = joblib.load(MODEL_PATH)
vectorizer = joblib.load(VECTORIZER_PATH)

# === FastAPI app ===
app = FastAPI(title="Scam Email Detector API", version="1.0")

# === Input schemas ===
class InputData(BaseModel):
    text: str

class FeedbackData(BaseModel):
    input: str
    result: str
    rating: int
    feedback: str

# === Inference endpoint ===
@app.post("/infer")
def infer(data: InputData):
    text = data.text.strip()
    if not text:
        return {"error": "Empty text not allowed."}

    text_vector = vectorizer.transform([text])
    prediction = model.predict(text_vector)[0]
    confidence = model.predict_proba(text_vector)[0][prediction]

    label = "Phishing Email 🚨" if prediction == 1 else "Safe Email ✅"
    return {
        "prediction": label,
        "confidence": round(float(confidence) * 100, 2)
    }

# === Feedback storage (in-memory for now) ===
feedback_store = []

@app.post("/feedback")
def collect_feedback(data: FeedbackData):
    entry = {
        "input": data.input,
        "result": data.result,
        "rating": data.rating,
        "feedback": data.feedback,
        "timestamp": datetime.utcnow().isoformat()
    }
    feedback_store.append(entry)
    return {"message": "Feedback stored successfully", "entry": entry}

@app.get("/feedback")
def get_feedback():
    return {"feedback_entries": feedback_store}

# === Run locally ===
if __name__ == "__main__":
    uvicorn.run("app:app", host="0.0.0.0", port=8080, reload=True)
