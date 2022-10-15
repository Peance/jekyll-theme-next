---
title: "Singular Homology"
categories: 
    - Algebraic Topology
tags: 
    - Homology
---

Given a space, we want to study it "step by step". We want to sort out the points, the edges, the faces etc. All those things are connected: edges connecting points,  faces gluing to edges etc, and those connecting can be viewed as maps. In algebra, such a long chain is called a ***chain complex***, and our first goal is to assign a chain complex to a given space. Then we can use homology to understand the maps. 

This series is abondoned. 

<!--more-->

Now we have a topological space $X$.

## Topological n simplex

The "simplest" objects is triangular, and the analog here is topological $n$-simplex $\Delta^n_{top}$, they are defined as:

$$
\{ (x_0,\dots,x_n)\in \mathbb{R}^n \mid x_i\geq 0, \sum_i x_i =1 \}
$$

As for the map, all maps between those $n$-simplexs are boil down to face maps: 

$$
d^i(x_0,\dots,x_n) = (x_0,\dots,x_{i-1},0, x_i,\dots,x_n)
$$

## Singular simplicial set

We look at the homomorphisms from topological $n$-simplex to sets, which are called ***singular simplicial set***. They are defined by:

$$
Sing_n(X):=\hom_{Top}(\Delta^{n}_{top},X) : \Delta^{op} \rightarrow Set
$$

Together with the face maps between topological $n$-simplex, we now have a chain of sets:

$$
\dots \xleftarrow{d_i}\hom_{Top}(\Delta^n_{top},X) \xleftarrow{d_i} \hom_{Top}(\Delta^{n+1}_{top},X) \xleftarrow{d_i}\dots 
$$

For example, $Sing_0 (X)$ is set of points of $X$, and $Sing_1(X)$ are paths in $X$. Now, $f: \Delta^{1}_{top}\rightarrow X$ is sent to $f(1)\in X$ by $d_0$.

## Singular chain complex

Recall that for each set $S$, we can find a free abelian group $\mathbb{Z}(S)$ such that every map from $S$ to any abelian group $G$ factors through $\mathbb{Z}(S)$.  We abelianize the singular simplicial set to get a chain of abelian groups: 

$$
C_n(X;\mathbb{Z}):=\mathbb{Z}\{Sing_n(X)\}
$$

This thing is not a chain complex yet, we still need a differential map. It is of course built upon the face maps:

$$
d:= \sum_{i=0}^n (-1)^i d_i:A_n \rightarrow A_{n-1}
$$

where $d_i$ is the $i$-th face map. 

Check: pick $\alpha \in A_{n+1}$, WTS $d^2(\alpha) = 0 \in A_{n-1}$. Indeed, 

$$
d^2(\alpha)= \sum_i \sum_j (-1)^{i+j} d_i d_j \alpha
$$

which can be broken into two pieces:

$$
\sum_{0\leq i < j \leq n+1} + \sum_{0\leq j \leq i <n+1}
$$

It is easy to check the following simplicial identities:

$$
d_id_j = d_{j-1}d_i,\quad i<j
$$ 

as well as

$$
d_j d_j = d_j d_i, \quad j \leq i
$$

And eventually we can prove that $d^2=0$.


## Singular homology 

Then we define $H_n(X;\mathbb{Z})$ as usual. 

## Property

### H0

We can immediately prove $H_0$ is a free abelian group. By definition, $H_0=Z_0/B_0$. Here $Z_0=C_0$, which is the set of points in $X$. Since $d=d_0-d_1$, $d(\sigma) = \sigma(1)-\sigma(0)$. Hence 

$$
H_0 = \mathbb{Z}\{\text{pts of X}\}/\sim
$$

where $x_0\sim x_1$ if there's a path connecting them.

### Disjoint spaces

Claim: $\mathbb{Z}\{\amalg_{\lambda\in \Lambda} S_\lambda\}\cong \bigoplus_{\in \Lambda} \mathbb{Z}\{S_\lambda\}$, where $\amalg$ is the disjoint union.

The claim follows from the following facts:
1. free abelian group functor preserves **co**products;
2. $H_n(\bigoplus_{\lambda\in \Lambda} A^\lambda_\bullet ) \cong \bigoplus H_n(A^\lambda_\bullet)$
where $A_\bullet= \bigoplus_{\lambda \in \Lambda} A_\bullet^\lambda$ of chain complexes $A_\bullet^\lambda$, where $A_n = \oplus A_n^\lambda$ and $d= \oplus d^\lambda$;
3. $\hom_{Top}(\Delta^n_{top},\amalg_{\lambda \in \Lambda}X_\lambda) \cong \amalg \hom_{Top}(\Delta^n_{top},X_\lambda)$ ( because each topological n-simplex is connected);
4. $C_\bullet (\amalg_{\lambda\in\Lambda}) X_\lambda; \mathbb{Z}) \cong \oplus_{\lambda \in \Lambda} C_\bullet(X_\lambda;\mathbb{Z})$

## Preview

The next question is: For what kind of spaces can we compute $H_n(X;\mathbb{Z})$ for all $n$?

