---
layout: page
title: Baxter Pose Following
description: Empower the Baxter robot to follow a human's pose.
img: assets/img/baxter-pose-following.jpg
importance: 1
category: work
---

I led other members of RIPL at TTIC in the development of software to empower the Baxter robot to follow a human's pose in real time. We installed our system at the Museum of Science and Industry in Chicago for the 2022 and 2023 National Robotics Week. The installation gained great popularity during both exhibits, and had the honor to stay in the Museum for regular showcase.

* With the RGB-D image stream captured by an Intel RealSense camera, we took advantage of the state-of-the-art (as of 2023) pose model [RTMPose-m](https://github.com/open-mmlab/mmpose/tree/main/projects/rtmpose) for detecting human poses present in the image stream.
* We implemented a robust tracking algorithm to focus on a highlighted pose over frames, while identifying the user's intetion of tranfering the focus to other people.
* The 3D landmark positions of the highlighted pose were then used to compute and control the joint angles of the Baxter robot, enabling it to follow the user's pose in real time.

[[code]](https://github.com/ripl/baxter-pose-following)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/baxter-pose-following.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
