---
title: "The Definition of Lie Algebra"
categories: 
    - Lie Algebra
tags: 
    - Lie Algebra
---

In this post we will give the definition of Lie Algebra as well as some other basic concepts.
<!-- more -->

# Definitions

## Algebra

A vector space $$L$$ over field $$F$$ is called a **$$L$$-algebra** if there exists an bilinear function:
\$$
    (x,y): L \times L \rightarrow L 
$$

Bilinear means that $$(,)$$ satisfies:
1. $$(a+b,c) = (a,c)+(b,c)$$
2. $$(a,b+c) = (a,b)+(a,c)$$
3. $$(\lambda a,b) =\lambda(a,b) = (a,\lambda b)$$

## Lie Algebra

We will use $$[,]$$ to denote the $$(,)$$ on Lie algebra.

An algebra $$ (L,[,]) $$ is called a **Lie algebra** if it satisfies:
1. $$[a,a]=0$$ i.e. $$ [a,b]=-[b,a]$$ 
2. $$[a,[b,c]] = [[a,b],c]+[b,[a,c]]$$ (Jacobi identity)

## Homomorphism and Isomorphism

A function $$f:L\rightarrow L^{\prime}$$ is called **homomorphism** of Lie algebra if:
    \$$f([x,y])=[f(x),f(y)] \quad \forall x,y\in L$$

A hormormorphism of Lie algebra is called an **isomorphism** if it is a bijection.

# Examples

## dim = 1

In this case, $$[\lambda e, \mu e] = \lambda \mu  [e,e] =0$$, this algebra is trivial.

## dim = 2

In this case, $$L = Fe_1 + Fe_2$$. If $$[e_1, e_2]\neq 0$$, denoted $$[e_1,e_2]$$ as $$x$$, and we have $$x = ae_1+be_2$$. Then $$\forall y \in L$$:
\$$
[x,y] = [ae_1+be_2,ce_1+de_2]=(ad-bc)[e_1,e_2]=(ad-bc)x.
$$

Then $$L$$ is isomorphic to $$L^{\prime}= Fu\oplus Fv$$, where $$[u,v] = u$$.

$$L^{\prime}$$ is a Lie algebra: we can define $$[,]:L' \times L' \rightarrow L'$$ s.t. $$[u,u] = [v,v]=0$$ and $$[u,v] = u = -[v,u]$$.

Construct $$f$$ by setting $$f(x) = u$$, $$f(1/\lambda y) = v$$. It's easy to show that $$f$$ is an isomorphism between Lie algebra. 

# Read more
[Lie Algebra Class Note 1](https://peance.github.io/note/2020/05/07/LieAlg-Week1/)