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
   - A song will be classified as "successful" if it has reached one of these tiers of success (These could be changed more suitably during implementing):
     - **Tier 1:** Top 10 peak position, remained on the chart for at least **10 weeks**.  
     - **Tier 2:** Top 50 peak position, remained on the chart for at least **5 weeks**.  
     - **Tier 3:** Top 100 peak position, remained on the chart for at least **3 weeks**. 
   - Songs that have charted but failed to enter the top 50 will serve as a control group for comparative analysis. Additionally, we will consider to use a **continuous success measure** (e.g., total weeks on the chart or normalized rank percentile) for more nuanced classification.  

2. **Integration with Spotify’s Audio Features**  
   - Match Billboard chart data with Spotify’s track information using a combination of **song title and artist name**.  
   - Extract key audio features including:  
     - **Tempo (BPM):** Measures the speed of a song.  
     - **Energy:** Reflects intensity and loudness.  
     - **Danceability:** Quantifies how suitable a song is for dancing.  
     - **Valence:** Indicates the emotional positivity of a track.  
     - **Loudness, Speechiness, and Instrumentalness** as secondary features.  

3. **Statistical Analysis & Data Visualization**
   - Segment songs into major genres (e.g., pop, hip-hop, rock, EDM) and examine whether audio features differ significantly in their contribution to success.  
   - Perform **time-series analysis** to observe whether key features such as tempo, valence, or danceability fluctuate over different periods.  
   - Identify whether certain features are more critical for **pop hits** compared to **rap hits** (e.g., do rap hits rely more on speechiness and lyrical content?).
  
   - Examine whether the relationship between musical attributes and success has **remained stable or shifted over time** for each genre.  
   - Investigate whether certain trends, such as the rise of electronic production, have influenced hit song characteristics across multiple genres.  
   
   - Conduct **descriptive statistics** (mean, median, standard deviation) to compare feature distributions between successful and less successful songs.  
   - Generate **correlation matrices** to explore relationships between audio features and chart success.  
   - Use **histograms and boxplots** to visualize key feature distributions.
     
   - Employ **machine learning classification models (e.g., logistic regression, decision trees)** to assess the predictive power of audio features on chart success.  

5. **Example Case Study: The Evolution of Taylor Swift’s Chart-Topping Songs**
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
- **`feature_z_score`** – Standardized version of each audio feature to compare across different scales.
- **`hit_tier`** – Multi-tier success level (1, 2, or 3).  
- **`feature_trend`** – Time-based trend analysis of each feature.  
- **`streaming_impact`** – Flagging songs released after streaming milestones.  
- **`social_media_boost`** – Tagging viral songs using external data (e.g., TikTok).

#### **External Data to be Merged**  
- Spotify’s audio feature dataset (via song title and artist name matching).

---

### **Question 2: How have musical trends evolved over time in relation to major industry shifts?**  

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
   - Compute yearly averages for key audio features (e.g., tempo, energy, loudness, valence).
   - Perform **segmented regression analysis** to detect abrupt shifts in musical styles.
   - Overlay key historical events onto trend visualizations, such as:  
       - **2008–2010:** The decline of physical album sales and rise of digital downloads.  
       - **2015–Present:** The dominance of streaming platforms (Spotify, Apple Music).  
       - **2020–2022:** The influence of short-form video platforms (TikTok) on song virality.  

3. **Dynamic Genre Comparison Using Unsupervised Learning**
   Traditional genre labels may be limiting, as they fail to capture how musical styles evolve. Instead of relying on predefined genre tags, this analysis will:  
      - **Apply Clustering Algorithms (e.g., K-Means, DBSCAN, Hierarchical Clustering)** on **audio features** to identify distinct musical styles.  
      - Track **how clusters evolve** over time, highlighting the emergence of new subgenres.  
      - Compare these data-driven genre clusters with traditional genre labels from Billboard or Spotify to identify discrepancies.
        ##### **Example: Evolution of Hip-Hop & Pop Hybrids**
        - In the 2000s, hip-hop and pop were more distinct.
        - In the 2010s, a new cluster may emerge, representing **pop-rap fusion** (e.g., Drake, Post Malone).
        - By analyzing feature distributions over time, we can see **when and how genres start blending**.  

4. **Linking Genre Evolution to Industry Shifts**
   - Identify whether **certain clusters become more dominant** following industry changes (e.g., Do high-energy clusters gain popularity post-2015 as streaming grows?).
   - Investigate **whether newer music styles** emerge in response to changing consumption patterns (e.g., the rise of shorter, hook-driven tracks due to TikTok).
   - Study how **cross-genre collaborations** (e.g., Latin pop + hip-hop) impact success metrics over time.  

