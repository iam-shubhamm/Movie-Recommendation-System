🎬 Movie Recommendation System


🌐 Live Demo
    👉[ https://your-app-name.streamlit.app](https://movie-recommendation-system-nrnbqlvq4bvmakhktzcd88.streamlit.app/)
    
📌 Introduction

    Modern streaming platforms such as Netflix and Amazon Prime Video host thousands of movies, making it difficult for        users to discover relevant content efficiently. This project implements a Content-Based Movie Recommendation System that suggests movies based on similarity of content features such as genres, keywords, cast, and overview.

🎯 Business Objective

    The system aims to:
        ⏳ Reduce user decision time
        📈 Increase engagement
        🎯 Improve recommendation accuracy
        😊 Enhance user experience
        👉 This is similar to real-world recommendation systems used in OTT platforms.

🧠 Recommendation System Type
        
    🔹 Content-Based Filtering
        This system recommends movies based on similarity between movie features.

    🔍 Why Content-Based?
        No need for user history
        Works well for new users
        Easy to interpret
        Scalable for small datasets
        
🛠️ Tech Stack

    🐍 Python
    📊 Pandas
    🔢 NumPy
    🤖 Scikit-learn
    🌐 Streamlit
    
📂 Dataset
    
    🔹 Source
        TMDB Movie Dataset (Kaggle)
    🔹 Features Used
        Feature                  	Description
        title	                    Movie name
        overview	                Description of movie
        genres	                    Categories
        keywords	                Important tags
        cast                    	Actors
        crew	                    Director

⚙️ System Architecture

    Raw Data → Preprocessing → Feature Engineering → Vectorization → Similarity → Recommendation → UI (Streamlit)

🧹 Data Preprocessing

    Removed missing values
    Merged movies and credits datasets
    Selected relevant columns
    Converted JSON-like columns using ast.literal_eval
    Extracted:
        Top 3 cast members
        Director name
        
🏗️ Feature Engineering

    Created a new feature called tags by combining:
        Genres
        Keywords
        Overview
        Cast
        Crew


🔤 Text Normalization

    Converted all text to lowercase
    Removed spaces from names
    Applied stemming (PorterStemmer)
    Example:
    running → run
    movies → movi
    👉 Helps reduce dimensionality and improve similarity

🔢 Vectorization

    Used:
    🔹 CountVectorizer
    🔹  Converts text into numerical vectors
    🔹 Uses Bag-of-Words approach
        Example:
        Movie A → [1,0,2,1,0...]
        Movie B → [0,1,1,0,2...]
        
📏 Similarity Calculation

        Used:
            🔹 Cosine Similarity
            🔹 Formula:
                    cos(θ) = (A · B) / (||A|| × ||B||)
    👉 Measures angle between vectors instead of distance
                1 → highly similar
                0 → not similar
⚡ Recommendation Algorithm

    Steps:
    User selects a movie
    Find movie index
    Get similarity scores
    Sort in descending order
    Return top 5 similar movies

📊 Example

    🎯 Input:
        Avatar
    ✅ Output:
        Guardians of the Galaxy
        John Carter
        Star Trek
        Avengers

