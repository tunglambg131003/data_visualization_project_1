# **Proposal: Top Hit Songs Data Analysis & Visualization**

## **1. Introduction** 

Music is an integral part of human life, shaping our emotions and cultural identity. From birth, we have a natural inclination to perceive and follow rhythms, while the prevailing musical styles and trends continuously evolve over time. Songs that achieve top-charting success do not emerge randomly; they serve as reflections of popular culture and, at times, symbols of societal transformation.

By analyzing the key figures (artists) and characteristics (genres, audio features, etc.) that define these ever-changing musical trends, we can gain valuable insights into the evolution of music. 

Specifically, by examining top hit songs since 1960, this study aims to explore:  

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
