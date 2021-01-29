# Analytics Project

In this project, you will be implementing an AutoEncoder to support timeseries compression
while preserving similarity search. You'll first implement one of the autoencoders
presented in a paper of your choice (see paper section below). Then, you'll try your best
to improve the autoencoder results.

## AutoEncoders

Briefly, deep autoencoders are neural networks that introduce a bottleneck in the network.
The section before the bottleneck is called the encoder. The section after the bottleneck
is called the decoder. During training, the autoencoder learns how to reconstruct the
input data. In doing so, the bottleneck generates a small matrix (or vector) that, should
retain important information about the input. This is called the __latent space__.

Image of TBD

## Papers

There are a growing number of papers that use autoencoders for timeseries clustering. We
include two of the more recent ones:

* [Learning Representations for Time Series Clustering][1]
* [Salient Subsequence Learning for Time Series Clustering][2]
* [RTFN: Robust Temporal Feature Network][3]

We suggest you find papers that have code that you can replicate. Alot of this code uses
TensorFlow v1. Therefore, part of your task is porting or interpretting the autoencoder
architecture to TensorFlow v2.

## Code

### Repositories

[https://github.com/fsolleza/timeseries-similarity](https://github.com/fsolleza/timeseries-similarity) contains the code for the actual project. See the brief code description below.

[https://github.com/fsolleza/timeseries-data](https://github.com/fsolleza/timeseries-data)
contains code that helps you read in benchmark datasets used in academia for timeseries
analytics tasks. Read the repository's README for how to use this repository.

### Brief code description

The code uses Python and TensorFlow to implement a simple autoencoder. The file
`auto_encoder.py` has two Model classes: `Encoder` and `Decoder`. There is also a
`train_step` function that executes a single training step and backpropagates the loss.
`Experiments.ipynb` shows how to train and run the experiments we care about.

### Experiments

*Reconstruction*: We care about whether the autoencoder can sufficiently reconstruct the
inputs from a given code. We'll be using Euclidean Distance (L2 norm) to calculate the
reconstruction however, this can be modified depending on your approach.

*Clustering*: We care about whether the code can be clustered effectively. We use KMeans
clustering here. We use Euclidean Distance because it's far cheaper than other timeseries
similarity measures like Dynamic Time Warping.


[return home](index.md)

[1]: ./papers/dtcr.pdf
[2]: ./papers/ussl.pdf
[3]: ./papers/rtfn.pdf

