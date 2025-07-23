# Movie Recommendation System

## Overview
This repository features a **Content-Based Movie Recommendation System** designed to provide personalized movie suggestions. Leveraging natural language processing and machine learning techniques, the system analyzes movie content to find and recommend films similar to a user's preferences. 

## Features
* **Content-Based Filtering:** Recommends movies based on the similarity of their content (genres, cast, director, keywords, plot summaries, etc.) to a given movie or user preference.

* **Interactive User Interface:** Built with `Streamlit`, providing an easy-to-use web interface for users to get movie recommendations.

* **Model Persistence:** The processed data and similarity matrix are serialized using `pickle` for efficient loading and prediction without re-processing the entire dataset every time.

## Technologies Used
* **Python:** The core programming language.

* **Jupyter Notebook:** Used for exploratory data analysis, model development, and experimentation.

* **Pandas:** For efficient data manipulation and analysis of the movie dataset.

* **scikit-learn (sklearn):** Specifically for `CountVectorizer` and `cosine_similarity`.

* **Pickle:** For serializing and deserializing Python objects, particularly the processed movie data or recommendation model.

* **Streamlit:** For creating the interactive web application that serves the recommendations.

## Model Used
The core of this content-based recommendation system relies on the following components:
* **Feature Extraction:** Movie attributes such as genre, keywords, cast, and director are combined into a single string for each movie.

* **Text Vectorization:** `CountVectorizer` from `scikit-learn` is used to convert this combined textual data into a sparse matrix of token counts. Each movie is represented as a vector in this high-dimensional space, where each dimension corresponds to a unique word/token.

* **Similarity Measurement:** `Cosine Similarity` is then applied to these vectorized representations. Cosine similarity measures the cosine of the angle between two vectors, indicating how similar they are. A higher cosine similarity score indicates greater similarity between movies' content profiles.

## Data Processing
The development process involved thorough data analysis and a structured training approach.

### Data Analysis

* **Initial Data Inspection:** The TMDB Movies Dataset was loaded into a Jupyter Notebook to inspect its structure, identify relevant columns (e.g., `genres`, `keywords`, `cast`, `crew`, `overview`, `title`), and check for missing values or inconsistencies.

* **Feature Selection:** Key textual and categorical features crucial for defining movie content were identified and extracted.

* **Text Cleaning:** Basic text preprocessing steps were performed on relevant text columns, which might include converting to lowercase, removing punctuation, and handling potential formatting issues to prepare data for vectorization.

## Model Training

1.  **Feature Combination:** Relevant textual features (e.g., `genres`, `keywords`, `cast`, `director`, `overview`) for each movie were combined into a single string. This unified text provides a comprehensive content profile for each film.

2.  **Vectorization (CountVectorizer):** An instance of `CountVectorizer` was fitted on the combined text data from all 10,000 movies. This step builds a vocabulary of all unique words/tokens across the dataset and transforms each movie's text into a numerical vector based on the frequency of these tokens.

3.  **Similarity Matrix Generation:** The `cosine_similarity` function was applied to the output of the `CountVectorizer`. This generated a large square matrix where each element `(i, j)` represents the cosine similarity between movie `i` and movie `j`. This matrix is the heart of the recommendation engine, allowing for quick retrieval of similar movies.

4.  **Model Serialization:** Both the fitted `CountVectorizer` object and the calculated `cosine_similarity` matrix were saved (`pickled`) to disk. This allows the Streamlit application to load these pre-computed components quickly without needing to re-process the entire dataset upon startup, significantly improving performance.


## Dataset
* **Name:** TMDB Movies Dataset from Kaggle

## How to Run the Project
To view this project locally on your machine:

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/sjain2580/oaqjp-final-project-emb-ai.git](https://github.com/sjain2580/oaqjp-final-project-emb-ai.git)
    ```

2.  **Navigate to the Project Directory:**
    ```bash
    cd oaqjp-final-project-emb-ai
    ```

3.  **Create a Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    ```
    * **Activate the virtual environment:**
        * **Windows:** `.\venv\Scripts\activate`
        * **macOS/Linux:** `source venv/bin/activate`

4.  **Install Dependencies:**
    Make sure you have all the necessary libraries installed.
    ```bash
    pip install -r requirements.txt
    ```

5.  **Run the Streamlit Application:**
    ```bash
    streamlit run app.py
    ```

6.  **Access the Application:**
    Your default web browser should automatically open to the Streamlit application (usually at `http://localhost:8501`). If not, copy the URL provided in your terminal.

## Live Deployment
Check the live app here - https://25866n7q-5000.inc1.devtunnels.ms/

## Contributors
**https://github.com/sjain2580**

## Connect with Me
Feel free to reach out if you have any questions or just want to connect!
**[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sjain04/)**
**[![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sjain2580)**
**[![Email](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:sjain040395@gmail.com)**

---
