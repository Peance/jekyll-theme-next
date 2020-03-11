---
title: "Crystal Geometry Notes: Point Groups"
categories: Note
tags: [Crystal Geometry, Point Group]
date: 2020-03-10
---

# Basic Model
Crystal geometry aims to describe the patterns of ordered congruent motifs. A minimal set of motifs is called cell. A cell can be translated, rotated or reflected with some limitations.

<!-- more -->
# Translation
A motif can be traslated in three directions. The natural way to describe such operation, of course, is using vector:
\$$  
T=u\mathbf{t_1}+v\mathbf{t_2}+w\mathbf{t_3} 
$$

## Lattice
We can choose a cell and use its sides as the basic translation vectors. Then we can build a coordinate system based on the three translation vectors. This system is called lattice.

The cell usually represents the symmetry of the motifs in a way. There are 7 kinds of cells. Each kind of cell can have several types, and there are 14 types of 3D lattice.

*We are talking Bravais lattice here. In fact, we can add some types of lattice when needed.*

# Proper Rotation
A motif can be rotated about an axis through an angle. When combined with translation, the angle is restricted to $$ 2\pi, \pi, \frac23\pi, \frac{\pi}2  \text{ and } \frac{\pi}3 $$ for the rotated motif has to be a duplicate of a translated motif. 

Traditionally, we use numbers $$ 1,2,3,4,6 $$ to indicate the rotation.

## Combination

When two operations are combined, a third arised as a consequence.

For example, consider a 4-fold rotation $$A$$ combined with a 2-fold rotation $$B$$. Imagine a xyz-axis here, where z-axis is $$A$$ and the other two axis are $$B$$. That is, a non-origin point should be rotated around the z-axis through $$ \frac{\pi}{4} $$, and rotated around other axis though $$ \frac{\pi}{2} $$. As a result, the combination will generated 8 congruent points. Notice that a new rotation $$C$$ arises in this combination, which is different from $$B$$.

The combination is distinct from either $$A$$ or $$B$$, and related to a third operation $$C$$. So we can use three numbers to represent such combinations. Non-trival solutions are:
\$$
222 \quad 32(2) \quad 422 \quad 622 \quad 23(3) \quad 432
$$

These are the standard representations for these axial-symmetry combinations.

# Improper Rotation

Your right hand turns to left hand in the mirror. Such an operation is called an operation of *second sort*. Another kind of operation of second sort is inversion.

Operations of second sort are special cases of a more general operation, improper rotation. There are two varieties of improper rotation.

Rotoreflection
: The motif is rotated about an axis $$A$$ and reflected across a plane normal to $$A$$. The rotation and reflection can be performed in either order.

Rotoinversion
: The motif is rotated about an axis $$A$$ and inverted through a point on the axis. The rotation and inversion can be performed in either order.

These two varities accomplish for the sam purpose. We will use rotoinversion from now on.

An operation of the second sort produces an enantiomorphic object. If the same operation acts on the new object, the result will be enantiomorphic with the second, hence congruent to the origin object. Hence in a cyclical sequence of objects, the total number of operations (and therefore objects) must be even.

The angles permitted to rotoinversion are the same as those for the pure rotation operation. We place a bar over the numbers to indicate such operations.

## Representing $$\bar{n}$$ by other symmetries

| rotoinversion | replacement | equivalent rottreflection |
|:--:|--|:--:|
|$$\bar{1} $$| $$i$$: inversion |$$\bar{2} $$|
|$$\bar{2} $$| $$m$$: reflection |$$\bar{1 } $$|
|$$\bar{3} $$| $$3i$$: a 3-fold proper rotation and an inversion|$$\bar{6 } $$|
|$$\bar{4} $$| $$-$$ |$$\bar{4 } $$|
|$$\bar{6} $$| $$\frac{3}{m}$$: a 3-fold proper rotation and a reflection |$$\bar{3 } $$|

## Combination

Let $$P$$ be a proper rotation and $$I$$ a improper one. We already know that when combining two proper rotations, a third proper rotations will arises, so the combination is $$PPP$$.

A proper rotation produces a congruent object while a improper rotation produces a enantimorphic one, hence the combination of them, which can be described as a third rotation, is of the second sort, so the combination is $$PII$$.

Obviously improper rotations should come in pairs, otherwise the produced object wouldn't be congruent. Therefore, the final list should be:
\$$
PPP ,\quad PII ,\quad IPI ,\quad IIP
$$

Another combination of $$I$$ and $$P$$ is that two axes can coincide, denoted as $$\frac{P}{I}\frac{P}{I}\frac{P}{I}$$.

There are 21 distinct combinations involving improper rotation.

# Point Groups

There are 32 point symmetries in total. They are the products of proper and improper rotations. 

