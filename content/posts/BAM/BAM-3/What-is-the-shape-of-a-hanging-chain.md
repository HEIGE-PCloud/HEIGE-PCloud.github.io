---
title: "What is the shape of a hanging chain?"
draft: true
date: 2021-06-10T08:31:19+01:00

tags: [Mathematics]
categories: [Beyond A Level Mathematics]

hiddenFromHomePage: false
hiddenFromSearch: false
---

You may think that the graph of $\cosh{x}$ looks like a parabola, but it is slightly flatter. It is called a catenary, which is the shape formed by a hanging chain.

<!--more-->

## Catenary

{{< image src="/images/BAM/BAM-3/catenary.svg" caption="Catenary">}}

Assume we have a light, thin and inextensible chain hangs stationary in the air. Let $A$ be the lowest point of the chain. We randomly select another point $B$ and let's consider the chain $AB$. There are 3 forces acting on chain $AB$, a horizontal force $F$ to the left acting on point $A$, a force $T$ acting on point $B$ along its tangent and the gravity of the chain $AB$. Since chain $AB$ is hanging stationary in the air, the resultant force is zero. Hence we have a simultaneous equation.

$$
\begin{dcases}
   F=T\cos(\theta) \\\\ 
   G=T\sin(\theta)
\end{dcases}
$$


Hence we have

$$
\begin{aligned}
    \tan(\theta)&=\frac{G}{F} \\\\ 
    &=\frac{mg}{F} \\\\ 
    &=\frac{\rho lg}{F} \\\\ 
    &=\frac{l}{a} \left(\text{where a }=\frac{F}{\rho g}\right) \\\\ 
    y'=\tan(\theta)&=\frac{l}{a} 
\end{aligned}
$$

$m$ is the mass of the chain, $\rho$ is the density of the chain, $l$ is the length of the chain, $g$ is the gravitational acceleration. We can measure the value of $F$, $\rho$ and $g$, so we can determine the value of $a$ as it is a constant.

Now we have a differential equation.

$$y'=\frac{l}{a}$$

What is the length of the chain $AB$ then?

### The length of a curve

Consider a very short length of our curve $\mathrm{d}c$, as it is very short, we can approximate it to a striaght line.

By the Pythagoras's Theorem, we can have

$$\mathrm{d}c^2=\mathrm{d}x^2+\mathrm{d}y^2$$

Divide $\mathrm{d}x^2$ on both side

$$\left(\frac{\mathrm{d}c}{\mathrm{d}x}\right)^2=1+\left(\frac{\mathrm{d}y}{\mathrm{d}x}\right)^2$$

Then we square root bot side

$$\frac{\mathrm{d}c}{\mathrm{d}x}=\sqrt{1+\left(\frac{\mathrm{d}y}{\mathrm{d}x}\right)^2}$$

Finally, we integrate both side to get our result

$$\int_a^b1\\ \mathrm{d}c=\int_a^b\sqrt{1+\left(\frac{\mathrm{d}y}{\mathrm{d}x}\right)^2}\mathrm{d}x$$

So the length of the curve between point $a$ and $b$ is $c_{ab}=\int_a^b\sqrt{1+\left(\frac{\mathrm{d}y}{\mathrm{d}x}\right)^2}\mathrm{d}x$.

### The shape of the hanging chain

We have $y'=\frac{l}{a}$ above, and now we know how to calculate the length of the chain.

$$l=\int_{0}^{x}\sqrt{1+y'^{2}}\mathrm{d}x$$

So

$$y'=\frac{1}{a}\int_{0}^{x}\sqrt{1+y'^{2}}\mathrm{d}x$$

Next, we diffierent both sides of the equation

$$y''=\frac{1}{a}\left(\int_{0}^{x}\sqrt{1+y'^{2}}\mathrm{d}x\right)'$$

What is $\left(\int_{0}^{x}\sqrt{1+y'^{2}}\mathrm{d}x\right)'$ then?

Let's consider a more general case. What is the value of $\left(\int_{0}^{x}f(x)\mathrm{d}x\right)'$?

Let $g'(x)=f(x)$
$$
\begin{aligned}
    \int_{0}^{x}f(x)\mathrm{d}x&=g(x)-g(0) \\\\ 
    \left(\int_{0}^{x}f(x)\mathrm{d}x\right)'&=g'(x) - 0 \\\\ 
    &=f(x)
\end{aligned}
$$

So
$$
\begin{aligned}
    y''=&\frac{1}{a}\left(\int_{0}^{x}\sqrt{1+y'^{2}}\mathrm{d}x\right)' \\\\ 
    =&\frac{1}{a}\sqrt{1+y'^{2}}
\end{aligned}
$$

---

$$y''=\frac{1}{a}\sqrt{1+y'^{2}}$$
$$y(0)=a$$
$$y'(0)=0$$
$$y'=p$$
$$\frac{\mathrm{d}p}{\mathrm{d}x}=\frac{1}{a}\sqrt{1+p^2}$$
$$\frac{\mathrm{d}p}{\sqrt{1+p^2}}=\frac{\mathrm{d}x}{a}$$