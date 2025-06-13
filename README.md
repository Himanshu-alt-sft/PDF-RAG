# PDF-RAG

---

## 🧠 What It Does

This project creates a **Retrieval-Augmented Generation (RAG)** pipeline that:

1. 🧾 Loads a PDF (like Tanenbaum OS)
2. ✂️ Chunks the text intelligently into groups of sentences
3. 🧠 Generates embeddings for semantic search using `sentence-transformers`
4. 🔍 Retrieves relevant chunks based on your query
5. 🤖 Uses a local LLM (TinyLlama) to generate an answer in natural language

---

## 🚀 Features

- ✅ PDF chunking with sentence-level granularity  
- ✅ Sentence embedding via `all-mpnet-base-v2` on GPU  
- ✅ Fast semantic retrieval using dot product  
- ✅ Answer generation via TinyLlama 1.1B  
- ✅ Can be extended for **formula extraction**, glossary generation, or flashcard prep  

---

## 📁 Project Structure

```
📦 rag-pdf-assistant/
┣ 📄 main.py                            <- Main script
┣ 📄 page_and_text.json                 <- Page-level text + stats
┣ 📄 page_and_text_with_sentences.json <- Sentence chunks
┣ 📄 text_chunk_embeddings.csv          <- (Not uploaded due to size)
┣ 📄 README.md
```

---

## ⚙️ Requirements

- Python 3.8+
- CUDA GPU (for fast embeddings + LLM inferencing)
- Libraries:

```bash
pip install sentence-transformers pandas tqdm transformers pymupdf spacy torch
python -m spacy download en_core_web_sm
```

---
You'll be prompted to:
- Paste a URL to download a textbook PDF  
- Ask questions like:
  - *"What is an operating system?"*
  - *"Explain process scheduling."*
  - *"List types of deadlock handling."*
Output will show:
- Relevant chunk context
- Generated answer
---
## 📘 Example Queries
> **Query**: *What is an operating system?*  
> **Answer**: *An operating system is software that manages hardware and software resources...*
---
Credits

This project was inspired by the amazing content of [Daniel Bourke](https://www.youtube.com/@Mrdbourke), especially his work on:
- Machine learning & NLP
- Practical LLM usage
- Making AI stuff not boring
