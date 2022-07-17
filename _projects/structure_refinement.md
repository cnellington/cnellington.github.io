---
layout: page
title: Deep Learning for Protein Design
description: using deep neural networks to refine unreliable regions of protein models 
img: 
importance: 2
category: work
---
Check out the full lightning talk [here](https://www.youtube.com/watch?v=DUCImelo9UE)!

This project encompasses my research with my undergraduate
 mentor Nao Hiranuma in the Institute for Protein Design at UW. 
We worked on a deep residual network to predict unreliable 
regions in computationally-derived protein structures 
(DeepAccNet), and applied another deep residual network 
to refine these unreliable regions (ULRs).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/protein_ulr.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The DeepAccNet to Estogram (estimated divergence from true structures) to unreliable region (ULR) pipeline.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/protein_refinement.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The ULR refinement pipleine, based on the DeepAccNet architecture.
    By focusing exclusively on ULRs and including surrounding regions
    with reliable structures, we improved the 
</div>

