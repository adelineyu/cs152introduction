### Introduction
Geoguessing is a popular web-based game where users are able to guess the location of a  randomized Google Street View. The game is challenging, so, as avid Geoguessers ourselves, we thought it would be a worthwhile and fun endeavor to make an application that attempts to guess the locations of a given snapshot. However, predicting the geographical location of photos without any prior knowledge is a very challenging task. 

We spent a good portion of time trying to get the Flickr image scraping code from one of our researched papers to work, but found ourselves running into more and more issues the further we got along. We decided to shift focus to using a pre-existing dataset and have decided to give this project our best shot despite having much less knowledge and ability as the professionals in the papers we have studied that have pursued the same goal. We have downloaded the image dataset that we will train our CNN with. We are now trying to build/find a CNN to use for our image classification problem.

We will create our neural network using Pytorch in the Pomona HPC servers and train it with the dataset of images we collected. The type of neural network we will use is a convolutional neural network. Our type of inputs will be .jpeg files. We will be performing a classification on those .jpeg files. 

Our intended output will be a calculated probability matrix of locations that are the highest likelihood for the input. Our end result is a web-based application to classify the location of any Google Map Street View image. We chose to focus on location classification of images outside of the game GeoGuesser, as the existing research and dataset we have found does the same. Having the application play within the web-application GeoGuesser is another step afterwards that we will not get to in the span of our project. 

We intend it to perform better than chance. To be more specific, this paper (http://graphics.cs.cmu.edu/projects/im2gps)  states that for every 6 guesses for each query, the median error is within 500 kilometers to the correct location. We would like our model to be around there. 

### Updated Literature Review (3/18/2021)
There is a various collection of pre-existing studies that have attempted to tackle this very problem, each proposing their own algorithms or different versions of similar algorithms. From these we took inspiration and molded our ideas as we researched our task from our initial plan to what we have now.

http://graphics.cs.cmu.edu/projects/im2gps/im2gps.pdf

The IM2GPS article performed a similar project. They set out with the goal to estimate geolocation from a single image via training a neural network on 6 million images scraped from Flickr and labeled with geotags. Using a nearest neighbor algorithm to compare individual photos with each of their 6 million images, comparing features such as line features, tiny images, color histograms built from the images, and more, they displayed the geographic location of a photo as a probability distribution over the Earth’s surface. 
