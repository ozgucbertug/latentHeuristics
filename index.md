--- 
title: Latent Heuristics
description: Ozguc Bertug Capunaman (<a href="okc5048@psu.edu">okc5048@psu.edu</a>)  Shakthi Suresh (<a href="sns5410@psu.edu">sns5410@psu.edu</a>) 

![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure7.gif?raw=true)
![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure8.gif?raw=true)
![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure9.gif?raw=true)

# Our Motivation

The gap between linear and discrete nature of computational systems and the reciprocal nature of creative inquiries poses a significant barrier to employing traditional CAD systems in complex design problems. Unlike these systems, Machine Learning (ML) models can be implemented to contribute to the creative process by enabling the users to explore otherwise hidden latent space. By doing so, we hypothesize that these systems can go beyond the role of task executors and take an active role in the design process. Furthermore, by training these learning-based models on problem-specific datasets, we aim to capture design intentions and provide relevant solutions as opposed to generic, cookie-cutter algorithms traditional systems incorporate. We believe that changing our perspective on CAD systems from automation and optimization to idea generation and collaboration can facilitate new human-machine interaction scenarios in creative domains.


# Background information

## Past Reserach
Historically, the field of design has been influenced by new techniques and technologies for design representation and fabrication. Arguably, one of the most influential of such technologies has been CAD since its conceptualization in the early 60s (Cardoso Llach, 2015). Even though early visions for CAD were to create a collaborative partner in creative exploration, the course of future research shifted from developing a collaborative partner to “perfect slaves'' poised to liberate designers from arduous tasks [1], This change in perspective crystalised the instrumentalist perspective surrounding the computer aids to design discourse.

Discussing the implications of computational systems, Dreyfus asserts that human agency is capable of responding to flexible criterion where machines excel at the constant evaluation of information [2]. Creative design inquires, however, rarely follow a linear pipeline and often re-evaluate context during the design process. Similar to Dreyfus’ observation, Donald Schon defines designers’ behavior as a sequence of “seeing, drawing, seeing” [3], highlighting a reciprocal interaction throughout the design process in which discoveries and ambiguities inform design decisions. 

## Current Research 
Current literature that investigates 3D ML models offer promising results in low-dimensional representation and generation of 3D objects by appropriating well established models. Some of the most popular models used in conjunction with 3D data are Variational Autoencoders (VAE) and Generative Adversarial Networks (GAN). These models are used in a wide range of problems from scene segmentation to object classification in different applications such as autonomous vehicles and robotics.

One area that research in geometric learning focuses on is how the geometry is represented within these models. Currently, there are three mainstream representation methods for handling 3D data representation in learning-based models; (1) voxels, (2) point clouds and (3) meshes. The underlying differences between the three methods lie in the application, operation, and representation. Voxel-based approaches are prevalent in ML applications as they are inherently very similar to multidimensional inputs such as images. However, since the representation relies on a grid-based data structure, this approach is limited in its ability to scale. Point clouds, on the other hand, define each point as a set of cartesian x, y, z coordinates. It is one of the most popular ways of representing 3D data as it offers more flexibility with scaling and can easily be worked into mesh geometries using computer graphics algorithms. However, since point clouds are often unorganized in terms of neighborhood information, this representation model needs to be approached carefully, especially in conjunction with ML models. Lastly, the mesh representation stores data in polygons and vertices that make up the faces of a volume. This eliminates the problem of unorganized data structure seen in point clouds. However, since this approach incorporates the most detailed data, the operations can quickly become computationally heavy.


## Deep Auto-Encoder

## Variational Auto-Encoder (VAE)

In machine learning, dimensionality reduction is the process of reducing the number of features that describe some data. This reduction is done either by selection (only some existing features are conserved) or by extraction (a reduced number of new features are created based on the old features) and can be useful in many situations that require low dimensional data. Dimensionality reduction can be interpreted as data compression where the encoder compress the data (from the initial space to the encoded space, also called latent space) whereas the decoder decompress them. The general idea of autoencoders is pretty simple and consists in setting an encoder and a decoder as neural networks and to learn the best encoding-decoding scheme using an iterative optimisation process.

