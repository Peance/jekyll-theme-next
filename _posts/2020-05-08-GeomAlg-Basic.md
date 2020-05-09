---
title: "Introduction to Geometric Algebra"
categories: 
    - Note
tags: 
    - Geometric Algebra
---

This note is the first part of my bachelor thesis, which is basically a reading note of David Hestenes' paper. It contains the definition of Geometric Algebra and some examples. It's written in Chinese.
<!-- more -->


# 数学定义

几何代数处理的对象仍然是向量。本章将从向量空间出发，构造出几何代数，然后给出具体的运算法则，为下一节的应用做准备。

考虑域$$\mathbb{F}$$上的任意维向量空间$$V$$，其上定义二次型$$q:V\rightarrow \mathbb{F}$$，满足：

1. $$q(\alpha v) = \alpha^2 q(v) \quad \forall \alpha \in \mathbb{F}, v\in V$$；
2. 映射$$(v,w)\mapsto q(v+w)-q(v)-q(w)$$对$$v$$和$$w$$都是线性的。

由此衍生出的双线性型$$\beta_q(v,w)=\frac12(q(v+w)-q(v)-q(w))$$则称为$$q$$的极化。

几何代数是张量代数的商代数。张量代数由$$V$$中任意有限个向量的张量积生成，张量积的符号记为$$\otimes$$。$$k$$个向量的积称为$$k$$-向量。对于固定的$$k$$，所有的$$k$$-向量生成一个向量空间$$T^k = \otimes^{k} V$$，即$$T^k$$对加法和标量乘法封闭（注意这并不意味着两个$$k$$-向量的和仍然是$$k$$-向量，但这个和仍然在该向量空间中）。特别的，$$T^0$$是域$$\mathbb{F}$$，$$T^1$$是向量空间$$V$$。所有这些向量空间的直和形成了张量代数：

$$
\begin{align*}
    \mathcal{T}(V):=\bigoplus_{k=0}^{\infty}T^k.
\end{align*}
$$

几何代数在张量几何的基础上添加了$$v\otimes v - q(v) \cong 0$$这一性质，具体的构造是考虑形如$$v\otimes v - q(v)$$的元素形成的理想：

$$
\begin{align*}
    \mathcal{I}_{q}(V):=\left\{\sum_{k} A_{k} \otimes(v \otimes v-q(v)) \otimes B_{k} \quad: \quad v \in V, A_{k}, B_{k} \in \mathcal{T}(V)\right\}.
\end{align*}
$$

张量代数商去该理想即为几何代数：$$\mathcal{G}(V,q):=\mathcal{T}(V)/\mathcal{I}_q(V)$$，其中的积，称为几何积，继承自$$\mathcal{T}(V)$$中的张量积：

$$
        \mathcal{G} \times \mathcal{G} \rightarrow \mathcal{G} 
        (A, B) \mapsto A B:=[A \otimes B]=A \otimes B+\mathcal{I}_{q}
$$

注意到：

$$
\begin{align*}
    v^2&=[v\otimes v]\\
    &=[v\otimes v -q(v)1 +q(v)1]\\
    &=[v\otimes v-q(v)1]+q(v)1_{\mathcal{G}}\\
    &=q(v) = \beta_q(v,v),
\end{align*}
$$

以及：

$$
\begin{align*}
    q(v+w) &= (v+w)^2 = v^2+vw+wv+w^2\\
    &= q(v)+vw+wv+q(w),
\end{align*}
$$

于是得到$$v^2=\beta_q(v,v)$$及$$vw+wv=2\beta_q(v,w)$$。由于$$\beta_q$$具有双线性和对称性，它形成了几何代数上的内积，记为$$a\cdot b$$。

若$$q(v)=0$$，商去理想$$\mathcal{I}_{q}(V)$$所得结果就是外代数，其中的积则称为外积，记为$$\wedge$$。在外代数中，$$v\wedge v=0$$，并且由于$$(v+w)\wedge(v+w) = v \wedge w + w\wedge v$$，有$$v \wedge w = - w \wedge v$$。

