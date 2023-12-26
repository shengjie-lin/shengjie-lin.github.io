---
layout: page
title: Code as Policies on UR5
description: Implementation of Code as Policies on the UR5 robot.
img: assets/img/code-as-policies-ur5.png
importance: 2
category: events
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/code-as-policies-ur5.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>

With joint efforts from other members of RIPL at TTIC, we implemented the [Code as Policies](https://code-as-policies.github.io/) algorithm on the UR5 robot. The robot is able to respond to the user's voice command and execute the corresponding task. The project was presented during the 2023 National Robotics Week at the Museum of Science and Industry in Chicago, and at the University of Chicago for the 2023 South Side Science Festival. It also paved the way for our future work on [Statler](https://statler-lm.github.io/).

* The wake word mechanism and dynamic ambient sound adaptation are implemented to robustly transcribe the user's spoken line into text within a noisy environment.
* As in [Code as Policies](https://code-as-policies.github.io/), the user's voice input is then used to generate code for the robot to execute, which may involve performing a pick-and-place action and/or issuing a verbal response.
* Since the pick-and-place action is prompted by natural language, we use an open-vocabulary object detection algorithm [MDETR](https://ashkamath.github.io/mdetr_page/) to locate the object of interest in the scene.
* Using the depth data from a RealSense camera, the pixel-aligned image region of the object is turned into a 3D point cloud, which is then used to determine the gripper's position and orientation for the pick-and-place action.
