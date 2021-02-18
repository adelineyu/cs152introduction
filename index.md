## Neural Unearthing

Group members: Nick Marsano, Daniel Tamkin, Adeline Yu
### Introduction
Geoguessing is a popular web-based game where users are able to guess the location of a  randomized Google Street View. The game is challenging, so, as avid Geoguessers ourselves, we thought it would be a worthwhile and fun endeavor to make an application that attempts to guess the locations, based off of either a collection of snapshots of the surrounding areas or just one snapshot. 

### Proposed process
We believe that the biggest technical challenge will be getting enough inputs from the location in order to accurately guess. 
We propose the following two methods. 

- First, we will use image segmentation to identify key features in a picture and feed it into existing trained datasets. We will work on identifying languages on surrounding signs, famous landmarks, plant species, car brands, etc. 
- Second, we will run a neural network that gets its inputs and labels directly from GeoGuesser many times. Within each game, the program will take snapshots of a path around the location, and use the collection of snapshots taken to make a guess on the location. Overtime, it will learn the best way to take snapshots and make more accurate guesses. 

### Assessment
Our most ideal result is to get the location correctly within a mile. For our attainable goal, we would like our application to accurately guess the country (outside of the US) or the state. 

### Ethical concerns
The only ethical implication we can think of currently is potential stalking of individuals uploading photos of their current location.
