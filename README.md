# WBS-unsupervised-ML-Clustering

# Spotify Song Clustering for Playlist Recommendation

**Unsupervised Machine Learning | Python | PCA | K-Means | Spotify Audio Features**

## About This Project

This project applies unsupervised machine learning to group songs according to their audio characteristics. The main objective is to explore whether numerical music features from Spotify can be used to create meaningful song groups that may later be used as playlist suggestions.

Instead of using predefined labels such as genre or mood, the model learns patterns directly from the data. Songs with similar audio profiles are placed into the same cluster. Each cluster can then be interpreted as a possible playlist category.

The project was developed as part of a machine learning exercise focused on clustering and dimensionality reduction.

## Main Idea

Music playlists are often created manually based on mood, genre, tempo, or personal taste. However, this process can be time-consuming when the number of songs becomes large.

In this project, I tested whether machine learning can support this process by automatically identifying groups of similar songs. The goal is not to replace human judgement, but to use clustering as a first step toward scalable playlist recommendation.

## Dataset

The analysis is based on a Spotify audio-feature dataset containing **5,171 songs**.

Each song is represented by several numerical features, including:

- danceability
- energy
- tempo
- loudness
- valence
- acousticness
- instrumentalness
- speechiness
- liveness

These variables describe different measurable aspects of a song and provide the input for the clustering model.

## Workflow

The project follows a typical unsupervised machine learning workflow:

### 1. Data Exploration

The dataset was first inspected to understand the available columns, data types, value ranges, and possible feature distributions.

### 2. Feature Selection

Only relevant numerical audio features were selected for clustering. Non-numerical information such as song names or artist names was not used directly in the model.

### 3. Data Scaling

Since the selected features have different scales, the data was normalised before modelling. This step is important because distance-based algorithms such as K-Means are sensitive to feature ranges.

### 4. Dimensionality Reduction with PCA

Principal Component Analysis was used to reduce the complexity of the feature space. PCA helped to summarise the most important variation in the data and made it easier to inspect the general structure of the songs.

### 5. Clustering with K-Means

K-Means clustering was applied to divide the songs into groups. Several cluster numbers were tested in order to compare different playlist structures.

The final solution grouped the songs into **91 clusters**.

### 6. Model Evaluation

The clustering results were evaluated using both quantitative and qualitative approaches:

- inertia
- silhouette score
- comparison of different cluster numbers
- inspection of songs within selected clusters
- interpretation of whether clusters could work as playlists

## Results and Interpretation

The model was able to separate the songs into different groups based on their audio features. Some clusters showed clear patterns, for example songs with similar energy, danceability, or acousticness.

This suggests that Spotify audio features can capture part of the musical similarity between songs. However, the results also show that audio features alone are not enough to fully describe how people experience music.

Some playlists may appear technically similar according to the model, but still feel different to a human listener because of genre, lyrics, artist style, cultural context, or personal preference.

## Key Findings

- Unsupervised learning can be useful for organising large music datasets.
- K-Means provides a simple and understandable clustering approach.
- PCA helps to analyse the structure of high-dimensional audio data.
- Spotify audio features can support playlist generation, but they do not fully capture human taste.
- Human evaluation is still important when judging playlist quality.

## Limitations

There are several limitations in this approach:

- The number of clusters must be chosen manually.
- K-Means assumes relatively compact cluster shapes.
- The model does not understand lyrics, genre, artist identity, or listener behaviour.
- Cluster sizes are difficult to control.
- Similar numerical features do not always mean that songs sound good together in a playlist.

## Possible Improvements

Future work could improve the project by:

- comparing K-Means with other clustering algorithms
- using hierarchical clustering or DBSCAN
- adding genre and artist metadata
- including user listening history
- analysing lyrics with natural language processing
- building a small interface for playlist exploration
- combining algorithmic clustering with human review

## Technologies Used

- Python
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- Jupyter Notebook

## Conclusion

This project shows how unsupervised machine learning can be applied to music data in order to create automatic song groupings. The results indicate that clustering can support playlist generation and help organise large collections of songs.

At the same time, the project makes clear that music recommendation is not only a technical problem. Human taste, mood, context, and cultural meaning are important factors that cannot be fully captured by numerical audio features alone.

Therefore, the best use of this approach is as a supportive tool for playlist creation rather than a complete replacement for human curation.