5. **Implications of Dynamic Genre Evolution**
   - Instead of treating genres as fixed, this approach helps **artists and producers understand how styles shift** and where music is headed.
   - Helps **music labels identify emerging trends** for talent scouting and marketing strategies.
   - Provides a **more accurate framework** for studying music trends beyond traditional genre definitions.   

6. **Case Study: The Shift from Upbeat Pop to Darker, Moodier Music**  
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

### **Question 3: Why do different genres achieve success in distinct ways, and what insights can this provide for artists?**  

#### **Objective**  
This question examines whether different musical genres rely on unique audio features for commercial success. Understanding genre-specific characteristics can help artists and producers tailor their sound to maximize chart performance.  

#### **Methodology**  

#### **Methodology**  
1. **Statistical Comparison of Features Across Genres**  
   - Perform **ANOVA tests** to determine whether key features (e.g., danceability, speechiness, energy) vary significantly across genres.  
   - Use **radar charts** to visually compare feature distributions.  

2. **Understanding Genre-Specific Success Factors**  
   - Analyze **why** certain genres emphasize specific features:  
     - **Hip-hop/Rap**: Higher speechiness scores due to lyrical focus—how does this impact hit probability?  
     - **EDM/Pop**: Higher danceability and energy—are faster, more rhythmic songs more likely to become hits?  
     - **Acoustic Genres (Folk, Indie)**: Higher acousticness—do slower, softer songs follow a different success trajectory?  

3. **Industry & Artist Implications**  
   - Discuss **how artists can leverage these insights** to optimize their songwriting and production choices.  
   - Explore whether collaborations between genres (e.g., pop-rap crossovers) benefit from blending different success factors.  
   - Investigate the role of **non-musical factors** (e.g., social media marketing, TikTok virality) in genre-specific success strategies.

4. **Case Study: Pop vs. Hip-Hop**  
   - Compare key features (e.g., tempo, energy, and speechiness) between **pop hits** and **hip-hop hits**.  
   - Determine whether hip-hop’s lyrical focus (high speechiness) influences its success differently than pop music’s reliance on danceability.
    
5. **Additional Considerations**  
- **Song Length & Release Timing**:  
  - Analyze whether **shorter songs** have become more dominant due to streaming revenue models.  
  - Examine **seasonal trends**—are summer releases more likely to be dance tracks?  
- **Social Media & Digital Influence**:  
  - Consider the impact of platforms like **TikTok and Instagram Reels** on song popularity.  
  - Investigate how artist collaborations and viral challenges influence a song’s trajectory.  
  
#### **Variables Involved**  
- **Billboard Chart Data:**  
  - `song_title`, `artist`, `peak_position`, `weeks_on_chart`  
- **Spotify Audio Features:** (same as Research Question 1)  
- **Genre Information:**  
  - `primary_genre` (categorical)  

#### **New Variables to be Created**  
- `avg_feature_by_genre` – Average feature values within each genre.
- `danceability_viral_index` – Danceability correlation with viral trends.  

#### **External Data to be Merged**  
- Genre classification from external sources if not present in the dataset (if they are available). 

## **5. Expected Insights**  
- Identification of key musical attributes that consistently define chart-topping hits.  
- Evidence of shifts in mainstream music trends, including changes in tempo, mood, and genre popularity.  
- Insights into how major artists adapt their sound to stay relevant over time.

- **Quantify genre-specific success mechanisms**—determine whether some genres rely more on **TikTok virality vs. traditional radio play vs. streaming traction**.  
- **Identify shifting trends**—assess whether modern hits are increasingly defined by **short-form content influence (TikTok, Shazam)**.  
- **Give practical insights for artists**—reveal **which genre features** musicians should focus on (e.g., rap → speechiness; EDM → danceability).  

## **6. Conclusion**  

This project aims to provide a comprehensive analysis of the factors that contribute to the success of top-charting songs and how music trends have evolved over the past decade. By integrating data from the Billboard Hot 100 and Spotify, we will uncover key audio features that define commercially successful tracks and analyze temporal shifts in musical attributes.  

Our findings will offer valuable insights into the music industry, benefiting artists, producers, and researchers seeking to understand the dynamics of popular music. Additionally, this study will serve as a foundation for future work in music recommendation systems, hit song prediction models, and cultural trend analysis. By leveraging data-driven methodologies, we hope to contribute to a deeper understanding of how music resonates with listeners and adapts to changing audience preferences over time.  

Ultimately, this research will bridge the gap between music analytics and industry applications, providing meaningful interpretations of why certain songs achieve widespread popularity and how the sonic landscape continues to evolve. 
