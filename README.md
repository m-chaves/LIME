# A comparison of methods for generation of perturbed samples for LIME.

## Overview

In this project, we focus on an interpretability machine learning technique proposed by  [Ribeiro et al. (2016)](https://dl.acm.org/doi/10.1145/2939672.2939778), known as **Local Interpretable Model-agnostic Explanations (LIME)**, restricted to its application to image classification.
This method is based on studying the change in the prediction probabilities caused by controlled distortions to the input image.
In this work, we propose different methods to perturb images and compare their results to those given by the original version of LIME.

To be more specific, the original technique generates distorted versions of an image by randomly selecting some regions of the original image $\xi$ to be changed.
We call *turned off* regions the parts of the image that will suffer a change and *turned on* the ones that will not.
We explore different alteration approaches for *turned off* regions.
We start by generating a replacement image $\xi^*$.
Then we replace the *turned off* regions of the original image with the respective pixels in $\xi^*$, while the pixels in the *turned on* regions remain unchanged.
With the default settings, LIME follows this same process to distort images, simply using the mean of the pixels in the *turned off* regions for replacement.
We explore 7 other ways of creating $\xi^*$ and, therefore, changing how perturbed samples are generated.

> Read the full report here

This study takes place as part of the Maasai team in collaboration with Université Côte d'Azur. 
Maasai is a research team at Inria Sophia-Antipolis, working on the models and algorithms of Artificial Intelligence. 
This is a joint research team with the laboratories LJAD (Mathematics, UMR 7351) and I3S (Computer Science, UMR 7271) of Université Côte d’Azur. 

## How to use this repository?

Install the requirements using 

``` pip install -r requirements.txt ```

The lime_perturbed_samples jupyter notebook contains a condensed version of the image perturbation techniques.
The notebook also contains functions of the evaluation methods explained in the full report.   

