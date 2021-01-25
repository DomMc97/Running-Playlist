# Running Playlist

## Overview

In this project I created running playlists using songs in my Liked Songs playlist on Spotify. I did this using 3 distinct methodologies: empirical modelling, unsupervised clustering and binary classification. I'm currently in the process of evaluating the most succesful technique.


## Spotify Data

This first notebook deals with the acquisition of my Liked Songs from Spotify and their audio features. This was acheived using a Spotify API I set up and the Spotipy library. After accessing the data I created a dataframe with the information which I cleaned for invalid tracks (such as songs which I have liked but have since been removed from Spotify). Finally I stadardised the audio features.  
