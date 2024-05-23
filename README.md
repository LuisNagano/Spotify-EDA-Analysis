# Spotify Exploratory Data Analysis Project

## Project Structure
1. [Introduction](#introduction)
2. [Necessary Libraries](#necessary-libraries)
3. [Dataset](#dataset)
4. [Data Preprocessing](#data-preprocessing)
5. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
    1. [Visualizations and Descriptive Statistics](#visualizations-and-descriptive-statistics)
    2. [Analysis of Variable Distributions](#analysis-of-variable-distributions)
    3. [Identification of Patterns and Correlations](#identification-of-patterns-and-correlations)
6. [Insights](#insights)
    1. [Discussion of Key Insights](#discussion-of-key-insights)
    2. [Implications and Future Suggestions](#implications-and-future-suggestions)

## Introduction

### Project Context and Objectives

The objective of this project is to perform an Exploratory Data Analysis (EDA) on a dataset of Spotify tracks. The analysis aims to identify patterns, trends, and insights relevant to the characteristics of the music available on the platform. The study covers aspects such as popularity, duration, musical genres, and various acoustic features of the tracks.

## Necessary Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy.stats import pearsonr
```

The libraries used in this project include:
- **pandas**: for data manipulation and analysis.
- **numpy**: for numerical operations.
- **matplotlib**: for graphical visualizations.
- **seaborn**: for statistical visualizations.
- **scipy**: for statistical calculations.

## Dataset

### Dataset Description

The dataset used in this project contains information about various tracks available on Spotify. The main variables include:
- `name`: Name of the track.
- `artists`: Artists involved in the track.
- `release_date`: Release date of the track.
- `popularity`: Popularity score of the track (0-100).
- `duration_ms`: Duration of the track in milliseconds.
- `danceability`, `energy`, `loudness`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`: Various acoustic features of the track.

The data source is the Spotify API.

## Data Preprocessing

### Data Cleaning and Preparation

In the data preprocessing phase, the following steps were performed:
1. **Handling Missing Values**: Removal or imputation of missing values in relevant columns.
2. **Date Formatting**: Conversion of the `release_date` column to datetime format.
3. **Creating New Variables**: Extraction of the release year for temporal analyses.

```python
# Preprocessing example
df_tracks['release_date'] = pd.to_datetime(df_tracks['release_date'], errors='coerce')
df_tracks['year'] = df_tracks['release_date'].dt.year
df_tracks.dropna(subset=['release_date'], inplace=True)
```

## Exploratory Data Analysis (EDA)

### Visualizations and Descriptive Statistics

The exploratory data analysis involves creating various visualizations and calculating descriptive statistics to explore the main characteristics of the Spotify tracks.

### Analysis of Variable Distributions

Visualizations were generated to understand the distribution of variables of interest, such as popularity, duration, and acoustic features.

### Identification of Patterns and Correlations

Correlation heatmaps and scatter plots were used to identify patterns and correlations between different characteristics of the music.

### Least Popular Songs
We analyzed the 10 least popular songs on Spotify. Popularity is measured on a scale from 0 to 100, where 0 is the least popular. Songs with the lowest popularity have a score of 0, indicating that they were rarely or never played on the platform.

### Most Popular Songs
![Most Popular Songs](path/to/most_popular_songs.png)
The analysis of the 10 most popular songs on Spotify reveals that all have a popularity score above 90. These songs represent the biggest hits on the platform. A horizontal bar chart was generated to visualize these data, where we can clearly see that artists like Justin Bieber (featuring Daniel Caesar and Giveon), Olivia Rodrigo, and The Weeknd dominate the top charts.

### Distribution of Songs by Year
![Distribution of Songs by Year](path/to/distribution_by_year.png)
A histogram shows the distribution of the number of songs released per year. There is a significant increase in the number of releases over the years, especially after 2010. This increase may be associated with the growth of digital music platforms.

### Duration of Songs Over the Years
![Duration of Songs Over the Years](path/to/duration_over_years.png)
Two charts were generated to analyze the duration of songs over the years: a bar chart and a line chart. There is a trend of decreasing average song duration over time. This behavior may reflect changes in listener preferences and production strategies.

### Duration of Songs in Different Genres
![Duration of Songs in Different Genres](path/to/duration_genres.png)
A bar chart shows the average duration of songs in different musical genres. Genres such as World, Soundtrack, and Soul tend to have longer songs, while songs in genres such as A Capella and Children's Music tend to be shorter.

### Most Popular Genres
![Most Popular Genres](path/to/popular_genres.png)
A bar chart of the top 5 musical genres by popularity shows that Dance, Pop, Rap, Hip-Hop, and Reggaeton are the most popular genres on Spotify.

### Correlation Analysis
![Correlation Heatmap](path/to/correlation_heatmap.png)
A correlation heatmap highlights the significant relationships between various features of the tracks. For example, there is a strong positive correlation between energy and loudness, and a moderate positive correlation between danceability and valence.

![Filtered Correlation Heatmap](path/to/filtered_correlation_heatmap.png)
The filtered heatmap shows only the most significant correlations (|r| > 0.5), providing a clearer view of key relationships.

## Insights

### Discussion of Key Insights

1. **Popularity**:
   - The most popular tracks have a popularity score above 90, with artists like Justin Bieber and Olivia Rodrigo dominating the top charts.

2. **Duration**:
   - The average duration of songs has decreased over the years, reflecting changes in listener preferences and production strategies.

3. **Musical Genres**:
   - Genres such as Dance, Pop, Rap, Hip-Hop, and Reggaeton are the most popular on the platform.
   - Songs in genres such as World and Soundtrack tend to have longer durations.

4. **Correlation between Features**:
   - There is a strong positive correlation between energy and loudness, indicating that more energetic songs tend to be louder.
   - There is a moderate positive correlation between danceability and valence, suggesting that happier songs tend to be more danceable.

### Implications and Future Suggestions

The insights obtained can have various implications for the music industry:
- **Music Production**: Understanding preferences for duration and acoustic features can help producers create tracks more aligned with what listeners seek.
- **Marketing and Playlists**: Identifying popular genres and features can aid in playlist curation and marketing strategies.
- **Future Analyses**: Further analyses in specific sub-genres and incorporating demographic data are suggested to better understand the impact of tracks on different audiences.
