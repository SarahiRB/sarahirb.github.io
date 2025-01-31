---
layout: post
title: high dimensions ruining the fun
date: 2025-01-31 16:29:00
description: In high dimensions they won't hear ya scream.
tags: images intuitive
categories: ML math
thumbnail: assets/img/square-circle-points.png
---

Well, here's a square with a circle inside.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/square-circle.png" class="img-fluid rounded z-depth-1" %} 
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/square-circle-points.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This is a 2-dimensional space, if you filled it with 20 points most of them would land inside the circle.
</div>

Now here's a cube with a sphere inside.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cube-sphere.png" class="img-fluid rounded z-depth-1" %} 
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/cube-sphere-points.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A 3-dimensional space. And most of the points would land inside the sphere, it's pretty much the same as before.
</div>

But what happens as we keep increasing the dimensions? Will it still be the same?

Well... apparently, no.

### Sooo.... What happens?

#### to the sphere
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/volume-hyper-sphere.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This gives you the volume of a sphere given a dimension (d). Actually, it should be called an "hypersphere" as a generalization. 
</div>

Here's the thing: the denominator increases faster than the numerator for higher and higher values of d
(i.e., the volume shrinks as d increases).

#### to the cube
Its volume remains unchanged (it was 1 when it was a 3D cube, and it’ll still be 1 when it becomes a 100D cube).

But its vertices? The number of them skyrocket with higher dimensions.

### And what does it mean?

In the previous example, almost all the random points were inside the circle/sphere.

In higher dimensions (e.g., 1000D), the volume of the hypersphere almost vanishes, meaning the points will be clustered around the corners. And there are *lots* of them (2^1000 in a 1000D space).

Before, if those points represented two or three different classes (imagine them as colors), and you wanted to classify a new point (i.e., determine its color based on nearby points), it was easy—just look at the surrounding points and assign the most common class (color).

But in higher dimensions, all the points are in the corners and roughly equidistant from each other, so that trick no longer works.

*Basically, that's why k-NN struggles with high-dimensional data.*