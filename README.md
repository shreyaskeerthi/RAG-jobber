# RAG-jobber
A lightweight retrieval-augmented generation (RAG) tool that takes a CSV of job descriptions and helps you quickly understand, analyze, and compare roles using LLMs.


## What this is  
A local RAG app that helps me analyze and talk about job listings pulled from a CSV of a scraped a job board.  
It uses embeddings + LLMs to break down what roles are really asking for.

Built so I can:
- Understand different job postings in one place
- Ask natural questions about them
- Quickly get summaries of top skills, responsibilities, and fit

---

## 💡 Why I Built It  
I had a CSV full of job descriptions. Reading each one, taking notes, comparing them — it was slow.  
This setup lets me just ask a question and get a structured answer. It’s like having a smart filter for job listings.

---

## ⚙️ How It Works

- CSV → LangChain `Document`s
- Text split + embedded (5 models tested)
- Stored in Chroma
- Queried via RAG using:
  - `Mistral` (via Ollama)
  - `DeepSeek-Coder` (via Ollama)
- Prompts dynamically built for each query

---

## 🧪 Benchmarked It Too

I tested 5 different embeddings across both models to find the fastest + most complete combo:

- Measured:
  - Response time
  - Output length
  - Efficiency (chars/sec)
- **Winner**: `E5-Small` + `DeepSeek`
  - Fast
  - Detailed
  - Doesn’t waste time

> This is what powers the app now. Speedy, useful, clean.

---

## 🚀 Usage
1. Install dependencies  
```bash
pip install pandas langchain chromadb sentence-transformers llama-cpp-python matplotlib seaborn
```
2. Drop in your job listings CSV (e.g., `linkedin_jobs_complete.csv`)
3. Run the script or notebook:
   - It’ll embed your jobs
   - Build the vectorstore
   - Let you type any question (e.g., “What are the top skills for these roles?”)
   - Returns an answer using your chosen LLM

---

## 📈 Visuals

- Charts for:
  - Timing  
  - Output length  
  - Efficiency  
- Logs everything cleanly per model/embedding

---

## 🧠 Ideal For

- Anyone applying to lots of roles  
- Anyone recruiting/hiring across technical job families  
- Anyone trying to extract meaning from unstructured job descriptions  

---
## 🚀 Future Implementation (Works-In-Progress):

- Testing and validating stronger models such `e5-mistral-7b`,  `e5-large`, and `e5-xl`
- Integrating scraper and csv generator into the pipeline
- Attempting to take it to a point of using it as a way to query the corpus

---


## ✍️ Author  
**Shreyas Keerthi**  
