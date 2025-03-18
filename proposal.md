# **Proposal: Top Hit Songs Data Analysis & Visualization**

## **1. Introduction** 

Music is an integral part of human life, shaping our emotions and cultural identity. From birth, we have a natural inclination to perceive and follow rhythms, while the prevailing musical styles and trends continuously evolve over time. Songs that achieve top-charting success do not emerge randomly; they serve as reflections of popular culture and, at times, symbols of societal transformation.

By analyzing the key figures (artists) and characteristics (genres, audio features, etc.) that define these ever-changing musical trends, we can gain valuable insights into the evolution of music. 

Specifically, by examining top hit songs, this study aims to explore:  

 - The shifts in musical genres over time.
 - The progression of audio features in hit songs.  
 - The most dominant artists on the charts.
 - The peak periods of top artists’ careers.
 - The musical preferences of leading artists, particularly regarding key selection.  

## **2. Dataset Description**  

We will use two primary datasets for this analysis:  

### **Billboard Hot 100 Dataset**  

| **Column**       | **Description** |
|-----------------|----------------|
| `date`         | The date when the song appeared on the Billboard chart. |
| `title`        | The title of the song. |
| `artist`       | The name of the performing artist. |
| `year`         | The year of the song's chart performance. |
| `rank`         | The song's ranking on the chart for the given date. |
| `last_week`    | The song's ranking in the previous week. |
| `peak`         | The highest rank the song achieved on the Billboard chart. |
| `weeks`        | The total number of weeks the song remained on the chart. |
| `danceability` | A measure of how suitable a track is for dancing (0 to 1). |
| `energy`       | A measure of intensity and activity (0 to 1). |
| `key`          | The musical key in which the song is played (0-11, corresponding to C to B). |
| `loudness`     | The overall volume of the track in decibels (dB). |
| `mode`         | The modality of the song (0 = Minor, 1 = Major). |
| `speechiness`  | The presence of spoken words in a track (0 to 1). |
| `acousticness` | The likelihood of the track being acoustic (0 to 1). |
| `instrumentalness` | The likelihood of the track being purely instrumental (0 to 1). |
| `liveness`     | Detects the presence of a live audience in the recording (0 to 1). |
| `valence`      | The musical positiveness of the track (0 to 1). |
| `tempo`        | The estimated beats per minute (BPM) of the track. |
| `duration_ms`  | The length of the song in milliseconds. |
| `genres`       | A list of genres associated with the song. |
| `genre_encoding` | A categorical encoding of the song’s genre for classification tasks. |


### **Spotify Song Attributes Dataset**  

| **Column**       | **Description** |
|-----------------|----------------|
| `track_id`     | The unique identifier assigned to the track by Spotify. |
| `artists`      | The names of the artists who performed the track (separated by `;` if multiple artists). |
| `album_name`   | The name of the album where the track is included. |
| `track_name`   | The title of the track. |
| `popularity`   | A score (0-100) representing the track’s overall popularity based on streams. |
| `danceability` | A value (0.0 - 1.0) reflecting how well the track is suited for dancing. |
| `energy`       | A rating (0.0 - 1.0) measuring the song’s intensity and activity level. |
| `key`          | The musical key of the track (0 = C, 1 = C♯/D♭, ..., 11 = B), `-1` if undetectable. |
| `loudness`     | The average volume level of the track in decibels (dB). |
| `mode`         | Specifies the musical mode (`0 = Minor`, `1 = Major`). |
| `speechiness`  | A measure (0.0 - 1.0) of spoken words in the track. |
| `acousticness` | A confidence score (0.0 - 1.0) indicating whether the track is acoustic. |
| `instrumentalness` | Estimates the likelihood that the track is purely instrumental (0.0 - 1.0). |
| `liveness`     | Probability of the track being recorded with a live audience (0.0 - 1.0). |
| `valence`      | A numerical score (0.0 - 1.0) representing the track’s emotional tone. |
| `tempo`        | The estimated speed of the track in beats per minute (BPM). |
| `time_signature` | The estimated number of beats per measure (3 to 7, e.g., `3/4` to `7/4`). |
| `track_genre`  | The musical genre classification for the track. |

## **3. Motivation for Dataset Selection**  

