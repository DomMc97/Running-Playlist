# Running Playlist

## Overview

In this project I created running playlists using songs in my Liked Songs playlist on Spotify. I did this using 3 distinct methodologies: empirical modelling, unsupervised clustering and binary classification. I'm currently in the process of evaluating the most succesful technique.


## Spotify Data

This first notebook deals with the acquisition of my Liked Songs from Spotify and their audio features. This was acheived using a Spotify API I set up and the Spotipy library. After accessing the data I created a dataframe with the information which I cleaned for invalid tracks (such as songs which I have liked but have since been removed from Spotify). Finally I stadardised the audio features.  

## Spotify Model
 This notebook creates a playlist on my Spotify account by filtering my songs to find 'good' running songs based on the following model assumptions:
1.   The songs in the playlist should have a good running tempo, which is 135-185 BPM as per this running [article](https://www.runnersneed.com/expert-advice/training/running-and-music-finding-your-bpm.html).
2.   The music should also be loud, which I define to be above average loudness for my Liked Songs, under the assumption that a loud song will 'pump me up'.
3. The song should be energetic to psychologically enhance my own energy.
4. The playlist should be of an order of roughly 150-300 songs in order to be long enough for repeated use without over repetition but not too long to overburden my phones memory.
