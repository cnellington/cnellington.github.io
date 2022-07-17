---
layout: page
title: Mixed Feelings
description: Recognizing, representing, and interpolating human emotions with deep learning.
img:
importance: 4
category: fun
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/mixedfeelings.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Using learned representations of emotion to project new emotions onto a neutral face.
</div>

Myself, Daniel Jeong, and Anush Devadhasan (my PhD colleagues)
a VAE-based architecture for learning latent representations
of human emotions. Check out our in-depth presentation [here](https://youtube.com/watch?v=mPtWvemach8)! 


We disentangled learned emotion representations by applying
an adversarial discriminator to the latent space.
Then we used these disentangled representations to interpolate
between emotions and project new emotions onto portrait photos.

