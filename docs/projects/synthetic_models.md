# Synthetic LandScape Generation
While working on synthetic landscape generation or neutral landscape generation, it it interesting to try out different randomizing and clustering algorithms. The ones included here were part of the same experiments. The outputs are generally preceded by a header so that the ASCII files can be read easily in a GIS software such as ArcMap. The output file is ASCII type since this is commonly accepted by multiple tools. The number of rows and columns can be changed as can the no data value which for now is set to a 16 bit signed integer output. There are codes included to generate a video using landscapes as frames within the output file. Further work can include the nlmpy module 

## Table of contents
* [Installation](#installation)
* [Packages](#usage-examples)
	* [Clumped matrix algorithms](#clumped-matrix-algorithms)
    * [Fragmentation Aggregation Algorithms](#fragmentation-aggregation-algorithms)
    * [NlmPy applications](#nlmpy-applications)
    * [Noise Function Terrain Generation](#noise-function-terrain-generation)
    * [Random matrix algorithms](#random-matrix-algorithms)
	* [Random matrix to video](#random-matrix-to-video)
* [Credits](#credits)

## Installation
We assume that the user already has a copy of Matlab and has installed necessary libraries in python such as nlmpy and numpy+mlk and scipy. The toolbox can be modified to accomodate varying sizes of images to be produced and varying number of classes. The codes are mostly written in matlab and some implementation in NlmPy produced by [ Etherington et al](http://onlinelibrary.wiley.com/doi/10.1111/2041-210X.12308/epdf) are included as well.

## Packages
Each folder has a variety of packages and tools available to run different kinds of analysis. Tools and methods include and are not limited to the following


### Clumped matrix algorithms
This allows for clumping to occur in random matrix algorithms such that there is an element of non random allocation of class

| filename                     | Description                                                             |
|------------------------------|-------------------------------------------------------------------------|
| clumped_randi_land.m         |clumping algorithm applied to Uniformly distributed pseudorandom integers|
| clumped_sprand_land          |clumping algorithm applied to Sparse uniformly distributed random matrix |


### Fragmentation Aggregation Algorithms
This one is more specific looking at different fragmentation and aggregation algorithms and allows the user to set convergence time for solution.It includes Gibbs model and Metropolis-Hastings algorithm.
 
### NlmPy applications
NlmPy was created as a python library which allows the user to user different algorithms [ Etherington et al](http://onlinelibrary.wiley.com/doi/10.1111/2041-210X.12308/epdf). The output files as ASCII to allow for easy read.

### Noise Function Terrain Generation
These Matlab functions allows you to test noise functions to generate artificial terrains using noise function executables.Source codes for the c++ noise functions files are included in the adjoining folder and were provided kindly by Travis Archer for open use.The codes create a bmp output which are then modified to create binned responses and landscape classes as needed. Noise types include
* Cell Noise
* Diamond Square
* Erosion
* Midpoint Displacement
* Perline Noise
* Simplex Noise
* Value Noise

### Random matrix algorithms
This uses the random matrix functions within matlab to extract different landscape types. Once again they are exported as ASCII.

| filename                     | Description                                       |
|------------------------------|---------------------------------------------------|
| randi_land.m                 |Uniformly distributed pseudorandom integers        |
| sprand_land.m                |Sparse uniformly distributed random matrix         |
| rand_land.m                  |Uniformly distributed random numbers               |
| rng_seed_land                |Random Seed Generation with Random Number Generator|


### Random matrix to video
These are experiments within matlab to use the landscapes generated as frames in a video output file from the landscapes. The video output is generally in avi format and includes slices of the landscapes produced.

## Credits
I would like to thank Dr. Scott Robeson my mentor among others who got me interested in some topics on Landscape ecology.
