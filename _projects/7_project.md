---
layout: page
title: Transcrib3D
description: 3D referring expression resolution through large language models.
img: assets/img/transcrib3d.png
importance: 3
category: research
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/transcrib3d.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>

[[OpenReview]](https://openreview.net/forum?id=7j3sdUZMTF)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/transcrib3d.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

With other members of RIPL at TTIC, I developed `Transcrib3D`, a software framework that grounds referring expressions in a 3D scene. `Transcrib3D` first transcribes the object detection results from some existing vision module into textual format, and then utilizes a large language model (LLM) to resolve the referring expressions in a zero-shot manner by following meticulously designed rules. To improve over existing rules for better generalization, we further take advantage of ground truth labels in training data for the LLM to generate self-reasoned corrections, which are used to fine-tune the LLM. We show that `Transcrib3D` achieves state-of-the-art performance on both ReferIt3D and ScanRefer benchmarks. An initial version of this work was presented at the [LangRob Workshop @ CORL 2023](https://openreview.net/forum?id=7j3sdUZMTF), while the extended version is currently under review.

* Given the visual representation of a 3D scene, a vision module is used to detect objects in the scene. Specifically, [Mask3D](https://jonasschult.github.io/Mask3D/) is used for point clouds, while [MDETR](https://ashkamath.github.io/mdetr_page/) is used for RGB-D images.
* The object detection results are then transcribed into textual format, where each object is described by a set of spatial-semantic attributes.
* Given the query referring expression and the transcribed textual scene representation, an LLM is employed to resolve it in a zero-shot fashion by following meticulously designed rules.
* To improve upon existing rules for better generalization, we provide the LLM with ground truth training labels for failure cases of the zero-shot resolution, and prompt it to generate self-reasoned corrections, which are used for LLM fine-tuning.
* We show that `Transcrib3D` achieves state-of-the-art performance on both the ReferIt3D and ScanRefer benchmarks in the zero-shot manner, which is further improved by the proposed fine-tuning strategy.
* We also deploy our method both in a PyBullet simulation environment and on the UR5 robot to perform pick-and-place tasks, given queries that contain challenging referring expressions.
