--- 
title: Latent Heuristics
description: Ozguc Bertug Capunaman (<a href="okc5048@psu.edu">okc5048@psu.edu</a>)  Shakthi Suresh (<a href="sns5410@psu.edu">sns5410@psu.edu</a>) 
---
![](https://cs.stanford.edu/~kaichun/structurenet/images/teaser.png)

# Our motivation

The gap between the linear and discrete nature of computational systems and the reciprocal nature of creative inquiries poses a significant barrier to employing traditional CAD systems in complex design problems. Unlike these systems, Machine Learning (ML) models can be implemented to contribute to the creative process by enabling the users to explore otherwise hidden latent space. By doing so, we hypothesize that these systems can go beyond the role of task executors and take an active role in the design process. Furthermore, by training these learning-based models on problem-specific datasets, we aim to capture design intentions and provide relevant solutions as opposed to generic, cookie-cutter algorithms traditional systems incorporate. We believe that changing our perspective on CAD systems from automation and optimization to idea generation and collaboration can facilitate new human-machine interaction scenarios in creative domains.

# Background information

## Variational Auto-Encoder (VAE)

In machine learning, dimensionality reduction is the process of reducing the number of features that describe some data. This reduction is done either by selection (only some existing features are conserved) or by extraction (a reduced number of new features are created based on the old features) and can be useful in many situations that require low dimensional data. Dimensionality reduction can be interpreted as data compression where the encoder compress the data (from the initial space to the encoded space, also called latent space) whereas the decoder decompress them. The general idea of autoencoders is pretty simple and consists in setting an encoder and a decoder as neural networks and to learn the best encoding-decoding scheme using an iterative optimisation process.

![](https://miro.medium.com/max/4800/1*iSfaVxcGi_ELkKgAG0YRlQ@2x.png)
_Encoding in different dimensions_ [0]

A variational autoencoder can be defined as being an autoencoder whose training is regularised to avoid overfitting and ensure that the latent space has good properties that enable generative process: instead of encoding an input as a single point, we encode it as a distribution over the latent space.

![](https://miro.medium.com/max/4800/1*ejNnusxYrn1NRDZf4Kg2lw@2x.png)
_Difference between autoencoder (deterministic) and variational autoencoder (probabilistic)_ [0]

## Loss fucntions

In the context of an optimization algorithm, the function used to evaluate a candidate solution (i.e. a set of weights) is referred to as the objective function.
We may seek to maximize or minimize the objective function, meaning that we are searching for a candidate solution that has the highest or lowest score respectively.
Typically, with neural networks, we seek to minimize the error. As such, the objective function is often referred to as a cost function or a loss function and the value calculated by the loss function is referred to as simply “loss".

### The Earth Mover's Distance:

The Earth Mover's Distance (EMD) is a method to evaluate dissimilarity between two multi-dimensional distributions in some feature space where a distance measure between single features, which we call the ground distance is given. The EMD "lifts" this distance from individual features to full distributions. 

Intuitively, given two distributions, one can be seen as a mass of earth properly spread in space, the other as a collection of holes in that same space. Then, the EMD measures the least amount of work needed to fill the holes with earth. Here, a unit of work corresponds to transporting a unit of earth by a unit of ground distance. 

>EQUATION?

### Chamfer Distance:

The chamfer distance function measures the similarity of two contours where the distance takes two sets of edge points, from a template T and an edge map E, and evaluates the score at a translation.

>EQUATION?

__For our model, we implemennted the Chamfer distannce loss funcrtion__


# Can learning-based models trained on customized datasets capture geometric design intention?

The gap between the linear and discrete nature of computational systems and the reciprocal nature of creative inquiries poses a significant barrier to employing traditional CAD systems in complex design problems. Unlike these systems, Machine Learning (ML) models can be implemented to contribute to the creative process by enabling the users to explore otherwise hidden latent space. By doing so, we hypothesize that these systems can go beyond the role of task executors and take an active role in the design process.

![](https://hackernoon.com/hn-images/1*vEZE5VcjUr5RUbt_OWfR_w.gif)
_Interpolation of 3D shapesc_ [0]

Furthermore, by training these learning-based models on problem-specific datasets, we aim to capture design intentions and provide relevant solutions as opposed to generic, cookie-cutter algorithms traditional systems incorporate. We believe that changing our perspective on CAD systems from automation and optimization to idea generation and collaboration can facilitate new human-machine interaction scenarios in creative domains.


# Using VAE to explore latent space

sive while offering little to no meaningful control over the output.
The primary approach comes from the prior work done by Achlioptas et al. in their paper titled “Learning Representations and Generative Models for 3D Point Clouds” (Achlioptas et al., 2018), where they explore the data-driven design capabilities of AE and GAN. By looking at geometric data as point clouds and employing a deep Auto-Encoder, they were able to reconstruct and generalize the 3D dataset to analyze, interpolate and edit 3D shapes. 

![](https://hackernoon.com/hn-images/1*op0VO_QK4vMtCnXtmigDhA.png)
_Architecture_ [1]

In this work, we aim to explore a similar field while emphasizing the possibilities and freedom this architecture can offer in the space of suggestive creative design as opposed to engineering design. While our approach follows a similar path established by Achlioptas et al., we intend to explore the suggestive design subjectively by taking a narrow design space and extrapolating the dataset. For this reason, we propose focusing on one or two categories of shapes and enable suggestive design space that places emphasis on subjective design over objective design.

![](https://hackernoon.com/hn-images/1*yMFJ-7fokU0Xkx89pSFfew.gif)
_Arithmeti on 3D shapesc_ [2]

In this work, we are going to work with point cloud representation over other prevailing methods. Points clouds provide unordered datasets while being computationally lenient, less memory intensive, and through surface reconstruction, offer an easy path to mesh geometries conversions when needed. Other representation models like voxels and meshes were omitted since they lead to computationally heavy models. We believe that point cloud representation offers an optimal middle ground between the memory-intensive voxel and computationally expensive mesh representations.

# Results
Input/output/Loss values

# Takeaway

# References
https://towardsdatascience.com/understanding-variational-autoencoders-vaes-f70510919f73
https://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/RUBNER/emd.htm


