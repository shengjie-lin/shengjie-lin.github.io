---
layout: page
title: Baxter Rubik's Cube
description: Solving a Rubik's Cube with the Baxter robot.
img: assets/img/baxter-rubiks-cube.jpg
importance: 4
category: event
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/baxter-rubiks-cube.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>

With joint efforts from other members of RIPL at TTIC, we developed the software to enable Baxter to physically solve an arbitrarily initialized Rubik's cube. The robot picks up and scans the Rubik's cube to determine its intial state, and solves it with both grippers. The project was presented during the 2019 National Robotics Week at the Museum of Science and Industry in Chicago.

* Using the built-in cameras mounted by the grippers, the robot locates the Rubik's cube and picks it up.
* The robot then exposes all 6 faces of the cube to the RealSense camera through a programmed routine, and uses a clustering-based technique to determine the grid of colors on each face, which is robust to lighting conditions.
* [Kociemba's Two-Phase-Algorithm](http://kociemba.org/cube.htm) is used to generate the solution to the cube, which gets executed accurately by Baxter with visual servoing.
* A visualization module is implemented to display the current step of solution and the cube's real-time state in 3D graphics.
