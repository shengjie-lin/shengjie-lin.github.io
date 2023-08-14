---
layout: page
title: Baxter Pose Following
description: Empower the Baxter robot to follow a human's pose.
img: assets/img/baxter-pose-following.jpg
importance: 1
category: work
---

With the help of other members of RIPL at TTIC, I developed the software to empower the Baxter robot to follow a human's pose in real time. The system was showcased at the Museum of Science and Industry in Chicago for the 2022 and 2023 National Robotics Week. The installation gained great popularity, and had the honor to stay in the Museum for regular exhibition.

* With the RGB-D image stream captured by an Intel RealSense camera, I took advantage of the state-of-the-art (as of 2023) pose model [RTMPose-m](https://github.com/open-mmlab/mmpose/tree/main/projects/rtmpose) for detecting human poses in the image stream.
* Considering the potentailly huge crowd, I implemented a robust tracking algorithm to focus on a highlighted pose over frames, while recognizing the user's intetion of tranfering the focus to other people.
* The 3D landmark positions of the highlighted pose are then used to compute and control the joint angles of the Baxter robot according to its kinematics.
* Given that Baxter cannot move its arms at the comparable speed of a human, the target pose is frequently refreshed so that the robot always tries to catch up with the user's real-time pose.

[[code]](https://github.com/ripl/baxter-pose-following)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/baxter-pose-following.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
