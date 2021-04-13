--- 
title: Latent Heuristics
description: Ozguc Bertug Capunaman (<a href="okc5048@psu.edu">okc5048@psu.edu</a>)  Shakthi Suresh (<a href="sns5410@psu.edu">sns5410@psu.edu</a>) 
---

## Can learning-based models trained on customized datasets capture geometric design intention?

The gap between the linear and discrete nature of computational systems and the reciprocal nature of creative inquiries poses a significant barrier to employing traditional CAD systems in complex design problems. Unlike these systems, Machine Learning (ML) models can be implemented to contribute to the creative process by enabling the users to explore otherwise hidden latent space. By doing so, we hypothesize that these systems can go beyond the role of task executors and take an active role in the design process.

![](https://hackernoon.com/hn-images/1*vEZE5VcjUr5RUbt_OWfR_w.gif)
_Interpolation of 3D shapesc_ [0]

Furthermore, by training these learning-based models on problem-specific datasets, we aim to capture design intentions and provide relevant solutions as opposed to generic, cookie-cutter algorithms traditional systems incorporate. We believe that changing our perspective on CAD systems from automation and optimization to idea generation and collaboration can facilitate new human-machine interaction scenarios in creative domains.


## Using VAE to explore latent space

sive while offering little to no meaningful control over the output.
The primary approach comes from the prior work done by Achlioptas et al. in their paper titled “Learning Representations and Generative Models for 3D Point Clouds” (Achlioptas et al., 2018), where they explore the data-driven design capabilities of AE and GAN. By looking at geometric data as point clouds and employing a deep Auto-Encoder, they were able to reconstruct and generalize the 3D dataset to analyze, interpolate and edit 3D shapes. 

![](https://hackernoon.com/hn-images/1*op0VO_QK4vMtCnXtmigDhA.png)
_Architecture_ [1]

In this work, we aim to explore a similar field while emphasizing the possibilities and freedom this architecture can offer in the space of suggestive creative design as opposed to engineering design. While our approach follows a similar path established by Achlioptas et al., we intend to explore the suggestive design subjectively by taking a narrow design space and extrapolating the dataset. For this reason, we propose focusing on one or two categories of shapes and enable suggestive design space that places emphasis on subjective design over objective design.

![](https://hackernoon.com/hn-images/1*yMFJ-7fokU0Xkx89pSFfew.gif)
_Arithmeti on 3D shapesc_ [2]

In this work, we are going to work with point cloud representation over other prevailing methods. Points clouds provide unordered datasets while being computationally lenient, less memory intensive, and through surface reconstruction, offer an easy path to mesh geometries conversions when needed. Other representation models like voxels and meshes were omitted since they lead to computationally heavy models. We believe that point cloud representation offers an optimal middle ground between the memory-intensive voxel and computationally expensive mesh representations.

## (results)

## (takeaway)

## References



