---
layout: page
title: Code as Policies on UR5e
description: Implementation of Code as Policies on the UR5e robot.
img: assets/img/code-as-policies-ur5e.png
importance: 2
category: events
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/code-as-policies-ur5e.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>

With joint efforts from other members of RIPL at TTIC, we implemeted the [Code as Policies](https://code-as-policies.github.io/) algorithm on the UR5e robot. The robot is able to respond to the user's voice command and execute the corresponding task. The project was presented during the 2023 National Robotics Week at the Museum of Science and Industry in Chicago. It also paved the way for our future work on [Statler](https://statler-lm.github.io/).

* The wake-up-word mechanism and dynamic ambient sound adaptation is implemented to robustly transcribe the user's voice line into text within a noisy environment.
* As in [Code as Policies](https://code-as-policies.github.io/), the user's voice input is then used to generate code for the robot to execute, which may perform some pick-place action and/or verbal response.
* Since the pick-place action is prompted by natural language, we use an open-vocabulary object detection algorithm [MDETR](https://ashkamath.github.io/mdetr_page/) to locate the object of interest in the scene.
* Using the depth data from the RealSense camera, the pixel aligned object is turned into a 3D point cloud, which is then used to determine the gripper's position and orientation for the pick-place action.
