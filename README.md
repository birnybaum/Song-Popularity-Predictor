# Song Popularity Prediction Model

## Overview

Humans have a deep connection with music, which can improve mood, decrease pain and anxiety, and facilitate emotional expression. Music's benefits on physical and mental health are well-documented. The goal of this project is to predict song popularity based on various acoustic features using machine learning algorithms.

## Motivation

Personally, music is an emotional escape, especially during challenging times like the pandemic. Listening to music for several hours a day has highlighted the importance of song quality on mood. Predicting song popularity can help in creating better music that people enjoy. This project aims to achieve that goal by analyzing song features and predicting their popularity.

## Data Set

The song data set was sourced from Kaggle and includes over 14,000 songs with the following 13 features:

- Song Duration
- Acousticness 
- Danceability
- Energy 
- Instrumentalness
- Key 
- Liveness
- Time Signature
- Audio Valence
- Loudness
- Audio Mode
- Speechiness
- Tempo 

## Data Cleaning and Preparation

### Initial Analysis

- **Visualization**: Countplot of song popularity (0-100) shows most values between 40-60, with few very popular (80-100) and many very unpopular (0) songs.
- **Duplicates and NA Values**: Removed duplicates and NA values.
- **Correlation Analysis**: Identified multicollinearity among features. Energy, Loudness, and Acousticness showed high correlation. Energy was removed to reduce multicollinearity.

### Feature Analysis

- **Instrumentalness**: Despite initial concerns, instrumentalness was kept as it was highly negatively correlated with song popularity.

### Data Splitting

- Split data into 70/30 train/test sets.
- Scaled features using MinMaxScaler.

## Machine Learning Models

Seven models were tested:

1. Logistic Classifier
2. Decision Tree Classifier
3. Random Forest Classifier
4. K Nearest Neighbor (K=5) Classifier
5. K Nearest Neighbor (K=32) Classifier
6. Support Vector Machine Classifier
7. Keras Classifier (Deep Learning)

### Model Performance

Initial results were poor due to imbalanced data. Most songs were average, making predictions around 50. This was addressed by re-categorizing the data into binary classes:

- **Popular**: >85% popularity
- **Not Popular**: <85% popularity

### Final Results

After addressing data imbalance, Random Forest Classifier showed the best performance with an area under the ROC curve of 0.785. The model effectively distinguished between popular and not popular songs and showed significance in predicting average scores.

## Applications

- **Album Creation**: Advising producers on song selection for albums.
- **Music Production**: Helping artists fine-tune songs based on popular features.

## Challenges and Solutions

### Challenges

- The model is incorrect 21.5% of the time, which can lead to significant errors.
- Binary classification may not fully capture the range of song popularity.

### Solutions

- Use the model as a supplementary tool rather than the sole decision-maker.
- Distinguish between average and popular songs for better predictions.
- Implement multi-class classification using one-hot encoding for continuous popularity values.

## Repository Contents

### `Song Popularity Prediction.ipynb`

This Jupyter Notebook contains the entire workflow for the song popularity prediction project, including data cleaning, feature analysis, model training, and evaluation.

### `song_data.csv`

This CSV file contains the raw data used for the project, including the 13 features and the popularity scores for over 14,000 songs.

### `plots/`

This directory contains visualizations used in the project, such as countplots, heatmaps, and scatterplots, illustrating data distribution and correlations.

### `Machine Learning Final Project.pdf`

The final project report from conception to completion, including all graphs, charts, and conclusions.

### `The Future of Music.pptx`

The PowerPoint presentation containing key graphs, charts, and conclusions from the project.

## Getting Started

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/birnybaum/Song-Popularity-Prediction.git
   cd Song-Popularity-Prediction

## Run the Jupyter Notebook

To run the Jupyter Notebook for this project, follow these steps:

1. Open the `Song Popularity Prediction.ipynb` file in Jupyter Notebook or JupyterLab.
2. Execute the code cells in the notebook to perform data cleaning, feature analysis, model training, and evaluation.
3. Visualize the results and analyze the predictions.

## Contact

If you have any questions or need further information, please feel free to contact Andrew M. Birnbaum.

## Acknowledgements

I would like to acknowledge the following individuals and organizations for their contributions and support:
- Instructor: Professor Jacek Dmochowski

