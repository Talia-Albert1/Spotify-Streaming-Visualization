# Spotify Streaming Project

## Overview
The goal of this to project is to examine my extended streaming history from Spotify, to look at which artists or individual songs I listened to the most, which years was I listening to the most music, etc. This dataset, alongside with information pulled from Spotify's web API such as valence, a measure of happiness, energy, dancibility, etc., can provide further insight on some interesting trends. Is there any patterns or correlations between the type of music I listen to and the time of day, or day of the week? Music plays an incredibly important and intimate role in my life, and a comprehensive history of my music listening is endlessly fascinating to dive into.

The analyses performed are mostly visualizations and summerizations of data, however in the future I plan to take a more predictive approach.

## Running this project
### Build the docker container
Clone this repository to your local computer, naviagte into the directory and build the docker container with the following command (ensuring you have docker installed first)
```
sudo docker build . -t spotify_streaming
```

Then run the docker container with the following command, the password can be changed to whatever you would like by replacing "password" after "PASSWORD=" with your password of choice.
```
sudo docker run -v "$(pwd)":/home/rstudio/work -e PASSWORD=password -p 8787:8787 -it spotify_streaming

```

### Creating report
Open a web browser and enter the URL
```
http://localhost:8787/
```
When prompted for the username enter
```
rstudio
```
and the password will be whatever is above, default is
```
password
```
Navigate to the terminal tab, change into the work directory (and update TexLive) with
```
cd work
bash update-tlmgr-latest.sh
```

And the final report can be built with
```
make report.pdf
```

## Output
### Report
If you would like to read the final report, rather than building it from the source code, it is available in "output/report.pdf"

[report.pdf](output/report.pdf)

### Sample Figures
![](output/min_month_grid.png)
![](output/top_albums.png)
![](output/minutes_year.png)
![](output/top_songs.png)
![](output/release_year_plot.png)
![](output/top_artists.png)

