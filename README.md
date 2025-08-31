# Google Location Review Detector

## 🚀 Project Overview
This project is an automated system to check the quality and relevance of Google location reviews.  
It detects violations like **spam, ads, irrelevant content, or rants without a visit** using a **custom DistilBERT model**.  

You upload a CSV of reviews → it outputs:  
- ✅ Clean reviews  
- ⚠️ Flagged reviews  
- 📊 A summary report  

This was built for **TikTok TechJam 2025, Track 1: Filtering the Noise – ML for Trustworthy Location Reviews**.  

---

## ⚡ Quick Setup (Best with Google Colab)
1. **Download** this project and upload it to your Google Drive.  
2. Open `track1.ipynb` in Colab.  
3. Switch to a GPU runtime.  
4. Run the **import modules** cell.  
5. Scroll to the **Showcase** section → run all cells below.  
6. A **Gradio app** will launch → upload your CSV and get predictions instantly.  

👉 If you don’t want to train from scratch, download the pre-trained model.  
👉 To use LLM-based pseudo-labeling, make sure you have a **Groq Cloud API key**.  

---

## 👨‍💻 Contribution
- **Sidharth Vinod** – Designed and implemented everything: preprocessing, feature engineering, pseudo-labeling (LLMs via Groq), model development, fine-tuning, evaluation, and deployment with Gradio.  

---

## 🧠 Model Info
- **Base:** `distilbert-base-uncased`  
- **Custom Head:** Combines text embeddings + engineered features (`review_length`, `polarity`, `suspicion_score`, `subjectivity`, `rating`).  
- **Training:** Fine-tuned on a labeled subset of the UCSD Google Maps Reviews dataset (New York), with class-weighted loss for imbalance.  

---