如果我们考虑$$vw- v\cdot w$$，则对任意向量$$v$$，有$$v^2-v\cdot v =0$$，这暗示它正是对应的外代数上的外积。

事实上，$$vw = v\cdot w + v\wedge w$$是另一种几何积的定义。下文中主要使用这一定义。

在进入下一节前，最后考虑一下几何代数的结构。它从张量代数继承了分级结构：$$\mathcal{G}=\bigoplus_{k=0}^{\infty}\mathcal{G}_k$$。其中，$$\mathcal{G}_0$$中的元素就是域中的元素，称为标量。$$\mathcal{G}_1$$中的元素是向量空间$$V$$中的元素，称为向量。定义$$r$$个正交的向量（即彼此反交换）的积为$$r$$-向量，若干$$r$$-向量之和称为$$r$$重向量。所有的$$r$$重向量构成了$$\mathcal{G}_r$$。

$$\mathcal{G}$$中的元素称为多重向量。显然，多重向量是一系列$$r$$重向量的和，并且对于任意$$r$$，$$\langle\rangle_{r}: \mathcal{G} \rightarrow \mathcal{G}_{r}$$将多重向量映射为唯一的$$r$$级分量。特别地，将$$\langle\rangle_0$$记为$$\langle\rangle$$，因为标量最为常用。

一个多重向量可以分解成若干个$$r$$-向量的和：

$$A=\sum_r \langle A \rangle_r$$

# 基本运算

在本节中我们将考虑在欧式空间中的实际运算。上一节中已经展示过几何积的定义：

$$ab = a\cdot b + a\wedge b.$$

因此可以用几何积来表示向量的内积和外积：

$$
\begin{align*}
    a \cdot b = \frac{1}{2}(ab+ba) = b \cdot a, \\
    a \wedge b = \frac{1}{2}(ab-ba) = - b \wedge a.
\end{align*}
$$

其中内积结果为标量，由$$a^2=a\cdot a $$，可以给每个向量分配一个标量值$$\vert a\vert $$。如果$$a^2=\vert a\vert ^2$$，则称该向量的符号为正。若$$a^2=-\vert a\vert ^2$$，则该向量的符号为负。若$$a^2=\vert a\vert ^2=0$$，则称该向量为空向量。在欧式空间中，所有的向量符号都为正。

对于非空向量，可以定义向量的乘法逆：

$$
\begin{align*}
    a^{-1} = \frac{1}{a^2}a = \pm \frac{a}{\vert a\vert ^2}.
\end{align*}
$$

其中正负号取决于向量的符号。显然有$$aa^{-1}=a^{-1}a=1$$。

考虑外积部分的“长度”。注意到：

$$ba = b\cdot a + b\wedge a= a\cdot b - a\wedge b,$$

故：

$$abba = (a\cdot b)^2 - (a\wedge b)^2,$$

在欧式空间中，内积$$a\cdot b = \vert a\vert \vert b\vert \cos(\theta)$$，$$\theta$$为两个向量的夹角，而$$abba=\vert a\vert ^2\vert b\vert ^2$$，于是：

$$(a\wedge b)^2 = -\vert a\vert ^2\vert b\vert ^2\sin^2\theta.$$

上式说明外积既不是标量也不是向量。事实上，两个向量的外积称为$$2$$-向量。由于$$2$$-向量的数值与两个向量张成的面积相同，并且是反对称的，因此它可以表示平面的形状、面积和方向。

我们尚未处理多个向量相乘的情况。为此首先需要定义多个向量的外积。外积的反交换性暗示，$$r$$个向量的外积可以表为：

$$
    a_{1} \wedge a_{2} \wedge \cdots \wedge a_{r}:=\frac{1}{r !} \sum_{\sigma}(\operatorname{sgn} \sigma) a_{\sigma(1)} a_{\sigma(2)} \cdots a_{\sigma(r)},
