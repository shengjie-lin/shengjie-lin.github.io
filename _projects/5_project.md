---
layout: page
title: Statler
description: State-maintaining language models for embodied reasoning.
img: assets/img/statler.png
importance: 2
category: research
---

[[project page]](https://statler-lm.github.io/) [[paper]](https://arxiv.org/abs/2306.17840)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/statler.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

With other members of RIPL at TTIC, we developed `Statler` based on the existing work of [Code as Policies](https://code-as-policies.github.io/). The gist of `Statler` is a state-maintaining language model, where an explicit representation of the world state is maintained over time and intended for long-horizon operations.

* Upon receiving the user's query, `Statler` feeds it to the `world_model_reader`, which extends it with the current world state and uses it as the prompt to elicit code generation from a large language model (LLM). Specifically, GPT 3.5 is used.
* The generated code not only enables the robot to perform the action in response, but also calls the `world_model_writer` with the necessary information to update the world state.
* `world_model_reader` and `world_model_writer` are both instances of general-purpose GPT-driven LLMs separatedly tuned via few-shot prompting. We found that splitting the reasoning burden into different LLMs results in improved accuracy and stability for long-horizon operations.
