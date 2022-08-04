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
{% include about/skills.html title="Programming Skills" source=site.about.programming-skills %}
{% include about/skills.html title="Software Skills" source=site.about.software-skills %}
{% include about/skills.html title="Other Skills" source=site.about.other-skills %}
</div>

## Experience
<div class="row">
<div class="col mt-4">
  <div class="timeline-body bg-themed">
    {% for item in site.about.exp-timeline %}
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
    {% for item in site.about.edu-timeline %}
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

* Course Introduction to CNC Technology by SIEMANS and APSSDC - *May 2017 - Jul 2017*

## Achievements

### Awards

* UR Graduate Scholarship - *Jul 2020*
* 2nd prize in competition Sumo Fight organised by MECHATRONICS-17 - *Nov 2017*
* 1st prize in competitions Pick ‘N’ Place and Soccer League Robotica at Ekathra-17 - *Mar 2017*
* 2nd prize in competitions Drag race and Mozobien Conducted at Ekathra-17 - *Mar 2017*
* 1st prize in competition Robotrix at VIDHYUTRA-2k17 - *Feb 2017*

### Participation

* Escalade Mains organised by Techniche at IIT Guwahati - *Sep 2019*
* SAE BAJA 2018 organised by SAEINDIA at Chitkara University - *Jul 2018*
* Robowars organised by SHAASTRA 2017 at IIT Madras - *Jan 2017*
* MECHATRONICS-16 Conducted by Rotary Club - *Sep 2016*
* Extreme Racing by VIVAAN 2k16 - *Mar 2016*

### Publications

* Pusapati Suryanarayana Raju, Dr. Subash Gokanakonda, Mallipudi Sarad Kumar, Kankatala Sai Kumar. **"Design and fabrication of a radio-controlled mini rover with audio-visual sensors, suspension and four-wheel steering."** *International Journal of Advance Research, Ideas and Innovations in Technology* 5.3 (2019). www.IJARIIT.com.

## Volunteership

* International Peer Advisor, UR International - *Spring/Summer 2021*
* Volunteer, National Service Scheme (NSS) - *2016-2018*
* Volunteer, Rotaract Club - Gayatri Vidya Parishad (RC-GVP) - *2016-2018*

## Hobbies

* Micro-controller programming.