$$

其中$$\sigma$$是$$1$$到$$r$$的一个变换，$$\operatorname{sgn} \sigma$$表示该变换的奇偶性，$$1$$对应偶变换，$$-1$$对应奇变换。

上节给出了$$r$$-向量的定义。由于向量正交时内积为零，此时外积和几何积相等，因此所有的$$r$$-向量都是$$r$$个向量的外积。并且任意$$r$$个向量的外积也一定可以表示成$$r$$-向量的形式。考虑矩阵$$M$$，其中$$M_{ij}=a_i\cdot a_j$$，则该矩阵是实对称矩阵，因此一定可以被一个正交矩阵对角化，即可以找到一个正交矩阵$$R$$和一组互相正交的向量$${e_i}_{i=1,2,\dots,r}$$，使得$$a_{i}=\sum_{j} R_{i j} e_{j}$$。此时：

$$
\begin{align*}
    a_{1} \wedge a_{2} \wedge \cdots \wedge a_{r} &=\sum_{i, j, \ldots, m} R_{1 i} e_{i} \wedge R_{2 j} e_{j} \wedge \cdots \wedge R_{r m} e_{m} \\
    &=\operatorname{det}(R) e_{1} \wedge e_{2} \wedge \cdots \wedge e_{r}
\end{align*}
$$

而$$\operatorname{det}(R)=\pm 1$$。如果$$\operatorname{det}(R)=-1$$，调换$$e_1$$、$$e_2$$即可。因此$$r$$个向量的外积总是$$r$$-向量。

两个多重向量的积$$C=AB$$也是多重向量。

对于$$k$$重向量$$A = a_1 a_2 \dots a_k$$，通过颠倒相乘的次序，可以得到其反向量$$A^{\dagger} = a_k \dots a_2 a_1$$。二者的乘积为一标量，其值为各向量的长度平方之积，由此可以定义一个$$k$$重向量的长度为$$\vert A\vert ^2 = \vert a_1\vert ^2 \vert a_2\vert ^2 \dots \vert a_k\vert ^2 =\pm AA^{\dagger}$$。

再来考虑$$k$$重向量的逆向量。为了满足$$AA^{-1}=1$$，可以推出：

$$
    A^{-1}=a_k^{-1} \dots a_2^{-1} a_1^{-1} = \pm \frac{A^{\dagger}}{\vert A\vert ^2}.
$$

# 几何意义

几何代数中大部分对象都有其几何意义。上文中我们已经讨论过外积的几何意义，下面我们来看一些更多的例子。

首先考虑镜像。在三维中可以用一张平面来表示镜像，但在高维中平面不只有一个法向量。为了保证适用性，可以用一条轴（即单个向量）来表示镜像：对于任意其他向量，与轴平行的分量（也就是在轴上的投影）改变符号，其余部分保持不变。若用向量$$a$$来表示该轴，则向量$$b$$可以表示为：

$$
    b = b(aa^{-1}) = (ba)a^{-1} = (b\cdot a)a^{-1} + (b \wedge a)a^{-1},
$$

其中第一项$$ (a\cdot b)a^{-1} = \frac{a\cdot b}{\vert a\vert ^2}a $$为$$b$$在$$a$$方向上的投影，因此$$b$$关于$$a$$的镜像应为：

$$ 
    b^{\prime} = - (b\cdot a)a^{-1} + (b \wedge a)a^{-1},
$$

利用外积的反对称性可以进一步地整理上式：

$$
    b^{\prime} = - (a\cdot b)a^{-1} - (a \wedge b)a^{-1} = -aba^{-1}.
$$

这一简洁的形式展示了几何代数的优点之一。

注意到$$a$$和$$a^{-1}$$成对出现，这说明镜像的结果不受$$a$$的数值和方向的影响。

