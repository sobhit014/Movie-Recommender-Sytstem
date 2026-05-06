# 🎬 Movie Recommender System

A content-based movie recommendation engine built with Python and Streamlit that suggests similar movies based on metadata like genres, keywords, cast, and crew — powered by the TMDB 5000 dataset.

---

## 🚀 Demo

Enter any movie title and get 5 personalized recommendations with posters fetched live from The Movie Database (TMDB) API.

---

## 🧠 How It Works

This is a **content-based filtering** system. It recommends movies by measuring the similarity between their metadata tags (genres, keywords, cast, crew, and overview). The key steps are:

1. **Data Loading** — Loads `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`
2. **Merging** — Combines both datasets on the `title` column
3. **Feature Selection** — Keeps only `movie_id`, `title`, `overview`, `genres`, `keywords`, `cast`, and `crew`
4. **Vectorization** — Converts the combined tags into a feature matrix
5. **Similarity Scoring** — Uses cosine similarity to find the closest matches
6. **Poster Fetching** — Retrieves movie posters live from the TMDB API

---

## 🗂️ Project Structure
Movie-Recommender-System/
│
├── app.py                   # Streamlit web app
├── notebook86c26b4f17.ipynb # Data processing & model building notebook
├── model/
│   ├── movie_list.pkl       # Serialized movie list
│   └── similarity.pkl       # Precomputed cosine similarity matrix
└── README.md

---

## ⚙️ Setup & Installation

### Prerequisites

- Python 3.8+
- A free [TMDB API key](https://www.themoviedb.org/documentation/api)

### Installation

```bash
# Clone the repository
git clone https://github.com/sobhit014/Movie-Recommender-Sytsem.git
cd Movie-Recommender-Sytsem

# Install dependencies
pip install streamlit pandas scikit-learn requests
```

### Running the App

```bash
streamlit run app.py
```

---

## 📦 Dataset

The project uses the [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) from Kaggle, which contains:

- **`tmdb_5000_movies.csv`** — Movie metadata (budget, genres, keywords, overview, etc.) — 4803 movies × 20 columns
- **`tmdb_5000_credits.csv`** — Cast and crew information for each movie

---

## 🔧 Model Details

| Component | Detail |
|-----------|--------|
| Algorithm | Content-Based Filtering |
| Similarity Metric | Cosine Similarity |
| Feature Space | Genres, Keywords, Cast, Crew, Overview |
| Recommendations | Top 5 similar movies |
| Persistence | Pickle (`.pkl`) files for fast loading |

---

## 🔑 API Configuration

The app fetches live movie posters using the TMDB API. Replace the API key in `app.py` if needed:

```python
url = "https://api.themoviedb.org/3/movie/{}?api_key=YOUR_API_KEY&language=en-US".format(movie_id)
```

Get your free API key at [themoviedb.org](https://www.themoviedb.org/settings/api).

---

## 📸 Features

- 🔍 Search from 4800+ movies
- 🎯 Get 5 similar movie recommendations instantly
- 🖼️ Movie posters fetched in real-time from TMDB
- ⚡ Fast inference using precomputed similarity matrix

---

## 🛠️ Built With

- [Pandas](https://pandas.pydata.org/) — Data manipulation
- [Scikit-learn](https://scikit-learn.org/) — Vectorization & cosine similarity
- [Streamlit](https://streamlit.io/) — Web app framework
- [TMDB API](https://www.themoviedb.org/documentation/api) — Movie poster fetching
- [Pickle](https://docs.python.org/3/library/pickle.html) — Model serialization

---

## 👤 Author

**Sobhit Singh R**  
- GitHub: [@sobhit014](https://github.com/sobhit014)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
