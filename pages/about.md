---
layout: page
title: About
permalink: /about/
weight: 1
---

# **About Me**

Hi I am **{{ site.author.name }}** :wave:,<br>
I am a data-driven engineer, which means I solve real-world problems using Statistical modelling and Machine learning techniques.

<div class="row">
{% include about/skills.html title="Programming Skills" source=site.data.programming-skills %}
{% include about/skills.html title="Other Skills" source=site.data.other-skills %}
</div>

## Experience
<div class="row">
<div class="col mt-4">
  <div class="timeline-body bg-themed">
    {% for item in site.data.exp_timeline %}
      <div class="timeline-item">
        <div class="content">
          <h2>{{ item.title }}</h2>
          <h6 class="date">{{ item.from }} — {{ item.to }}</h6>
          <p>{{ item.description }}</p>
        </div>
      </div>
    {% endfor %}
  </div>
</div>
</div>

## Education
<div class="row">
<div class="col mt-4">
  <div class="timeline-body bg-themed">
    {% for item in site.data.edu_timeline %}
      <div class="timeline-item">
        <div class="content">
          <h2>{{ item.title }}</h2>
          <h6 class="date">{{ item.from }} — {{ item.to }}</h6>
          <p>{{ item.description }}</p>
        </div>
      </div>
    {% endfor %}
  </div>
</div>
</div>

## Certifications

## Achievements
  ### Awards
  ### Publications

## Hobbies


