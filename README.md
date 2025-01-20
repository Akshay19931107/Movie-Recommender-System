# Movie-Recommender-System
# Movie Recommender System

## Overview
This project is a movie recommender system that suggests similar movies based on user preferences. It is implemented using Python and provides a web-based user interface powered by Streamlit. The recommendation is performed using Singular Value Decomposition (SVD) to reduce dimensionality and cosine similarity for identifying similar movies.

---

## Features
- **Data Preprocessing**:
  - Filters movies and users based on thresholds for the number of ratings.
  - Normalizes the rating matrix to handle missing values effectively.
- **Recommendation Engine**:
  - Uses SVD to generate a latent feature space for movies.
  - Employs cosine similarity to find the most similar movies.
- **Streamlit Interface**:
  - Allows users to select a movie and view recommendations interactively.

---

## Project Structure
```plaintext
.
├── recommender.py          # Core recommendation logic
├── app.py                  # Streamlit application
├── movies_list.pkl         # Serialized movie metadata
├── similarity.pkl          # Serialized similarity indices
├── movies.dat              # Raw movie metadata
├── ratings.dat             # Raw user-movie ratings data
└── requirements.txt        # Python dependencies
```

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone <repository-url>
cd <repository-folder>
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Prepare the Dataset
Ensure the `movies.dat` and `ratings.dat` files are in the root directory. These files contain:
- `movies.dat`: Metadata about movies (IDs, titles, genres).
- `ratings.dat`: User ratings for movies.

### 4. Run Preprocessing Script
```bash
python recommender.py
```
This script will:
- Process the datasets.
- Generate recommendation vectors.
- Save processed data as `movies_list.pkl` and `similarity.pkl`.

### 5. Launch the Streamlit Application
```bash
streamlit run app.py
```

---

## Usage
1. Open the Streamlit interface in your browser.
2. Select a movie from the dropdown menu.
3. Click the "Show recommend" button to view similar movie recommendations.

---

## Methodology
### Data Preprocessing
- Dropped movies and users with insufficient ratings to ensure meaningful recommendations.
- Constructed a user-movie rating matrix for analysis.
- Normalized the rating matrix to handle missing entries.

### SVD-Based Decomposition
- Applied Singular Value Decomposition (SVD) to extract latent features.
- Used the top 50 latent features to reduce dimensionality.

### Cosine Similarity
- Calculated cosine similarity between movie vectors in the latent feature space.
- Identified the top 5 similar movies for each movie.

### Streamlit Integration
- Loaded preprocessed data from `movies_list.pkl` and `similarity.pkl`.
- Provided a user-friendly interface for selecting movies and viewing recommendations.

---

## Example
### Input
Selected Movie: `Toy Story (1995)`

### Output
Top 5 Recommended Movies:
1. **A Bug's Life (1998)**
2. **Toy Story 2 (1999)**
3. **Monsters, Inc. (2001)**
4. **Finding Nemo (2003)**
5. **The Incredibles (2004)**

---

## Future Enhancements
- Add functionality for personalized recommendations based on user history.
- Integrate additional similarity metrics like Pearson correlation.
- Enhance the user interface with movie posters and descriptions.
- Optimize the algorithm for large-scale datasets.

---

## License
This project is licensed under the MIT License.

---

## Authors
**Akshay Baviskar**

