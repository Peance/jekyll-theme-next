---
title: "Lie Algebra Notes 1: Definitions"
categories: 
    - Note
tags: 
    - Lie Algebra
    - GTM 9
---

A class note for Undergraduate Lie Algebra given by Professor Changzheng Li, Sun Yat-Sen University. It requires only knowledge in Linear Algebra and Calculus. 

<!-- more -->
# Overture

The first thing we need is the definition of algebra, now that we are talking about Lie **algebra**.A vector space $$L$$ over field $$F$$ is called a **$$L$$-algebra** if there exists an bilinear function:
\$$
    (x,y): L \times L \rightarrow L 
$$

Bilinear means that $$(,)$$ satisfies:
1. \$$(a+b,c) = (a,c)+(b,c)$$
2. \$$(a,b+c) = (a,b)+(a,c)$$
3. \$$(\lambda a,b) =\lambda(a,b) = (a,\lambda b)$$


We will use $$[,]$$ to denote the $$(,)$$ on Lie algebra.The natural question is, what distinguishes Lie algebra from other algebras? The answer would be the nature of $$[,]$$. 

# Approaches

Please notice that in this section we are using examples which lead to desired properties of Lie algebra instead of rigious definition. The purpose of this section is to provide deeper understanding of the unusual definition made in next section.

Lie algebra is roughly the combination of Calculus and Algebra. The differential has such a property:
\$$
    \operatorname{d}(fg) = (\operatorname{d}f)g + f(\operatorname{d}g)
$$

Now, we want our product on Lie algebra holding a similar property. That is, we would like to define the product $$a*b$$ as $$\partial_a b$$, so that $$\partial_a(b*c)=(\partial_ab)*c+b*(\partial_ac)$$.

Lie algebra is deeply connected to matrices, which would be shown in the following dections. Let's put $$\partial_a b$$ and matrices together and see what we can get.

Let $$a$$ be the differential of an invertible matrix $$A(t)$$:
$$
    a = \frac{\operatorname{d}A(t)}{\operatorname{d}t}\Big\rvert _{t=0}
$$ 
where $$t$$ is a variation and $$A(0) = T_n$$. Then $$\partial_ab$$ should look like:
$$
    \partial_ab = \frac{\operatorname{d}}{\operatorname{d}t} A(t)*b \Big\rvert _{t=0}
$$

This equation will lead to two properties:
1. \$$ \partial_ab=ab-ba $$
2. \$$ \partial_a(b*c)=(\partial_ab)*c+b*(\partial_ac) $$ 

To get the first property, let $$A(t)*b = A(t)bA(t)^{-1}$$, then we have:

$$
\begin{align*}
    \partial_ab &= \frac{\operatorname{d}}{\operatorname{d}t} A(t)*b \Big\rvert _{t=0} \\
    &= \frac{\operatorname{d}}{\operatorname{d}t} (A(t)bA(t)^{-1}) \Big\rvert _{t=0}  \\
    &= (\frac{\operatorname{d}}{\operatorname{d}t} A(t)  bA(t) + A(t)b\frac{\operatorname{d}}{\operatorname{d}t} A(t)^{-1} )\Big\rvert _{t=0}\\
    &= ab + b(-a) = ab-ba
\end{align*}
$$

The equation $$\frac{\operatorname{d}}{\operatorname{d}t} A(t)^{-1} \Big\rvert _{t=0} = -a $$ comes from:
\$$
    \frac{\operatorname{d}}{\operatorname{d}t} (A(t)A(t)^{-1}) \Big\rvert _{t=0} = \frac{\operatorname{d}}{\operatorname{d}t} I_n \Big\rvert _{t=0} = 0
$$
    
Then for the second property:

$$
\begin{align*}
    \partial_a(bc) &= \frac{\operatorname{d}}{\operatorname{d}t} A(t)*bc \Big\rvert _{t=0}\\
    &=\frac{\operatorname{d}}{\operatorname{d}t} (A(t)bA(t)^{-1}A(t)cA(t)^{-1)} \Big\rvert _{t=0}\\
    &=[\frac{\operatorname{d}}{\operatorname{d}t} (A(t)*b) A(t)*c + A(t)*b \frac{\operatorname{d}}{\operatorname{d}t} (A(t)*c)] \Big\rvert _{t=0}\\
    &=(\partial_ab)*c+b*(\partial_ac)
\end{align*}
$$

# Definitions

Now we can give a rigious definition of Lie algebra. If you feel confused of this definiton, please check the above section.

An algebra $$(L,[,])$$ is called a **Lie algebra** if it satisfies:
1. \$$ [a,a]=0 \operatorname{i.e.} [a,b]=-[b,a] $$
2. \$$ [a,[b,c]] = [[a,b],c]+[b,[a,c]] $$ 

Another example to help understand the first property: Consider $$a,b$$ as the tangent vectors of a curve. Then $$[a,a]$$ must be a constant, and the only universal constant is 0.

As for property 2, Jacobi identity, the first product looks like derivative while the send looks like normoal product.

I would like to give defnitions of homomorphism and isomorphism here.

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

Construct $$f$$ by setting $$f(x) = u$$, $$f(1/\lambda y) = v$$. It's easy to show that $$f$$ is an isomorphism between Lie algebra:

$$
\begin{align*}
    f([a,b]) &= f([a_1x+a_2y,b_1x+b_2y])\\
    &= (a_1b_2-a_2b_1)f([x,y])\\
    &= \lambda (a_1b_2-a_2b_1) u \\
    &= (a_1b_2-a_2b_1)[u,\lambda v] \\
    &= (a_1b_2-a_2b_1)[f(x),f(y)] \\
    &= [f(a_1x+a_2y),f(b_1x+b_2y)] = [f(a),f(b)]
\end{align*}
$$

And $$f$$ is obviously a bijection, hence the conclusion.        
