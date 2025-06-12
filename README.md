# Homeopathy-llm-rag

A symptom-based Homeopathy chatbot built using Retrieval-Augmented Generation (RAG). It uses FAISS for similarity search over Phatak Materia Medica and TinyLlama to generate answers. Powered by MiniLM embeddings and served through Gradio.

---

## 🎯 Objective

To help users find relevant homeopathic remedies by querying symptoms and receiving contextually generated answers from a local LLM.

---

## 📚 Data Source

- **Phatak Materia Medica**
- Converted to structured JSON with:
  - `medicine`
  - `symptoms`
  - `description`

---

## 🧱 Tech Stack

| Component         | Tool/Library                                    |
|------------------|--------------------------------------------------|
| Embeddings        | `all-MiniLM-L6-v2` from `sentence-transformers` |
| Vector Store      | FAISS                                            |
| Language Model    | `TinyLlama/TinyLlama-1.1B-Chat-v1.0` (HuggingFace) |
| UI                | Gradio                                           |

---

## ⚙️ How It Works

1. Load `phatak.json` containing homeopathy knowledge
2. Convert each medicine's data to text chunks
3. Generate dense embeddings using MiniLM
4. Store & index these embeddings using FAISS
5. Accept user symptom query via Gradio UI
6. Retrieve most similar entries using FAISS
7. Pass results to TinyLlama LLM via HuggingFace `pipeline`
8. Display generated answer in the chatbot interface

---

## 💬 Example User Queries

- "Remedy for sore throat with cough"
- "What is the treatment for acidity and indigestion?"
- "Tell me about symptoms of Nux Vomica"

---

## 🖥️ How to Run

```bash
# Clone this repo
git clone https://github.com/yourusername/homeopathy-chatbot.git
cd homeopathy-chatbot

# Install required libraries
pip install -r requirements.txt

# Run the notebook
jupyter notebook Copy_of_homeo.ipynb
