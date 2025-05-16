# 🎬 Movie Database Analysis: Data Analysis and Interpretation

**By Ram Kishore Karuppiah Nadar Venkateswaran**  
_With the help of Chaitanya Shashi Kumar and Robert Lignowski_

---

### 📌 Project Overview

This project is the **second phase** of a movie data pipeline. After collecting and enriching metadata from TMDb and Wikipedia in Phase I, this phase focuses on deep analysis using machine learning, NLP, network analysis, and visualizations.

We investigate genre trends, build predictive models, create a movie recommendation system, and explore actor–director relationships — all based on a curated dataset of 7000+ movies spanning 1950 to 2010.

---

### 🎯 Objectives

- Predict movie genres using both SpaCy and Naive Bayes
- Build a TF-IDF based recommendation system
- Visualize genre popularity across decades
- Identify top-rated and most profitable movies, actors, and directors
- Explore actor–director collaborations using network graphs

---

### 📁 Contents

| File                         | Description |
|------------------------------|-------------|
| `merged_movies2.csv`         | Cleaned and merged movie dataset (7,000+ entries) |
| `GenrePredictionML.ipynb`    | ML-based genre prediction using Naive Bayes |
| `FinalSpaCy.ipynb`           | Rule-based genre prediction using SpaCy |
| `recommendation_system.ipynb`| Content-based movie recommendation system |
| `actors_directors_network.ipynb` | Actor–Director network analysis by decade |
| `top_movies.ipynb`           | Identify top movies by box office and ratings per decade |
| `genrepopularity.ipynb`      | Visualization of genre trends over time |
| `Lignowski_Kumar_Kishore_Presentation.pptx` | Final project slides |
| `README.txt`                 | Detailed execution notes for each notebook |

---

### 🚀 How to Run

1. Make sure `merged_movies2.csv` is in the correct path.
2. Open any `.ipynb` file in Jupyter or VS Code and run cell by cell.
3. Follow inline markdown comments to understand each step.

---

### 🧠 Techniques Used

- **NLP with spaCy** for genre inference from plot
- **Naive Bayes** for supervised genre classification
- **TF-IDF + Cosine Similarity** for movie recommendations
- **NetworkX** for actor–director graphs
- **Matplotlib / Seaborn** for visualizations

---

### 📊 Key Insights

- Genre prediction accuracy (Naive Bayes): ~47%
- Recommendation system uses plot similarity + weighted ratings
- Drama, Action, and Comedy remain dominant genres over decades
- Actor–Director networks reveal key recurring collaborators

---

### 🔧 Challenges & Improvements

- NLP-based classification was limited by vague or short plot summaries
- Some recommendations were loosely relevant due to plot overlap
- Ratings were attributed to movies, not individuals — may introduce bias
- Future work: use deep learning models and custom similarity metrics

---

### 👥 Acknowledgments

This project was completed by  
**Ram Kishore KV**  
with the help of **Chaitanya Shashi Kumar** and **Robert Lignowski**  
for coursework at **Drexel University**.

---

