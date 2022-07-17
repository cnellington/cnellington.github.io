---
layout: page
title: Contextualized
description: a machine learning toolbox for inferring highly personalized statistical models.
img: assets/img/contextualized_icon.png
importance: 1
category: work
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/contextualized_logo.png" title="contextualized logo" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

A statistical machine learning toolbox for estimating models, distributions, and functions with context-specific parameters.

Take a look at the [main demo](https://github.com/cnellington/Contextualized/blob/main/demos/main_demo.ipynb) for a complete overview with code, or the [easy demo](https://github.com/cnellington/Contextualized/blob/main/demos/Easy-demo/easy_demo.ipynb) for a quickstart with sklearn-style wrappers!

Implemented by [Caleb Ellington](https://calebellington.com/) (CMU) and [Ben Lengerich](http://web.mit.edu/~blengeri/www/index.shtml) (MIT).

## Install and Use Contextualized
```
pip install git+https://github.com/cnellington/Contextualized.git
```

## Contextualized Family
Context-dependent modeling is a universal problem, but every domain presents unique challenges and opportunities. 
Here are some layers that others have added on top of Contextualized.
Feel free to add your own page(s) by sending a PR.

<table>
<tr>
<td><a href="http://bio-contextualized.ml/">bio-contextualized.ml</a></td>
<td>Contextualized and analytical tools for modeling medical and biological heterogeneity</td>
</tr>
</table>

## Related Publications and Pre-prints
Lengerich, Benjamin J., Mark E. Nunnally, Yin Aphinyanaphongs, Caleb Ellington, and Rich Caruana. 2022. “Automated Interpretable Discovery of Heterogeneous Treatment Effectiveness: A COVID-19 Case Study.” Journal of Biomedical Informatics, April, 104086. https://www.sciencedirect.com/science/article/pii/S1532046422001022

Lengerich, Ben, Caleb Ellington, Bryon Aragam, Eric P. Xing, and Manolis Kellis. 2021. “NOTMAD: Estimating Bayesian Networks with Sample-Specific Structures and Parameters.” arXiv [stat.ML]. arXiv. http://arxiv.org/abs/2111.01104.

Lengerich, Benjamin J., Maruan Al-Shedivat, Amir Alavi, Jennifer Williams, Sami Labbaki, and Eric P. Xing. 2020. “Discriminative Subtyping of Lung Cancers from Histopathology Images via Contextual Deep Learning.” medRxiv. https://www.medrxiv.org/content/10.1101/2020.06.25.20140053v1.abstract.

Al-Shedivat, Maruan, Avinava Dubey, and Eric P. Xing. 2018. “Personalized Survival Prediction with Contextual Explanation Networks.” arXiv [cs.LG]. arXiv. http://arxiv.org/abs/1801.09810.

Al-Shedivat, Maruan, Avinava Dubey, and Eric Xing. 2020. “Contextual Explanation Networks.” Journal of Machine Learning Research: JMLR 21 (194): 1–44.
https://jmlr.org/papers/v21/18-856.html
