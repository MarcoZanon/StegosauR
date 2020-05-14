# StegosauR
R package for Cryptographic Steganography

```StegosauR``` is a package for [R](https://cran.r-project.org/) that allows to hide a text message inside a tiff image.

A more detailed description can be found [on my website](https://www.zanon.xyz/cryptographic_steganography_StegosauR_intro.html).

## Preliminary note
```StegosauR``` has been tested with different R versions up R 3.6.3.

```StegosauR``` works with R x64 4.0.0, but crashes with R i386 4.0.0. The problem appears to be located within package [tiff](https://cran.r-project.org/web/packages/tiff/index.html), which is necessary to run ```StegosauR```. More in detail, its function ```readTIFF()``` crashes without returning any error.   

## Installation procedure

There are a couple of ways to install ```StegosauR```. Both of them start with downloading the StegosauR_0.1.0.tar.gz file contained in this GitHub repository.

### method 1
  * Install R package "devtools" by typing ```install.packages("devtools")``` in the R shell. 
  
  * Type ```library(devtools)``` to load the package you just installed.
  
  * Install ```StegosauR``` with the command ```devtools::install_local("<replace with_file_path>/StegosauR_0.1.0.tar.gz")```.


### method 2
  * Install the necessary dependencies first with ```install.packages(c("jpeg","tiff","png","Unicode","dplyr","openssl","magrittr"))```.
  
  * Download the StegosauR_0.1.0.tar.gz file from this page
  
  * Then install ```StegosauR``` by typing ```install.packages("C:/replace all this part with the path to your file/StegosauR_0.1.0.tar.gz", repos = NULL, type = "source")```.



Once the installation is complete, just type in ```library(StegosauR)``` to load the package.


### Quick example

``` {r}
# pick an image
img <- "image_name.jpg"

# message to encode
txt <- "Message stored with R package StegosauR v.0.1.0"

# add a password
psw <- "password_123"

#encode the message
encosaur(input=img, output="new_image_name", message=txt, secret=psw)

#decode message
decosaur(input="new_image_name.tiff", secret=psw)

```
