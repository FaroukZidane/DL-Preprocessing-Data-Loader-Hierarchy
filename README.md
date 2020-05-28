# Deep Learning Hierarchical Toolkit handling Pre-processing and Data set disk loading - implementing Keras and TensorFlow



## Introduction

This simple hierarchical toolkit aims to keep your python files well-organized and neat when building your own deep network.

## Pre-processing

- Simple pre-processing (resizing)

Before inserting the input image to the network, it is very much common to apply some pre-processing operations to it in order to make it ready for the network to train. This toolkit comprises pre-processing module which handles:

1. resizing the input image to your desired `width x height`.
2. applying the `interpolation` technique by OpenCV.



- Image to array (channel order)

Before inserting the input image to the network, it is better to take note of the channel ordering of the image, by default in keras json file, the ordering is channels last, which means that the channels is in the last ordering of the image format (WxHxD), so here we insure if the image was in the default keras format, otherwise, we would change the format to the one used in keras json. So simply this handles:

1. returning a new NumPy array with the channels properly ordered.

## Data set loading

Loading the data set from disk is a process you will to do every time you want to want to train your network. Having a module which handles this operation is a good practice. This simply handles:

1. Loading the dataset from your input data set path
   - Handling both: input image and class labels
2. Apply the pre-processing operations sequentially on the data set images. So actually, this is built upon the preprocessing module in a hierarchical manner.

All you have to do is to include this module `dlcv` in your project directory or repository. Then simply from .`dlcv` import `SimpleDataSetLoader` or `Preprocessing`