- Billboard and Spotify are two of the most authoritative sources in music rankings.  
- The dataset includes over 50,000 samples, providing a diverse and extensive collection that meets the criteria for Project 1. It contains both numerical and categorical features, enabling a comprehensive analysis of feature distributions. Additionally, the large dataset size presents opportunities to explore data preprocessing techniques and handle real-world challenges.
- The music industry is highly dynamic, with shifts in genre preferences, production styles, and audience engagement over time. Analyzing chart-topping songs can help identify patterns in musical composition and consumer behavior, shedding light on how certain audio attributes influence a song’s success.
- Music is a reflection of cultural and technological changes over time. By examining how key musical attributes have evolved across different decades, we can explore broader sociocultural influences on music production and audience reception. This long-term perspective enhances our understanding of how technological advancements, such as digital production tools, impact song composition and arrangement.
- The insights gained from this research have implications beyond the music industry. Understanding the relationship between audio features and song success can benefit fields such as marketing, recommender systems, and artificial intelligence in music generation.

## **4. Research Questions & Analysis Plan**  

### **Question 1: What are the key audio features that define top-charting songs over the past decade?**  

#### **Objective**  
This question aims to identify the distinct musical characteristics of commercially successful songs by analyzing their audio attributes. By examining the structural and acoustic features of top-ranking tracks, we can determine whether certain properties—such as tempo, energy, and danceability—consistently contribute to a song’s chart performance.  

#### **Methodology**  

1. **Defining "Success" in Chart Performance**  
   - A song will be classified as "successful" if it has reached a peak position within the **top 10** of the Billboard Hot 100 and remained on the chart for at least **10 weeks**.  
   - Songs that have charted but failed to enter the top 50 will serve as a control group for comparative analysis.  

2. **Integration with Spotify’s Audio Features**  
   - Match Billboard chart data with Spotify’s track information using a combination of **song title and artist name**.  
   - Extract key audio features including:  
     - **Tempo (BPM):** Measures the speed of a song.  
     - **Energy:** Reflects intensity and loudness.  
     - **Danceability:** Quantifies how suitable a song is for dancing.  
     - **Valence:** Indicates the emotional positivity of a track.  
     - **Loudness, Speechiness, and Instrumentalness** as secondary features.  

3. **Statistical Analysis & Data Visualization**  
   - Conduct **descriptive statistics** (mean, median, standard deviation) to compare feature distributions between successful and less successful songs.  
   - Generate **correlation matrices** to explore relationships between audio features and chart success.  
   - Use **histograms and boxplots** to visualize key feature distributions.  
   - Employ **machine learning classification models (e.g., logistic regression, decision trees)** to assess the predictive power of audio features on chart success.  

4. **Example Case Study: The Evolution of Taylor Swift’s Chart-Topping Songs**  
   - Taylor Swift, a globally recognized artist, has consistently produced hits across multiple genres (country, pop, and alternative).  
   - By analyzing the audio features of her most successful tracks (e.g., *Shake It Off*, *Blank Space*, *Anti-Hero*), we can investigate whether her musical attributes align with broader trends in hit songs.  
   - A comparative study with her lower-charting songs will highlight whether any specific musical attributes contributed to their differing levels of success.  

#### **Variables Involved**  
- **Billboard Chart Data:**  
  - `song_title` (string)  
  - `artist` (string)  
  - `peak_position` (integer) – highest rank achieved  
  - `weeks_on_chart` (integer) – total number of weeks on the chart  

- **Spotify Audio Features:**  
  - `tempo` (BPM) – speed of the song  
  - `energy` (float) – intensity and loudness (0-1)  
  - `danceability` (float) – how suitable the song is for dancing (0-1)  
  - `valence` (float) – emotional positivity (0-1)  
  - `loudness` (dB) – overall sound level  
  - `speechiness` (float) – presence of spoken words (0-1)  
  - `instrumentalness` (float) – likelihood of being an instrumental track (0-1)

#### **New Variables to be Created**  
- `hit_song` (binary) – 1 if a song peaked in the **top 10** and remained on the chart for **at least 10 weeks**, 0 otherwise.  
- `feature_z_score` – Standardized version of each audio feature to compare across different scales.  

#### **External Data to be Merged**  
- Spotify’s audio feature dataset (via song title and artist name matching).

---

### **Question 2: How have music trends evolved over the past decade?**  

#### **Objective**  
Music trends shift over time due to changes in audience preferences, production techniques, and industry innovations. This research question explores whether certain musical features—such as tempo, energy, and mood—have changed significantly over the years, reflecting broader trends in popular music.  

#### **Methodology**  

1. **Temporal Grouping & Data Aggregation**  
   - Segment the dataset into **yearly intervals** (e.g., 2010–2020).  
   - Compute annual averages for key audio features, such as tempo, energy, danceability, and valence.  
   - Categorize songs by **genre** (pop, hip-hop, rock, R&B, electronic, etc.) to analyze genre-specific trends.  

