# 🎬 Content-Based Cinematic Recommendation Engine

**Content-Based Cinematic Recommendation Engine** is an end-to-end machine learning application that analyzes movie metadata to deliver highly personalized film suggestions. By leveraging Natural Language Processing (TF-IDF vectorization) and cosine similarity, the engine understands the thematic elements of a movie to find its closest matches. The project features a decoupled microservice architecture, with a high-performance FastAPI backend serving the ML inferences and a responsive Streamlit frontend that enriches the user experience using live data from the TMDB API.

The backend is deployed on **Render**, and the Streamlit frontend consumes the deployed API to provide real-time movie recommendations.

---

## 👨‍💻 Author  

**TechyKunj**

---

## 🚀 Live Architecture  

```
User → Streamlit UI → Render (FastAPI Backend) → TF-IDF Model → Recommendations
```

---

## 📂 Project Structure  

```
.
├── app.py                    # Streamlit Frontend
├── main.py                   # FastAPI Backend
├── movies.ipynb              # Data preprocessing & model building
├── movies_metadata.csv       # Dataset
├── df.pkl                    # Processed dataframe
├── tfidf.pkl                 # TF-IDF vectorizer
├── tfidf_metrix.pkl          # TF-IDF matrix
├── indices.pkl               # Movie indices mapping
├── requirements.txt
├── runtime.txt
├── .python-version
└── .gitignore
```

---

## 📊 Dataset  

- `movies_metadata.csv`
- Contains movie title, overview, genres, and other metadata.

---

## 🧠 How It Works  

### 1️⃣ Data Processing (movies.ipynb)

- Clean null values  
- Select important columns (title, overview, genres)  
- Apply TF-IDF Vectorization  
- Compute cosine similarity  
- Save processed files:
  - `df.pkl`
  - `tfidf.pkl`
  - `tfidf_metrix.pkl`
  - `indices.pkl`

---

### 2️⃣ Backend (FastAPI – main.py)

- Loads saved pickle files  
- Exposes recommendation API  
- Deployed on Render  

### API Endpoint

```
GET /recommend/{movie_name}
```

Example:

```
https://your-render-app.onrender.com/recommend/Inception
```

### 3️⃣ Frontend (Streamlit – app.py)

- Takes movie name input  
- Sends request to Render backend  
- Displays recommended movies  

## 🛠️ Tech Stack  

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- FastAPI  
- Uvicorn  
- Streamlit  
- Render (Cloud Deployment)

---

## ⚙️ Run Locally  

### 1️⃣ Install Dependencies

```
pip install -r requirements.txt
```

### 2️⃣ Run FastAPI Backend

```
uvicorn main:app --reload
```

Open:
```
http://127.0.0.1:8000/docs
```

### 3️⃣ Run Streamlit Frontend

```
streamlit run app.py
```

---

## ☁️ Backend Deployment (Render)

- Connect GitHub repository  
- Use start command:

```
uvicorn main:app --host 0.0.0.0 --port 10000
```

- Python version specified in:
  - `runtime.txt`
  - `.python-version`

---

## 📈 Future Improvements  

- Add movie posters  
- Add rating-based filtering  
- Add collaborative filtering  
- Deploy frontend on Streamlit Cloud  
- Add Docker support  

---

## 📌 Key Learnings  

- End-to-end ML project deployment  
- TF-IDF + Cosine Similarity  
- REST API development with FastAPI  
- Cloud deployment on Render  
- Frontend-backend integration  

---

## 📄 License  

MIT License  