第二个例子是旋转。同样地，这里使用的是在高维中也适用的描述方法，即与某一平面平行的分量旋转，而垂直于平面的分量保持不变。进一步地，旋转可以由连续两次对称构成，其中两次对称的轴的夹角为旋转角度的一半，并且方向与旋转的方向一致。具体的证明如下：

考虑两个向量$$a$$、$$b$$，二者夹角为$$\theta$$，二者的几何积记为$$R=ab$$。任意给定向量$$x$$，考虑$$a$$、$$b$$连续作用在$$x$$上所得的结果$$-a(-bxb^{-1})a^{-1}$$。

首先将$$x$$分解成平行于平面的分量$$x_{\parallel}$$和垂直于平面的分量$$x_{\perp}$$。由于$$x_{\perp}$$同时垂直于$$a$$、$$b$$，故在两次对称中$$x_{\perp}$$均保持不变。因此，只需考虑对称在$$a$$与$$b$$张成的平面上的限制。简单的计算显示：角度为$$\alpha$$的向量沿角度为$$\beta $$的向量对称后的角度为$$2 \beta - \alpha$$。设$$a$$的角度为$$0$$，则$$b$$的角度为$$\theta$$。记$$x$$的初始角度为$$\alpha$$，两次对称后的角度就变成了$$\alpha+2 \theta$$，即$$x$$沿$$b$$到$$a$$的方向旋转了二倍二者的夹角。

$$R=ab$$称为一个旋子。通常来说旋子是若干单位向量的几何积，在这个例子中，就意味着$$RxR^{-1}=(ab)x(ab)^{-1}=(ab)x(ba)$$。将旋转的角度记为$$\theta$$，继续观察旋子$$R$$：

$$
\begin{align*}
    R &= a \cdot b + a \wedge b \\
    &= a\cdot b - b \wedge a \\
    &= \cos\frac{\theta}2 - \sin\frac{\theta}2 E,
\end{align*}
$$

其中\(E=(b \wedge a) / \sin (\theta / 2)\)是单位双向量，满足$$E^2=-1$$，因为\((a\wedge b)^2 = -\sin^2(\theta)\)。于是有：

$$
    R = \exp(-E\theta/2),
$$

即旋子同时表示了旋转的角度、平面的形状、和平面方向。

上面两个例子说明几何代数不仅可以表示几何对象，也可以表示几何对象间的变换。具体而言，对于每一个正交变换$$\underline{A}$$，都能够以以下典范形态表述出来：

$$
\begin{align*}
    \underline{A}: x \rightarrow x^{\prime} = \underline{A}(x) = \pm A^{-1}xA = \pm \frac{A^{\dagger}xA}{\vert A\vert ^2},
\end{align*}
$$

其中$$A$$是一个多重向量，而符号取决于$$A$$的奇偶性。换言之，每一个多重向量都唯一对应一个正交变换，而每一个正交变换也唯一对应一族仅相差正负号和系数的多重向量。因此，单位多重向量$$\hat{A}=A\vert A\vert ^{-1}$$是$$\underline{A}$$的一个双值表示。

向量空间$$R(r,s)$$上的正交变换以及其复合构成了一个群，称为正交变换群，记为$$\operatorname{O}(r,s)$$。正交变换可以用向量来刻画，正交变换的复合也可以用向量的几何积来刻画：

$$
\begin{align*}
    \underline{C}(x) = \underline{B} \underline{A}(x) = \pm B^{-1}(A^{-1}xA)B = \pm (AB)^{-1}x(AB) =\pm C^{-1}xC,
\end{align*}
$$

其中多重向量$$C$$由$$A$$和$$B$$的几何积给出。同样的，单位向量及其积构成了正交变换群的一个双值表示，这个群记为$$\operatorname{Pin}(r,s)$$。

在$$\operatorname{Pin}(r,s)$$中，由偶数个向量相乘形成的多重向量（即偶数重向量）构成一个子群，称为旋转群，记为$$\operatorname{Spin}(r,s)$$。这个群表示的是特殊正交变换群，在三维向量空间中即为旋转构成的子群。