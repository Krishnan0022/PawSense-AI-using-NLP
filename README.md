# 🐾 PawSenseAI
### AI-Based Pet & Cattle Health Assistance Chatbot

PawSenseAI is an NLP-driven conversational system designed to assist pet owners and cattle farmers with health, nutrition, and general care queries. The system combines semantic search with transformer-based response generation to provide context-aware answers through a Streamlit web interface.

---

## 📌 Overview

PawSenseAI integrates:

- Semantic Search using **SentenceTransformer (MiniLM)**
- Response generation using **fine-tuned FLAN-T5**
- **Firebase Realtime Database** for storing cattle health records and embeddings
- **Streamlit UI** for interactive access
- Optional **Speech-to-Text** and **Text-to-Speech** support

The application supports two service modes:
- 🐶 Pet Care Chatbot
- 🐄 Cattle Care Chatbot

---

## 🧠 System Workflow

1. User selects Pet Care or Cattle Care.
2. User submits a natural language query (text or speech).
3. Query is converted into embeddings using MiniLM.
4. Semantic similarity search retrieves top relevant Q&A pairs from Firebase.
5. A few-shot prompt is constructed using retrieved results.
6. The prompt is passed to the fine-tuned FLAN-T5 model.
7. Generated response is displayed and optionally converted to speech.
8. Session history is maintained during runtime.

This pipeline enables context-aware responses instead of purely generic answers.

---

## 🛠️ Tech Stack

### Programming & Framework
- Python
- Streamlit

### NLP & ML
- Hugging Face Transformers
- FLAN-T5 (fine-tuned)
- SentenceTransformers (MiniLM)
- TensorFlow
- PyTorch (for embeddings)

### Database
- Firebase Realtime Database

### Speech Integration
- Google Speech-to-Text API
- gTTS (Google Text-to-Speech)

---

## 📂 Dataset Preparation

Data was collected and structured in Q&A format from:
- Public datasets (e.g., Kaggle)
- Veterinary resources
- Web-scraped sources (processed using BeautifulSoup)

Preprocessing steps:
- Text cleaning
- Tokenization
- Input-output formatting
- Tensor conversion
- Train-validation split

Embeddings were generated using MiniLM and stored for semantic retrieval.

---

## 🔍 Model Training

FLAN-T5 was:
- Loaded from a pretrained checkpoint
- Fine-tuned on curated pet and cattle care Q&A datasets
- Trained with defined hyperparameters (epochs, batch size, learning rate)

### Evaluation Metrics
- ROUGE Score
- BLEU Score
- F1 Score (for classification tasks)

---

## 📊 Preliminary Results

- Speech-to-Text accuracy ~90% in controlled environments
- Average response time: 2–3 seconds per query
- Secure handling of cattle health records in Firebase
- Context-aware responses generated using retrieval + generation pipeline

---

## 💡 Key Features

- Multi-species support (Pets & Cattle)
- Semantic retrieval before text generation
- Context-based few-shot prompting
- Optional voice input and output
- Session memory tracking
- Real-time database integration

---

## 🖥️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/PawSenseAI.git
cd PawSenseAI
