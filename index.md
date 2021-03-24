## Neural Unearthing

Group members: Nick Marsano, Daniel Tamkin, Adeline Yu
### Introduction
Geoguessing is a popular web-based game where users are able to guess the location of a  randomized Google Street View. The game is challenging, so, as avid Geoguessers ourselves, we thought it would be a worthwhile and fun endeavor to make an application that attempts to guess the locations of a given snapshot. However, predicting the geographical location of photos without any prior knowledge is a very challenging task. 

Our current plan is that we will be using the IM2GPS provided code to create a dataset by scraping Flickr to collect 1,000,000 images that are location-tagged. The IM2GPS code (http://graphics.cs.cmu.edu/projects/im2gps/flickr_code.html)  is discussed more below in our Related Works Section.
We will then create our neural network using Pytorch in the Pomona HPC servers and train it with the dataset of images we collected. The type of neural network we will use is a convolutional neural network. Our type of inputs will be .jpeg files. We will be performing a classification on those .jpeg files. We plan to use the open-source S2 (https://s2geometry.io/) geometry library to subdivide the surface of the Earth into non-overlapping cells. From literary sources we expect to have up to 26,200 cells however we may change our methods, altering this number. We will also incorporate scene filtering based on contextual knowledge about the environmental scene. We will take these two methods to predict geolocation probabilities and use that to compute our classification output. For each input test image, we expect our neural network to output the probability of the image being taken at that location, for all possible locations. If we subdivide the Earth into 26,200 cells, then we expect 26,200 probabilities. Our end result is a web-based application to classify the location of any Google Map Street View image. 
We chose to focus on location classification of images outside of the game GeoGuesser, as the existing research and dataset we have found does the same. Having the application play within the web-application GeoGuesser is another step afterwards that we will not get to in the span of our project. 

Our intended output will be a calculated probability map, see similar example on page 8 of this paper: http://graphics.cs.cmu.edu/projects/im2gps/im2gps.pdf. We would like our results to be more accurate than chance. To be more specific, this paper (http://graphics.cs.cmu.edu/projects/im2gps)  states that for every 6 guesses for each query, the median error is within 500 kilometers to the correct location. We would like our model to be around there.  

### Project Update 1 (3/13/2021) 
Our current plan is that we will be using the IM2GPS code to create a dataset by scraping Flickr. We initially expect to collect 1,000,000 images for our training purposes.

The IM2GPS code can be found here: http://graphics.cs.cmu.edu/projects/im2gps/flickr_code.html

We will then create our neural network on pytorch in the Pomona HPC servers and train it with the dataset of images we collected. The type of neural network we will use is a convolutional neural network. Our type of inputs will be .jpeg files. We will be performing a classification on those .jpeg files (screenshots of random Google Map Street View locations). Lastly, we will create a web-based application to classify the location of any Google Map Street View image. 
 
We plan to use Google’s open-source S2 (https://code.google.com/archive/p/s2-geometry-library/) geometry library to subdivide the surface of the Earth into non-overlapping cells. From literary sources we expect to have up to 26,200 cells however we may change our methods, altering this number. We will then predict probabilities of photos  being taken from inside these individual cells in order to produce our classification output.

For each input test image, we expect our neural network to output the probability of the image being taken at that location, for all possible locations. If we subdivide the Earth into 26,200 cells, then we expect 26,200 probabilities.

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
Once we get enough images to train our neural network, we believe that the biggest task at hand is to create this neural network. We plan to create a CNN. The CNN will take the dataset, which includes snapshots from Google Street View and the labels of its location (a geographical cell partitioned on Google Earth). 

Once it is done training, the user can input some screenshot from Google Street View, feed it to our neural network, and our neural network will output the probabilities for each geographical cell, but listing the highest probability as its guess for the location. 

We realize this process currently does not involve the actual game GeoGuesser, however the work we do here can then be migrated towards a neural network that can play the GeoGuesser game. 

### Assessment
Our most ideal result is to get the location correctly within a mile. For our attainable goal, we would like our application to accurately guess the country (outside of the US) or the state. 

### Ethical concerns
The only ethical implication we can think of currently is potential stalking of individuals uploading photos of their current location.
