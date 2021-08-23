---
layout: page
title: sPIrograph
description: Geometric drawing with a spirograph using a bare-bones Raspberry Pi (2020)
img: /assets/img/sPIrograph1.JPG
importance: 1
category: technical
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/sPIrograph1.JPG' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
            Images made with digital sPIrograph
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <p>
        Using some rotary dials and a display, this is a digitalized spirograph drawing tool! This program runs off a bare-bones Raspberry Pi. 
        </p> 
        <p>
        The spirograph file spirograph.c uses many libraries I developed for the bare-bones Raspberry Pi. The dials portion reads in each dial value to determine the various radii for the spiral and also represents the "pencil" that draws the curve. The rest of the code contains math equations to draw those curves (as a series of dots) on a graphical display.
        </p>
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/sPIrograph2.JPG' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/sPIrograph4.JPG' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/sPIrograph3.JPG' | relative_url }}" alt="" title="example image"/>
    </div>
</div>

<br/>

***

<h2 class="category"> see it in action </h2>

<p style="text-align:center" > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/yW_d6hbv3v0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
</p>

***

<h2 class="category"> code </h2>

<script src="https://gist.github.com/lkmsf/db1df083b6d5764ac4a4073b2baff7c2.js"></script>
