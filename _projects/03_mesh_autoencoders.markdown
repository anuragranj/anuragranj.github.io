---
layout: page
title: Mesh Autoencoders
description: Generate faces, clothing and more using mesh convolutional autoencoders
img: /assets/img/coma.png
---

<div class="img_row">
    <img class="col two obj-top" src="{{ site.baseurl }}/assets/img/coma_samples.jpg" alt="" title="Faces using CoMA"/>
    <img class="col one obj-top obj-right" src="{{ site.baseurl }}/assets/img/autoenclother.jpg" alt="" title="Clothing using Mesh-VAE-GAN"/>
</div>
<div class="col three caption">
    Generated faces using Convolutional Mesh Autoencoders and dressing humans with a GAN added to the CoMA framework.
</div>



### Learning to Generate Faces

{% cite ranjan2018generating %}

Learned 3D representations of human faces are useful for computer vision problems such as 3D face tracking and reconstruction from images, as well as graphics applications such as character generation and animation. Traditional models learn a latent representation of a face using linear subspaces or higher-order tensor generalizations. Due to this linearity, they can not capture extreme deformations and non-linear expressions.

To address this, we introduce a versatile model that learns a non-linear representation of a face using spectral convolutions on a mesh surface. We introduce mesh sampling operations that enable a hierarchical mesh representation that captures non-linear variations in shape and expression at multiple scales within the model. In a variational setting, our model samples diverse realistic 3D faces from a multivariate Gaussian distribution. Our training data consists of 20,466 meshes of extreme expressions captured over 12 different subjects. Despite limited training data, our trained model outperforms state-of-the-art face models with 50% lower reconstruction error, while using 75% fewer parameters. We also show that, replacing the expression space of an existing state-of-the-art face model with our autoencoder, achieves a lower reconstruction error.

### Dressing Humans in 3D

{% cite ma2019dressing %}

Three-dimensional human body models are widely used in the analysis of human pose and motion. Existing models, however, are learned from minimally-clothed humans and thus do not capture the complexity of dressed humans in common images and videos. To address this, we learn a generative 3D mesh model of clothing from 3D scans of people with varying pose. Going beyond previous work, our generative model is conditioned on different clothing types, giving the ability to dress different body shapes in a variety of clothing. To do so, we train a conditional Mesh-VAE-GAN on clothing displacements from a 3D SMPL body model.

This generative clothing model enables us to sample various types of clothing, in novel poses, on top of SMPL. With a focus on clothing geometry, the model captures both global shape and local structure, effectively extending the SMPL model to add clothing. To our knowledge, this is the first conditional VAE-GAN that works on 3D meshes. For clothing specifically, it is the first such model that directly dresses 3D human body meshes and generalizes to different poses.

{% bibliography --cited %}
