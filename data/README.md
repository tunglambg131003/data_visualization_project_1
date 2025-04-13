📄 Dataset Metadata

1. Dataset Overview  
**Title:** Billboard Hot 100 Dataset 
**Description:** The dataset was created using a custom Scrapy web crawler to collect weekly *Billboard Hot 100* chart data from **January 4, 1960**, to **April 2, 2022**, resulting in **324,787** records. To focus on influential songs, the author selected the top 50 tracks from each year based on their chart longevity, reducing the dataset to **3,150** entries. These records were then enriched using the **Spotify for Developers API**, adding **21** musical and metadata attributes. 

2. Provenance  
**Source:** [Billboard Hot 100 Dataset ](https://github.com/Ikea-179/Top-Hit-Songs-Data-Analysis-and-Visualization/tree/main/Datasets)    
**Original Publisher:** [Ikea-179](https://github.com/Ikea-179)
**Data Collection:** Information compiled from Billboard statistics and Spotify metadata. 

3. Dataset Structure  
The dataset contains the following key components:

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

4. Usage  
This dataset is useful for:
- Analyzing trends in music appreciation over time.
- Studying genre evolution and artist popularity.
- Data visualization and storytelling exercises.
- Educational purposes in data science, particularly in data cleaning and wrangling.

5. Licensing  
**License Type:** Not explicitly stated in the source repository.  
**Notes:** Since this dataset scrapes data from Billboard and uses Spotify’s API, users should ensure their usage aligns with [Billboard's Terms of Use](https://www.billboard.com/terms-of-use/) and the [Spotify Developer Terms of Service](https://developer.spotify.com/terms/).

6. Acknowledgments  
Thanks to **[Ikea-179](https://github.com/Ikea-179)** for developing the custom Scrapy crawler and compiling the data, and to **Spotify for Developers** for providing access to track-level audio features and metadata.

7. Citation  
If you use this dataset in your work, please cite it as follows:  
> Ikea-179. *Billboard Hot 100 Dataset*. GitHub repository. Available at: https://github.com/Ikea-179/Top-Hit-Songs-Data-Analysis-and-Visualization/tree/main/Datasets