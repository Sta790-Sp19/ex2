Exercise 2 - Week 2
----------------------

### Task 0 - Setup

* Make sure you have a working Docker install on your VM or locally.

* You should be able to run `docker run --rm hello-world` successfully as well as pull images from DockerHub.


### Task 1 - Creating an R focused docker image reproducibly

* Using rocker's r-ver as your base image create a "light weight" image that provides at least the following packages

  * Data handling - `tidyverse`, `sf`
  * Modeling - `tidymodels`, `rjags`, `rstan`, `brms`
  * Extra - any other packages you are particularly fond of
  
* Our goal is to avoid some of the heavier dependencies in the versioned stack (e.g. latex, rstudio, etc.)

* Write up a Dockerfile that will reproducibly create this image 

* Make sure that `docker build` is able to completely and correctly build your image


### Task 2 - Performance

* Compare the performance between `r-ver` and `debian:stretch`, with R installed via apt, when performing the following 
linear algebra operation (you should only benchmark the matrix multiplication, not the matrix generation):

```r
x = matrix(rnorm(1e6), 1e3)
z = x %*% x
```

* Pay attention to the version of R you get in the `debian:stretch` image - does matching versions appear to matter?

* Which container performed better? Based on `r-ver`s Dockerfile do you have any idea about why this difference might exist?
