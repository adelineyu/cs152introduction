## Neural Unearthing

Group members: Nick Marsano, Daniel Tamkin, Adeline Yu
### Introduction
Geoguessing is a popular web-based game where users are able to guess the location of a  randomized Google Street View. The game is challenging, so, as avid Geoguessers ourselves, we thought it would be a worthwhile and fun endeavor to make an application that attempts to guess the locations, based off of either a collection of snapshots of the surrounding areas or just one snapshot. 

### Literature Review
Source: https://arxiv.org/abs/1810.03077
These researchers share a similar intent as us with creating a model that could do well at playing the game GeoGuessr. They ended up  making a model that was 20 times better than chance at predicting random locations  in the US. This model could beat humans in 4 out of 5 rounds of the game. They created the 50states10K dataset which is a set of 125000 samples, 10000 unique images of each of the 50 states gathered from Google Street View. This is a dataset we are interested in looking at for our project.  

Source: https://www.youtube.com/watch?v=mM_dC1HVAQ4
Here, this YouTuber walks the viewer through how he trained an AI to play GeoGuessr. He shows the AI being trained in various different epochs. He uses convolutional neural networks and feature extraction to train it. 

Source: https://arxiv.org/abs/1602.05314
This article approaches the issue of photo geolocation through image classification. They subdivided the earth into thousands of multi-scale geoegraphic cells and trained a neural network using millions of geotagged images. Rather than using landmarks or approximate matching, their models integrate multiple visual cues to guess the image location. Their’s exceeded all others and even attained superhuman levels of accuracy in some cases.

Source: https://phys.org/news/2008-06-geographic-photos.html
This article describes the IM2GPS algorithm designed by Carnegie Mellon University. The algorithm doesn’t attempt to identify distinguishing features within the photo but rather “analyzes the composition of the photo, notes how textures and colors are distributed and records the number and orientation of lines in the photo.” and then searching Flickr for similar photos. Instead of asking the computer to analyze a photo, the computer just needs to find photos that look like a given photo.

### Proposed process
We believe that the biggest technical challenge will be getting enough inputs from the location in order to accurately guess. 
We propose the following two methods. 

- First, we will use image segmentation to identify key features in a picture and feed it into existing trained datasets. We will work on identifying languages on surrounding signs, famous landmarks, plant species, car brands, etc. 
- Second, we will run a neural network that gets its inputs and labels directly from GeoGuesser many times. Within each game, the program will take snapshots of a path around the location, and use the collection of snapshots taken to make a guess on the location. Overtime, it will learn the best way to take snapshots and make more accurate guesses. 

### Assessment
Our most ideal result is to get the location correctly within a mile. For our attainable goal, we would like our application to accurately guess the country (outside of the US) or the state. 

### Ethical concerns
The only ethical implication we can think of currently is potential stalking of individuals uploading photos of their current location.
