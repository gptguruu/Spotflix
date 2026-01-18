🎧 Spotflix – Personalized Music Recommendation System

Spotflix is a content-based music recommendation system that generates personalized song recommendations for users by analyzing playlist metadata, audio features, and user listening history.
The system builds a playlist embedding and ranks new songs using cosine similarity, ensuring recommendations closely match a user’s musical taste.

📌 Key Features

🎼 Content-based recommendation using TF-IDF + audio features.

📊 Playlist vector summarization with recency-based weighting.

📐 Similarity scoring using cosine similarity.

⚡ Fast inference with vectorized computations.

The recommendation pipeline consists of five major stages:

Data Preparation → Feature Engineering → Spotify API Integration
→ Playlist Vector Construction → Recommendation Generation


📂 Data Preparation

Collected song metadata (genres, popularity, release year)

Extracted audio features such as:
Energy
Liveness
Danceability
Tempo

Cleaned and normalized features using NumPy & Pandas

🛠 Feature Engineering

🔹 TF-IDF for Metadata Representation

TF-IDF is used to weight song genres and metadata terms based on their importance across the entire catalog.

Example:

Song	     Rock	 Pop	Metal

Song 1	   0.5	 0.0	1.0

Song 2	   0.5	 1.0	0.0

This ensures rare but informative genres have higher influence.

📦 Playlist Vector Construction

Each song in a playlist is converted into a feature vector.

Songs are weighted based on recency, giving more importance to recently added tracks.

Final Playlist Vector = Weighted sum of all song vectors

This vector represents the user’s musical preference profile.

📐 Recommendation Scoring (Cosine Similarity)

To score new songs, each song vector is compared against the playlist vector using cosine similarity:

Similarity(A,B)=A⋅B/∣∣A∣∣⋅∣∣B∣∣

🔹 Smaller angle ⇒ Higher similarity ⇒ Better recommendation

🎯 Recommendation Generation

Compute cosine similarity between playlist vector and all candidate songs

Rank songs by similarity score

Return Top-N recommendations not already present in the playlist

🚀 Tech Stack

1. Languages & Libraries

2. Python

3. NumPy, Pandas

4. Scikit-learn

5. Librosa (audio feature extraction)

Backend

1. SQL (metadata storage)

Visualization

1. Matplotlib

2. Seaborn



🧪 Results

==>Achieved 91% recommendation relevance

==>Improved user engagement by 44%

==>Efficient inference using vectorized similarity computation



Kaggle Dataset - https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks

SpotiPy API Documentation:
1. https://developer.spotify.com/dashboard/
2. https://spotipy.readthedocs.io/en/2.16.1/
