---
layout: page
title: Infant
description: Artistic demonstration of a digital infant's reaction to external stimuli.
img: assets/img/infant.png
importance: 3
category: events
---

[[code]](https://github.com/shengjie-lin/Infant) [[article]]({{'assets/pdf/Infant.pdf' | relative_url}})

As a cross-disciplinary endeavor to bring robotics to artistic creation, I designed the hardware system and developed the software framework for `Infant`, an interactive installation demonstrating a digital infant's reaction to external stimuli. The idea of `Infant` is formulated jointly with a student from the School of the Art Institute of Chicago (SAIC), and the project was featured in the 2020 SAIC Shows.

* With neural style transfer, the infant's state of alertness and comfort level are visualized via the gradation of art style in its skin texture.
* With face detection and tracking, the infant gets alerted by approaching and leaving of audiences. Such alert attenuates over time as the same audience stays longer within sight.
* With audio sensing, the infant is also alerted by playful sounds. However, loud noises discomfort the infant.
* With pressure data processing, the infant's comfort level is affected by touching. Gentle and steady touches comfort the infant, while sudden and strong ones discomfort it.
* With pulse sensing, the infant slowly recovers from malfuntioning caused by too much discomfort.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/infant_high_plain.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/infant_normal_rot.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/infant_malfunction.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Sample visualizations of the infant generated from neural style transfer according to its state of alertness and comfort level.
</div>
