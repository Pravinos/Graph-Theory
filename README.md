# Community Detection in Scientific Articles

## 📌 Project Overview
This project focuses on **finding subject areas for scientific articles based on their titles and abstracts** using **network theory and community detection algorithms**.  

The dataset consists of approximately **20,000 scientific articles** with metadata including:
- Article **ID**
- **Title**
- **Abstract**
- Subject area indicators (e.g., *Computer Science, Physics, Mathematics, Statistics, Quantitative Biology, Quantitative Finance*).

The primary goal was to:
1. Build a **network graph** where:
   - Nodes represent articles.
   - Edges represent semantic similarity between articles (based on embeddings).
2. Detect **communities** within the graph using **Louvain community detection**.
3. Evaluate how well the detected communities align with the provided subject areas using metrics such as the **Fowlkes–Mallows score**.

This project was developed as part of the course **“Network Theory”** (Winter Semester 2022–23).

---

## ⚙️ Methodology

1. **Data Preprocessing**
   - The input dataset is provided as a `CSV` file (`train.csv`).
   - Each article has one or more subject area labels.
   - A subset of 500 articles was used for experiments.

2. **Text Embeddings**
   - The **Sentence-Transformers** library (`all-MiniLM-L6-v2`) was used to generate embeddings from:
     - **Titles**
     - **Abstracts**

3. **Graph Construction**
   - Constructed an **undirected weighted graph** using **NetworkX**:
     - **Nodes**: individual articles.
     - **Edges**: similarity between articles (measured by **cosine similarity** of embeddings).
     - Applied a similarity threshold (`> 0.2`) to filter meaningful connections.

4. **Community Detection**
   - Applied the **Louvain algorithm** (`community_louvain.best_partition`) to partition the network into communities.
   - Each community groups articles with high semantic similarity.

5. **Evaluation**
   - Compared detected communities against ground truth subject areas.
   - Used **Fowlkes–Mallows score (FMI)** to measure clustering quality.
   - Example results:
     - Titles-based graph → **~50.9% FMI**
     - Abstracts-based graph → **~56.4% FMI**

---

## 📊 Example Outputs

- **Communities Detected**:  
  - Titles graph: 6 main communities  
  - Abstracts graph: slightly improved community alignment  

- **Evaluation Metric**:  
  - FMI Score (Titles): `50.90%`  
  - FMI Score (Abstracts): `56.38%`  

---

## 🛠️ Technologies & Libraries

- **Python 3.9**
- [NetworkX](https://networkx.org/) – Graph representation & analysis  
- [Pandas](https://pandas.pydata.org/) – Data manipulation  
- [scikit-learn](https://scikit-learn.org/) – Cosine similarity & evaluation metrics  
- [SentenceTransformers](https://www.sbert.net/) – Embedding generation  
- [Community-Louvain](https://python-louvain.readthedocs.io/) – Community detection  
- **NumPy** – Numerical computations  
