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


## Spotify Clustering

This notebook consists of the unsupervised clustering of my Liked Songs from Spotify to create a set of playlists, with the hope that one of the clusters will be suitable for running. I used a Gaussian Mixture Model (GMM) to cluster the songs according too their audio features. I will used a GMM due to it's soft clustering feature which allows non-mutually exclusive clusters, this allows songs similar to multiple playlists to be included in both. 

This process found 11 clusters. I concluded for plotting of centroids and empirical evidence (use of the playlists) that the 8th cluster is the most suitable running playlist.

## Spotify Classification

This notebook consists of the binary classification as of each of my Liked songs on Spotify on there quality to run too: 1 being a good song to run too and 0 being a bad song to run too. 

I did this firstly by the generation of a rating for 650 of my songs, this was done using the Spotify API to play a song followed by a user input to rate the song. From these ratings I built a classifiers using the songs audio features. I used both a Ridge classifier and a RBF kernel SVM classifier, both these models were optimised using cross-validation. 

I selected the SVM model to be the most suitable model, I then proceeded to make a prediction of the quality of all the remaining songs in my Liked Songs using this model.
