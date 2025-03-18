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
The Billboard Hot 100 dataset contains weekly rankings of the top 100 songs in the U.S. over multiple years. It includes:  

- **date**: The date when the song appeared on the Billboard chart.  
- **title**: The title of the song.  
- **artist**: The name of the performing artist.  
- **year**: The year of the song's chart performance.

- **rank**: The song's ranking on the chart for the given date.  
- **last_week**: The song's ranking in the previous week.  
- **peak**: The highest rank the song achieved on the Billboard chart.  
- **weeks**: The total number of weeks the song remained on the chart.

- **danceability**: A measure of how suitable a track is for dancing (0 to 1).  
- **energy**: A measure of intensity and activity (0 to 1).  
- **key**: The musical key in which the song is played (0-11, corresponding to C to B).  
- **loudness**: The overall volume of the track in decibels (dB).  
- **mode**: The modality of the song (0 = Minor, 1 = Major).  
- **speechiness**: The presence of spoken words in a track (0 to 1).  
- **acousticness**: The likelihood of the track being acoustic (0 to 1).  
- **instrumentalness**: The likelihood of the track being purely instrumental (0 to 1).  
- **liveness**: Detects the presence of a live audience in the recording (0 to 1).  
- **valence**: The musical positiveness of the track (0 to 1).  
- **tempo**: The estimated beats per minute (BPM) of the track.  
- **duration_ms**: The length of the song in milliseconds.  

