---
layout: page
title: NeRFuser
description: Scalable scene representation via NeRF registration and blending.
img: assets/img/publication_preview/nerfuser.svg
importance: 1
category: research
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/nerfuser.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>

[[code]](https://github.com/ripl/nerfuser) [[paper]](https://arxiv.org/abs/2305.13307)

With another member of RIPL at TTIC, I developed `NeRFuser`, a software framework that uses an arbitrary number of pre-generated neural radiance fields (NeRFs) to represent a large-scale scene. `NeRFuser` registers individual NeRFs in a shared global coordinate system, and synthesizes better quality novel views by blending the visual information from the source NeRFs at the ray sample level. An initial version of this work was presented at the [Neural Fields Workshop @ ICLR 2023](https://sites.google.com/view/neural-fields/home), while the extended version is currently under review.

* Given pre-generated NeRFs, `NeRFuser` registers them by
    1. rendering novel views at camera poses sampled in each NeRF's local coordinate system with heuristics;
    2. re-purposing an off-the-shelf structure-from-motion algorithm to recover the poses of the synthesized images in a global coordinate system; and
    3. using the recovered poses to solve for the transform from the global coordinate system to each NeRF.
* Given the query camera pose and the transforms among the source NeRFs as solved in the registration phase, `NeRFuser` then blends the visual information from the source NeRFs at the ray sample level. Specifically,
    1. we only use NeRFs that are sufficiently close (when compared to the closest one) to the query camera for blending, which not only reduces the time cost, but also improves image quality;
    2. when it comes to the ray corresponding to a pixel to be rendered, we merge the sets of ray samples proposed by each kept source NeRF, essentially creating the union set of ray samples with their color and termination probabilities properly set; and
    3. we blend the ray samples following inverse distance weighting, where the distance between the ray sample and each NeRF's center is used.
