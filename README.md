# 🛍️ AI Fashion Recommendation Engine using NLP, Transformers, and Semantic Search

An end-to-end Natural Language Processing (NLP) pipeline designed to optimize fashion e-commerce discovery. This project handles unstructured retail data, builds an intelligent semantic search database, generates automatic review text summaries, and implements a multi-approach Named Entity Recognition (NER) framework to index product traits dynamically.

---

## 🎯 Project Objectives

* **Semantic Search:** Replace rigid keyword search with contextual sentence understanding to capture aesthetic vibes.
* **Review Summarization:** Compress multi-paragraph customer reviews into quick, two-line styling summaries.
* **Feature & Attribute Mining:** Automatically isolate raw text elements into clean clothing metadata tags (fabrics, silhouettes, categories).
* **Interactive Query Execution:** Build a live-inference command-line pipeline that allows real-time customer profile matching.

---

## 📂 Dataset Profile

The project utilizes the **ECommerce Women's Clothing Reviews** dataset, mapping thousands of customer shopping logs.

* **Key Features Processed:** `Title` and `Review Text`.
* **Target Focus:** Merging user headline feedback and raw review paragraphs into unified document-level semantic representations (`paper_text`).

---

## 🛠️ Tech Stack & Libraries

* **Vector DB & Search:** FAISS (Facebook AI Similarity Search - `IndexFlatIP`)
* **Text Embedding:** SentenceTransformers (`all-MiniLM-L6-v2`)
* **Text Summarization:** Hugging Face Pipelines (`facebook/bart-large-cnn`)
* **Named Entity Recognition (NER):** 
  * *Deep Learning Model:* Transformers Token Classification (`dslim/bert-base-NER`)
  * *Rule-Based Model:* Custom Regular Expressions (Regex) Fashion Dictionary
* **Data Wrangling:** Pandas, NumPy

---

## 📈 Key Components & System Pipeline

### 1. Vector Indexing & Semantic Search
Standard searches miss textual nuances. By encoding full review paragraphs into **384-dimensional dense vectors** and indexing them via **FAISS L2-normalized Inner Product similarity**, the search engine dynamically processes descriptive lifestyle requirements like *"baggy jeans"* or *"lightweight dress for beach"* rather than relying on exact product title matching.

### 2. Transformer-Based Review Summarization
Using a state-of-the-art **BART Large CNN architecture**, long and detailed customer feedback strings are read and parsed on the fly. The pipeline dynamically reduces text layout noise, delivering an immediately readable styling verdict summarizing the overall product fit and comfort.

### 3. Dual-Approach Named Entity Recognition (NER)
To capture explicit metadata without manual text tagging, the engine applies two distinct structural extraction layers side-by-side:
* **Approach 1 (Hugging Face Transformers):** Leverages a deep learning `BERT-NER` pipeline to identify proper structural names and geographic locations (e.g., *Paris, California*).
* **Approach 2 (Custom Pattern Fashion-NER):** Employs an exact boundary regex dictionary engine built to immediately pull out retail-specific features across fabrics, sizes, and styling categories.

---

## 🤖 Engine Pipeline Sample Output

When a user executes a search query, the complete system generates a synchronized real-time extraction log:

```text
COMPLETE AI ENGINE PIPELINE FOR QUERY: 'BAGGY JEANS'
------------------------------------------------------------

Similarity Score: 0.7
Review Title: Waist gets baggy with wear
AI Summary: The waist is really baggy. the fabric stretches with wear and takes a wash to get back to its original shape.

--------------------------------------------------
OUTPUT FOR APPROACH 1: HUGGING FACE BERT-NER
No standard entities found.
--------------------------------------------------
OUTPUT FOR APPROACH 2: CUSTOM DICTIONARY FASHION-NER
Categories Detected: jeans
============================================================

🚀 Future Roadmap
[ ] Connect the complete search pipeline backend to an interactive visual web interface using Streamlit.

[ ] Integrate KeyBERT tokenizers to output multi-word trend tags dynamically beside fashion metrics.

[ ] Port the localized .npy embedding framework to an online cloud vector store for real-time dataset indexing.

📄 Conclusion
This repository demonstrates a clean blueprint for modern intelligent e-commerce platforms. It bridges the gap between deep contextual understanding and automated feature extraction, turning unorganized text streams into structured, queryable retail assets.