2. **Time-Series Analysis**  
   - Use **line graphs** to visualize year-over-year changes in musical attributes.  
   - Apply **linear regression** and **moving averages** to identify long-term trends in tempo, valence, and other features.  
   - Investigate whether certain genres have increased or decreased in prominence over time by tracking their proportional representation in the dataset.  

3. **Comparative Genre Analysis: The Rise of Hip-Hop & Decline of Rock**  
   - Previous studies suggest that hip-hop has overtaken rock as the dominant genre in mainstream music.  
   - Compare the **audio features** of hip-hop tracks (e.g., *Drake's* and *Kanye West’s* songs) versus rock tracks (e.g., *Imagine Dragons* or *Coldplay*) to observe stylistic shifts.  
   - Analyze whether modern rock songs have incorporated more rhythmic and electronic elements to align with popular trends.  

4. **Case Study: The Shift from Upbeat Pop to Darker, Moodier Music**  
   - Compare the valence and tempo of early 2010s hits (e.g., *Katy Perry’s* *Teenage Dream*) to late 2010s hits (e.g., *Billie Eilish’s* *Bad Guy*).  
   - Investigate whether pop music has become **slower, darker, and more melancholic** over time, reflecting shifting listener preferences.

#### **Variables Involved**  
- **Time-based Aggregation:**  
  - `year` (integer) – extracted from release date  
- **Spotify Audio Features:** (same as Research Question 1)  
- **Genre Information:**  
  - `primary_genre` (categorical) – main genre of the song  

#### **New Variables to be Created**  
- `yearly_avg_feature` – Annual average of each audio feature to observe trends over time.  
- `dominant_genre` – The most frequent genre for each year based on song counts.  

#### **External Data to be Merged**  
- Genre classification data from an external music database (if not available in Billboard/Spotify datasets).

---

### **Question 3: Do different genres have distinct success factors?**  

#### **Objective**  
This question examines whether different musical genres rely on unique audio features for commercial success. Understanding genre-specific characteristics can help artists and producers tailor their sound to maximize chart performance.  

#### **Methodology**  

1. **Genre Categorization**  
   - Assign each song in the dataset to a primary genre (pop, rock, hip-hop, EDM, R&B, etc.).  
   - Compute average values for key audio features within each genre.  

2. **Feature Comparison Across Genres**  
   - Perform **ANOVA (Analysis of Variance)** tests to determine statistically significant differences in features across genres.  
   - Create **radar charts** to visualize how audio features differ between genres.  

3. **Case Study: Pop vs. Hip-Hop**  
   - Compare key features (e.g., tempo, energy, and speechiness) between **pop hits** and **hip-hop hits**.  
   - Determine whether hip-hop’s lyrical focus (high speechiness) influences its success differently than pop music’s reliance on danceability.
  
#### **Variables Involved**  
- **Billboard Chart Data:**  
  - `song_title`, `artist`, `peak_position`, `weeks_on_chart`  
- **Spotify Audio Features:** (same as Research Question 1)  
- **Genre Information:**  
  - `primary_genre` (categorical)  

#### **New Variables to be Created**  
- `avg_feature_by_genre` – Average feature values within each genre.  

#### **External Data to be Merged**  
- Genre classification from external sources if not present in the dataset. 

## **5. Expected Insights**  
- Identification of key musical attributes that consistently define chart-topping hits.  
- Evidence of shifts in mainstream music trends, including changes in tempo, mood, and genre popularity.  
- Insights into how major artists adapt their sound to stay relevant over time.  

## **6. Conclusion**  

This project aims to provide a comprehensive analysis of the factors that contribute to the success of top-charting songs and how music trends have evolved over the past decade. By integrating data from the Billboard Hot 100 and Spotify, we will uncover key audio features that define commercially successful tracks and analyze temporal shifts in musical attributes.  

Our findings will offer valuable insights into the music industry, benefiting artists, producers, and researchers seeking to understand the dynamics of popular music. Additionally, this study will serve as a foundation for future work in music recommendation systems, hit song prediction models, and cultural trend analysis. By leveraging data-driven methodologies, we hope to contribute to a deeper understanding of how music resonates with listeners and adapts to changing audience preferences over time.  

Ultimately, this research will bridge the gap between music analytics and industry applications, providing meaningful interpretations of why certain songs achieve widespread popularity and how the sonic landscape continues to evolve.  
