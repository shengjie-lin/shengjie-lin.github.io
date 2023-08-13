---
layout: page
title: Code as Policies on UR5e
description: Implementation of Code as Policies on the UR5e robot.
img: assets/img/code-as-policies-ur5e.png
importance: 2
category: work
---

Together with other members of RIPL at TTIC, I implemeted the [Code as Policies](https://code-as-policies.github.io/) algorithm on the UR5e robot. The robot was able to respond to the user's voice command and execute the corresponding task. The project was presented at the 2023 National Robotics Week at the Museum of Science and Industry in Chicago. It also paved the way for our future work on [Statler](https://statler-lm.github.io/).

* We used the [SpeechRecognition](https://pypi.org/project/SpeechRecognition/)+[Whisper](https://github.com/openai/whisper) library to implement the wake-up word mechanism and convert the user's voice line into text.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/code-as-policies-ur5e.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
