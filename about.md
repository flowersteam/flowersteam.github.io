---
layout: page
title: About
permalink: /about
---

## What is Developmental Systems?
The Developmental Systems blog presents and discusses work from the [Flowers Lab](https://flowers.inria.fr) (Inria, Univ. Bordeaux and Ensta ParisTech) and collaborators. It targets a wide and interdisciplinary audience. 

The works we present here are part of a long-term research program to understand autonomous developmental learning, at the frontiers of AI and cognitive sciences. This research program in [developmental machine learning](https://www.youtube.com/watch?v=7bJ0fnvPLaA&feature=emb_logo) studies how machines could learn like children, i.e. how one could build machines that are able to develop open-ended repertoires of sensorimotor and social skills in the real world, with limited resources of time, energy and compute. In return, we also study how computational models of developmental learning can be used as [tools to understand better human learning](http://www.pyoudeyer.com/oudeyerWiley16.pdf), as well as in [educational technologies](http://www.pyoudeyer.com/oudeyerGottliebLopesPBR16.pdf) to foster efficient and intrinsically motivated learning. 

## Getting started

New to the lab's research? Here are some good entry points:

- **[About the lab](https://flowers.inria.fr)** — our mission and long-term research programme
- **[Blog posts](/blogs)** — accessible write-ups of our latest work
- **[Publications](/publications)** — selected list of academic papers

## Key themes

**Human autotelic learning**

We use methods from psychology to design new experimental protocols, and computational theories and models to design and test hypotheses about human autotelic learning and how it interacts with metacognition, language and social interaction.


**Machine autotelic learning**

We aim to design and build open-ended learning machines that are autotelic, data frugal, with strong generalisation skills, and leverage language and social interaction to integrate within human cultures (values, ethics, preferences). We leverage generative AI systems, encoding forms of human cultural knowledge, as cognitive tools, and we aim to improve the frugality and grounding of generative AI systems using autotelic deep reinforcement learning.

**Applications: Educational technologies and Assisted scientific discovery**

In *Educational technologies*, we aim to stimulate curiosity-driven autotelic learning, meta-cognition and creativity in humans across the lifespan and across neurodiversity (leveraging both models of human autotelic learning and frugal generative edTech tools). In the domain of *Assisted scientific discovery*, we aim to study how curiosity-driven autotelic exploration algorithms can help scientists (physicists/chemists/mathematicians, …) make discoveries in complex systems.


## Latest talks & videos

- [Developmental machine learning (Pierre-Yves Oudeyer)](https://www.youtube.com/watch?v=7bJ0fnvPLaA)
- [MAGELLAN: Curriculum learning and metacognition for curiosity-driven open-ended LLM agents
](https://www.youtube.com/watch?v=OGxa_YUg4Nk)
- [Améliorer l'usage des IA génératives chez les collégiens : effets d'un atelier pédagogique (French video)](https://www.youtube.com/watch?v=jhuiRymIkyk)

## Latest blogs

{% for post in site.posts limit:5 %}
<div class="post py1">
  <div style="display: flex; gap: 1rem; align-items: flex-start;">
    <div style="flex-shrink: 0; width: 90px; text-align: right;">
      <p class="post-meta" style="margin: 0;">{{ post.date | date: site.date_format }}</p>
    </div>
    <div style="flex: 1; min-width: 0;">
      {% if post.external_url %}
      <a href="{{ post.external_url }}" class="post-link" target="_blank" rel="noopener">
        <h3 class="h3 post-title">{{ post.title }} <span class="external-link-icon">↗</span></h3>
      </a>
      {% else %}
      <a href="{{ post.url | relative_url }}" class="post-link">
        <h3 class="h3 post-title">{{ post.title }}</h3>
      </a>
      {% endif %}
      <div class="post-meta post-authors">
        {% for auth in post.authors %}<a href="{{ auth.link }}">{{ auth.name }}</a>{{ auth.next }}{% endfor %}
      </div>
      {% if post.summary %}<p class="post-summary">{{ post.summary }}</p>{% endif %}
    </div>
    {% if post.thumbnail %}
    <a href="{% if post.external_url %}{{ post.external_url }}{% else %}{{ post.url | relative_url }}{% endif %}" {% if post.external_url %}target="_blank" rel="noopener"{% endif %} style="flex-shrink: 0;">
      <img src="{{ post.thumbnail }}" alt="{{ post.title | xml_escape }}" style="width: 400px; height: 267px; object-fit: cover; border-radius: 4px;">
    </a>
    {% endif %}
  </div>
</div>
{% endfor %}

## Contact

Interested in collaborating or joining the lab? Reach out via the [About](/about) page.