![](https://miro.medium.com/max/4800/1*iSfaVxcGi_ELkKgAG0YRlQ@2x.png)
_Encoding in different dimensions_ [0]

A variational autoencoder can be defined as being an autoencoder whose training is regularised to avoid overfitting and ensure that the latent space has good properties that enable generative process: instead of encoding an input as a single point, we encode it as a distribution over the latent space.

![](https://miro.medium.com/max/4800/1*ejNnusxYrn1NRDZf4Kg2lw@2x.png)
_Difference between autoencoder (deterministic) and variational autoencoder (probabilistic)_ [0]

# Can learning-based models trained on customized datasets capture geometric design intention?

The gap between the linear and discrete nature of computational systems and the reciprocal nature of creative inquiries poses a significant barrier to employing traditional CAD systems in complex design problems. Unlike these systems, Machine Learning (ML) models can be implemented to contribute to the creative process by enabling the users to explore otherwise hidden latent space. By doing so, we hypothesize that these systems can go beyond the role of task executors and take an active role in the design process.

![](https://hackernoon.com/hn-images/1*vEZE5VcjUr5RUbt_OWfR_w.gif)
_Interpolation of 3D shapesc_ [0]

Furthermore, by training these learning-based models on problem-specific datasets, we aim to capture design intentions and provide relevant solutions as opposed to generic, cookie-cutter algorithms traditional systems incorporate. We believe that changing our perspective on CAD systems from automation and optimization to idea generation and collaboration can facilitate new human-machine interaction scenarios in creative domains.

# System Architecture 

## Loss fucntions

In the context of an optimization algorithm, the function used to evaluate a candidate solution (i.e. a set of weights) is referred to as the objective function.
We may seek to maximize or minimize the objective function, meaning that we are searching for a candidate solution that has the highest or lowest score respectively.
Typically, with neural networks, we seek to minimize the error. As such, the objective function is often referred to as a cost function or a loss function and the value calculated by the loss function is referred to as simply “loss".

### The Earth Mover's Distance:

The Earth Mover's Distance (EMD) is a method to evaluate dissimilarity between two multi-dimensional distributions in some feature space where a distance measure between single features, which we call the ground distance is given. The EMD "lifts" this distance from individual features to full distributions. 

Intuitively, given two distributions, one can be seen as a mass of earth properly spread in space, the other as a collection of holes in that same space. Then, the EMD measures the least amount of work needed to fill the holes with earth. Here, a unit of work corresponds to transporting a unit of earth by a unit of ground distance. 



### Chamfer Distance:

The chamfer distance function measures the similarity of two contours where the distance takes two sets of edge points, from a template T and an edge map E, and evaluates the score at a translation.



__For our model, we implemennted the Chamfer distannce loss funcrtion__

## Using VAE to explore latent space

VAE offers simplicity, scalable training, and, most importantly for us, the possibility of manipulating and analyzing the outcome. In contrast, GANs and other methods are computationally expensive while offering little to no meaningful control over the output. 
The primary approach comes from the prior work done by Achlioptas et al. in their paper titled “Learning Representations and Generative Models for 3D Point Clouds” (Achlioptas et al., 2018), where they explore the data-driven design capabilities of AE and GAN. By looking at geometric data as point clouds and employing a deep Auto-Encoder, they were able to reconstruct and generalize the 3D dataset to analyze, interpolate and edit 3D shapes. 

![](https://hackernoon.com/hn-images/1*op0VO_QK4vMtCnXtmigDhA.png)
_Architecture_ [1]

In this work, we aim to explore a similar field while emphasizing the possibilities and freedom this architecture can offer in the space of suggestive creative design as opposed to engineering design. While our approach follows a similar path established by Achlioptas et al., we intend to explore the suggestive design subjectively by taking a narrow design space and extrapolating the dataset. For this reason, we propose focusing on one or two categories of shapes and enable suggestive design space that places emphasis on subjective design over objective design.

![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure1.jpg?raw=true)
_Architecture implemented in this work_[2]

We aim to work with point cloud representation over other prevailing methods. Points clouds provide unordered datasets while being computationally lenient, less memory intensive, and through surface reconstruction, offer an easy path to mesh geometries conversions when needed. Other representation models like voxels and meshes were omitted since they lead to computationally heavy models. We believe that point cloud representation offers an optimal middle ground between the memory-intensive voxel and computationally expensive mesh representations.

![](https://hackernoon.com/hn-images/1*yMFJ-7fokU0Xkx89pSFfew.gif)
_Arithmetic on 3D shapes_ [3]


# Dataset

Within the scope of this project, we plan to use the dataset available at Princeton ModelNet (Z. Wu et al., 2015), a collaborative project of online 3D shapes available for research. Princeton ModelNet covers 662 objects with 127,915 unique CAD models
Each model on the ModelNet dataset is labeled and classified by category tags. However, models under each subsets are unlabeled. Since our aim is to not classify the models but rather extract local and global geometric features and fill in the creative space between models to explore different designs, the lack of these labels does not pose any problem.

![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure3.jpg?raw=true)
_Different shape and size of Vases in the dataset_ [3]

![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure4.jpg?raw=true)
_Different categories of Vase shapes to explore design intent of ML model_[2]

In addition to using ModelNet for developing and testing our model, we also aim to explore custom synthetic data generated using parametric modeling tools such as Grasshopper for Rhinoceros 3D. This would allow us to explore how geometric intentions can be learned through a deliberately biased dataset and investigate how well learning-based algorithms can generate problem-specific solutions.

![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure0.gif?raw=true) 
_Various forms of a Vase generated from Rhinoceros 3D to explore custome synthetic data_[4]

# Results
Input/output/Loss values

# Future Work
This work primarily focuses on stage one of a two stage project. Stage one (Geometric Learning) uses a deep autoencoder that utilizes input from our dataset to train the model into learning the geometric patterns and intentions that can then decode it from the latent space. 

In stage two of this project (Hypothesis Generation), we aim to utilize the decoder from stage one to reconstruct partial or incomplete input through the latent space vector. This stage allows  to  learn  shape  completion  using  an  unsupervised  maximum  likelihood  (ML)  loss  by training a new recognition model, a new encoder.

![](https://github.com/ozgucbertug/latentHeuristics/blob/main/docs/Figure2.jpg?raw=true) _Stage one - Geometric Learning and Stage two - Hypothesis Generation_[4]

# References
https://towardsdatascience.com/understanding-variational-autoencoders-vaes-f70510919f73
https://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/RUBNER/emd.htm


