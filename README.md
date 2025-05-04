# 🎥 Movie Recommender System 🎬

The **Movie Recommender System** is an interactive web-based application designed to provide personalized movie recommendations. It utilizes machine learning models and movie metadata to suggest similar movies based on a user's selection. The system also fetches and displays movie posters to create an engaging experience for users.

---

## 🌟 Features

- **Personalized Recommendations**: Based on movie similarity, users receive tailored recommendations for movies they might enjoy.
- **Poster Display**: Alongside recommendations, the application displays movie posters for visual context.
- **Interactive & User-Friendly Interface**: Powered by Streamlit, the app provides a seamless and interactive experience.
- **Efficient Search**: Fetches movie details and posters in real-time using TMDb's API.
- **Pre-trained Model**: Uses a pre-computed similarity matrix for instant responses.

---

## 🛠️ Technologies Used

- **Python**: Backend logic and data processing.
- **Streamlit**: Framework for building interactive web applications.
- **Pandas**: Library for data manipulation and analysis.
- **Pickle**: For serializing and deserializing Python objects (e.g., similarity matrix, movie list).
- **TMDb API**: Fetches movie metadata and posters in real-time.

---

## 🚀 Getting Started

### Prerequisites

To run this project locally, ensure you have the following:

1. **Python 3.x**: Installed on your machine.
2. **TMDb API Key**: Obtain an API key from [The Movie Database (TMDb)](https://www.themoviedb.org/documentation/api).
3. **Required Python Libraries**: Installed via `requirements.txt`.

### Installation & Setup

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/divyanshi116/movie_recommender_system.git
   ```
2. Navigate to the project directory:
   ```bash
   cd movie_recommender_system
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Add your TMDb API key to the `fetch_poster()` function in `app.py`:
   ```python
   url = "https://api.themoviedb.org/3/movie/{}?api_key=<your_api_key>&language=en-US".format(movie_id)
   ```

---

## 🖥️ Usage

1. Run the Streamlit app:
   ```bash
   streamlit run app.py
   ```
2. Open the provided local URL in your browser.
3. Use the dropdown menu to select a movie.
4. Click the **"Recommend"** button to display:
   - Recommended movies.
   - Posters of the recommended movies alongside their titles.

---

## 📂 Project Structure

- **`app.py`**: Main file containing the Streamlit code for the application.
- **`movies_list.pkl`**: Serialized file containing movie titles and corresponding metadata.
- **`similarity.pkl`**: Serialized file with a precomputed similarity matrix for movie recommendations.
- **`dataset.csv`**: Dataset containing movie details such as title, genres, and overview.
- **`frontend/`**: Directory for UI-related files and assets.

---

## 🎯 Example

### Input:
- Selected Movie: "The Shawshank Redemption"

### Output:
- Recommendations:
  - "The Godfather"
  - "Schindler's List"
  - "Pulp Fiction"
- Posters: Displayed alongside each recommended movie.

---

## 📝 Algorithm Details

1. **Data Preparation**:
   - The dataset is preprocessed to extract features like genres, keywords, cast, and crew.
   - These features are combined to create a single text representation for each movie.

2. **Vectorization**:
   - The combined text is vectorized using the `CountVectorizer` from Scikit-learn.
   - This creates a sparse matrix representation of the text data.

3. **Similarity Computation**:
   - Cosine similarity is computed between the vectors of all movies.
   - The result is a similarity matrix used to find movies similar to a user's selection.

4. **Recommendation**:
   - When a movie is selected, its similarity scores are retrieved from the precomputed matrix.
   - The top N movies (default: 5) with the highest similarity scores are recommended.

5. **Poster Retrieval**:
   - TMDb's API is used to fetch and display posters for the recommended movies.

---

## 📋 Dependencies

The following Python libraries are required for this project:

- **Streamlit**: For building the interactive web application.
- **Pandas**: For handling and analyzing the movie dataset.
- **Requests**: For making HTTP requests to the TMDb API.
- **Pickle**: For saving and loading precomputed data structures.
- **Scikit-learn**: For vectorization and similarity computation.

Install all dependencies via:
```bash
pip install -r requirements.txt
```

---

## 🤝 Contributing

Contributions are welcome! 🎉 If you’d like to contribute:

1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature/YourFeature
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add YourFeature"
   ```
4. Push to the branch:
   ```bash
   git push origin feature/YourFeature
   ```
5. Open a pull request.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 📧 Contact

For questions or feedback, feel free to reach out to [divyanshi116](https://github.com/divyanshi116). 💬
