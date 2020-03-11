---
title: "Crystal Geometry Notes: Symmetry Elements"
categories: 
 - Note
tags: [Crystal Geometry, Space Group]
date: 2020-02-15
---

What happens when combining rotations and translation? Two kinds of such symmetries are screw and glide. Other rotations do not combine with translations in this way.

We will use symmetry elements to help understand symmetries.

<!-- more -->


## Screw Axes

A screw is a proper rotation combined with a translatin $$ \tau $$ parallel to the rotation axis. 

The angle of rotation has the same limitations as the pure roatations. Since thre must be lattice translations $$t$$ parallel to the axis, the magnitude of $$\tau$$ is restricted as  follow:
\$$
n\tau = pt, \quad n,p, \text{ are integers,}
$$

The integers $$n$$ and $$p$$ therefore categorize different kinds of screw, whose designation is written as $$n_p$$. When $$p=0$$, the screw is simply a pure rotation, and we use the origin designation $$n$$.

There are 16 possible situations, including 5 pure rotations. They can be divided into the following three groups:
1. when $$\frac pn = \frac 12$$, the screw is neutral;
2. when $$\frac pn < \frac 12$$, the screw is right-handed;
3. when $$\frac pn > \frac 12$$, the screw is left-handed.

A screw may have several threads, which are created by the lattice translation $$t$$. When $$\frac pn \leq \frac 12$$, the number of threads is $$p$$. When $$\frac pn \geq \frac 12$$, the number of threads is $$n-p$$.

### Isogonal relations

Two screw axes are said to be *isogonal* if they have the same rotational abgle $$\alpha$$. For example, the six screws $$6, 6_1, 6_2, 6_3, 6_4,\text{ and } 6_5$$ are isogonal with the pure rotation $$6$$.  

The angle between two different screws is exactly the same as the angle between the two correspondings isogonal rotation axes. Thus the directions of all axes in a space group are the same as those of the isogonal axes of some point group.

It is clear that to every point group there exists a set of isogonal space groups. This relation makes it possible to discover all the space groups by systematically exploring all the point groups.

## Glide Planes

Two glide operations in sequence generate a translation-equivalent point from the initial point. Hence the magnitude of $$\tau$$ always half some lattice translation.

Some characteristics of glide planes:

| Translation Component | Type of Glide Plane | Symbol |
| :--:| -- | :--: |
| $$\frac{a}{2},\frac{b}{2},\frac{c}{2} $$ | axial-glide plane | $$a,b,c$$ |
| $$\frac{a}{2}+\frac{b}{2}$$, or $$\frac{a}{2}+\frac{c}{2}$$, or $$\frac{b}{2}+\frac{c}{2}$$ | diagnol-glide plane | n |
| $$\frac{a}{4}+\frac{b}{4}+\frac{c}{4}$$ | "diamond"-glide plane | d |
| Zero | mirror | m |

## Combination with Translation

We've seen that a combination of two rotation is a third rotation. This is a special case of a more general that, the combination of two operations is a third operation. We will have an elementary discussion here.

### 2-fold Screw and Translation

When combing a 2-fold rotation and a translation perpendicular to the axis, the points related by the origin axis and those duplicate points can be interrelated by a symmetry element 2.

In a similar way, when combing a $$2_1$$ screw and a translation perpendicular to the axis, a new $$2_1$$ screw arises.

But if the translation $$T$$ also has a component equal to half the translation interval parallel to the axis, a new combination, a $$2_1$$ screw, occurs. 

Similarly, the combination of a $$2_1$$ screw and a translation can generate a 2-fold rotation.

In short, the combination of screws and translations will generate new screws.

### Glide and Translation

Similarly, the combinaton of glides and translations will generate new glides.

### Inversion and Translation

Similarly, the combinaton of inversions and translations will generate new inversions.

## Combination with Each Other
Because of the existence of isogonal relations, we can expect a relationship between those combinations and combinations of elements in point groups.

### Screw and Glide

We already know that the combination of a rotation and a mirror implies an iversion center at their intersection. It can be expected that the combination of a screw and a glide imples an iversion, but the location of its center must be found.

Let's set a coordinate system, where the screw axis is z-axis and the glide plane is xy-plane. Let the translation component of glide be the y-axis. In this way we can calculate the coordinatie of the result point.

We will discover that the inversion point should be $$\frac{\tau_1}{2}+\frac{\tau_2}{2}$$, where $$\tau_1$$ is the translation component of the screw and $$\tau_2$$ the translation component of the glide.

### Non-intersecting Screws

Let A and B be two axes of orthogonal but non-intersecting screws. We can set a coordinate system where x-axis parallel to A, y-axis parallel to B, and Z orthogonal to both.

Let A lies on $$x=0,y=\frac{1}{4}$$ and B lies on $$x=\frac{1}{4},z=\frac{1}{4}$$. Then a point $$(x,y,z)$$ will be transformed to $$(\frac12+x,\frac12-y,\bar{z})$$ by A, then $$(\frac{1}{2}-(\frac{1}{2}+x),-\frac{1}{2}+(\frac{1}{2}-y),\frac{1}{2}-\bar{z}) = (\bar{x},\bar{y},\frac{1}{2}+z)$$ by B. Hence the origin point and the result points are related by a screw axis along C perpendicular to both A and B.

This shows that if two of the screw axes A, B and C are present, the third is required.