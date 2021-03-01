---
title: "How to prove $\\pi$ is an irrational number?"
subtitle: "Beyond A Level Mathematics"
date: 2021-02-27T13:42:08Z
tags: [Mathematics]
categories: [Beyond A Level Mathematics]
draft: false
---

## How to define number $\pi$

Unlike $\sqrt{2}$, which can be defined as the length of the diagonal of a square with side length $1$, number $\pi$ is related with a more complicated shape - circle. You might know that the perimeter of a circle is $2\pi r$ and its area is $\pi r^2$, so we can try to work out an approximation of $\pi$ with the help of a circle.

![Approximate circle with polygons](/images/BAM/BAM-1/approximate-circle-with-polygons.svg "Approximate circle with polygons")

Note that we can approximate a circle with a regular polygon. When the number of sides increases, you can see the approximation of both perimeter and area being more accurate. When the number of sides tends to infinity, we can say the "polygon" becomes a "circle", and the area of the "polygon" is equal to the area of the "circle". This is a picture of a regular 100-gon, it looks very similar to a circle.

![A regular 100-gon](/images/BAM/BAM-1/regular-100-gon.svg "A regular 100-gon")

And here is the question: given a regular polygon with $n$ sides, what is its area?

![](/images/BAM/BAM-1/regular-decagon-with-triangles.svg)

Note that with a $n$-side polygon, it always consists of $n$ triangles. So the angle $\alpha=\frac{n}{360\degree}$. And the overall area of the polygon is equal the sum of the $n$ triangles.

![](/images/BAM/BAM-1/triangle.svg)

For each triangle its area $S_{\triangle}=\frac{1}{2}r^2\sin(\alpha)$. So the area of the regular polygon $S=n\times S_{\triangle}$.

{{< admonition type=tip title="Rewind" open=true >}}
How to find the area of a triangle through two sides and their angle is covered in A Level Mathematics Student Book 1, Chapter 11 - Triangle geometry, Section 3 - Area of a triangle.
{{< /admonition >}}


$$
\begin{aligned}
    \pi r^2=&\lim_{n\to +\infty}\frac{n}{2}r^2\sin\left(\frac{360\degree}{n}\right)\\\\ 
        \pi=&\lim_{n\to +\infty}\frac{\sin\left(\frac{360\degree}{n}\right)n}{2}
\end{aligned}
$$

With this formula, we can work out the value of $\pi$ quite easily. Use your calculator to check, when $n=1000$, $\pi\approx3.141571983\cdots$, which is correct to $4$ decimal places. When you increase $n$, the result will be more accurate.

> Extension: Use the perimeter of the polygon to work out another formula to approximate number $\pi$. 

## Try to prove it yourself!

> This question is designed to split the original long proof into small and approachable questions. Just take it as a longer STEP question. Through proofing by your own hands, you can better appreciate the beauty of mathematics. You can check your answer by reading the explained proof below, or you can just skip it if you want. But I still strongly recommend you to have a go by yourself!😀

Assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors.

Let $f(x)=\frac{x^n(p-qx)^n}{n!}(n\isin\mathbb{N})$

1. Expand $(p-qx)^n$, use the symbol $\sum$ to write up your answer.

2. Show that $f(x)=\sum\limits_{m=n}^{2n}\frac{a_mx^m}{n!}(a_m,m\isin\mathbb{Z},n\leq m\leq 2n)$. Express $a_m$ in terms of $m,n,p,q$.

Consider the $k^{th}$ derivative $(\frac{ax^m}{n!})^{(k)}(k\isin\mathbb{N})$.

3. When $k=1$, find $(\frac{ax^m}{n!})'$.

4. State the value of $(\frac{ax^m}{n!})^{(k)}$ when $k>m$.

5. When $k=m$, find $(\frac{ax^m}{n!})^{(k)}$.

6. When $k<m$, find $(\frac{ax^m}{n!})^{(k)}$.

7. Show that $f^{(k)}(0)\isin\mathbb{Z}$ for all $k\isin\mathbb{Z}$.

Consider function $f(\pi-x)$.

8. Show that $f(x)=\frac{x^nq^n(\pi-x)^n}{n!}$.

9. Show that $f(x)=f(\pi-x)$.

10. Show that $f^{(k)}(\pi)=(-1)^{k}f^{(k)}(0)\isin\mathbb{Z}$

Let $F(x)=f(x)-f^{(2)}(x)+f^{(4)}(x)-f^{(6)}(x)+...+(-1)^nf^{(2n)}(x)$.

11. Show that $F(x)+F''(x)=f(x)$.

12. Show that $\frac{\operatorname{d}}{\operatorname{d}x}[F'(x)\sin(x)-F(x)\cos(x)]=f(x)\sin(x)$.

13. Show that $A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x=F(0)+F(\pi)\isin\mathbb{Z}$.

When $0<x<\pi$, given that

- If $f(x)>0$ then $\int_a ^b f(x) \operatorname{d}x>0$
- If $0<f(x)<g(x)$ then $0<\int_a ^b f(x) \operatorname{d}x<\int_a ^b g(x) \operatorname{d}x$
- $\lim\limits_{n\rightarrow+\infin}\frac{\pi^{n+1}p^n}{n!}=0$

14. Show $A>0$.

15. Show $A<1$.

16. Hence, or otherwise, find the contradiction and show that $\pi$ is an irrational number.

## How to prove $\pi$ is an irrational number

We use proof by contradiction to prove that $\pi$ is an irrational number.

So at the first step, we assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors. This step is exactly the same when you try to proof $\sqrt{2}$ is irrational. But unlike $\sqrt{2}$, which you can simply square it to get a nice integer $2$, the number $\pi$ is actually a lot harder to work with. So if the next few steps does not make a lot of sense for you, just keep on reading, and you will get there at the end!

Next, we construct a function $f(x)=\frac{x^n(p-qx)^n}{n!}(n\isin\mathbb{N})$. Note that the term $(p-qx)^n$ can be expanded by using the binomial expansion.

{{< admonition type=tip title="Rewind" open=true >}}
The binomial expansion is covered in A Level Mathematics Student Book 1, Chapter 9 - Binomial expansion, Section 1 - The binomial theorem.
{{< /admonition >}}


$$
\begin{aligned}
    (p-qx)^n=&\sum_{k=0} ^{n}\binom{n}{k}p^{n-k}(-qx)^{k}\\\\ 
            =&\sum_{k=0} ^{n}\binom{n}{k}p^{n-k}(-q)^{k}x^{k}
\end{aligned}
$$

So that we can substitute this result back to function $f(x)$.

$$
\begin{aligned}
    f(x)=&\frac{x^n(p-qx)^n}{n!}(n\isin\mathbb{N})\\\\ 
        =&\frac{x^n\sum\limits_{k=0}^{n}\binom{n}{k}p^{n-k}(-q)^{k}x^{k}}{n!}\\\\ 
        =&\sum_{k=0} ^{n}\frac{\binom{n}{k}p^{n-k}(-q)^{k}x^{k+n}}{n!}
\end{aligned}
$$

We let $m=k+n$, as $0\leq k\leq n$, $m$ has range $n\leq m\leq 2n$. So $f(x)$ can be transformed into a slightly nicer form.

$$
\begin{aligned}
    f(x)=&\sum_{m=n} ^{2n}\frac{\binom{n}{m-n}p^{2n-m}(-q)^{m-n}x^{m}}{n!}\\\\ 
        =&\sum_{m=n}^{2n}\frac{a_mx^m}{n!}
\end{aligned}
$$

Where

$$a_m=\binom{n}{m-n}p^{2n-m}(-q)^{m-n}\isin \mathbb{Z}$$

Why we say this is a better form? It is because that **the coefficient $a_m$ before $x^m$ is an integer**. This property will be used later.

Now, let's consider each individual term in this sum: $\left(\frac{ax^m}{n!}\right)$. What about its $k$th derivative $\left(\frac{ax^m}{n!}\right)^{(k)}$? It turns out that based on the different value of $k$, there are three different cases.

- When $k>m$, it is obvious that $\left(\frac{ax^m}{n!}\right)^{(k)}=0$.

- When $k=m$, $\left(\frac{ax^m}{n!}\right)^{(k)}=\frac{m!a}{n!}$.

- When $k<m$, $\left(\frac{ax^m}{n!}\right)^{(k)}=\frac{m(m-1)\cdots(m-k+1)ax^{m-k+1}}{n!}$.

Now if we consider the $k$th derivative of $f(0)$.

- When $k>m$, $f^{(k)}(0)=0+0+\cdots+0=0$ is an integer.

- When $k=m$, $f^{(k)}(0)=\sum\limits_{m=n}^{2n}\frac{m!a_m}{n!}$. And because $m\geq n$, so $\frac{m!}{n!}$ is an integer. We know that $a_m$ is an integer as well. So that $f^{(k)}(0)$ is an integer.

- When $k<m$, $f^{(k)}(0)=0+0+\cdots+0=0$ is an integer.

**So for any $k\isin\mathbb{Z}$, $f^{(k)}(0)\isin\mathbb{Z}$.**


Given that $$

Because $f(x)\sin(x)>0$, we can say $\int_0 ^\pi f(x)\sin(x)\operatorname{d}x=A>0$. 


This result is not so obvious, but to proof it strictly need something beyond the A Level syllabus. For now,  you can think of a function which is always positive in its domain, so the area between the function and the x-axis is always positive, so its definite integral is positive.

{{< admonition type=info title="Beyond A Level Syllabus" open=false >}}

The strict proof of this result contains topics beyond the A Level syllabus. You can just skip it if it does not make any sense to you.
$$f(x) > 0 \rightarrow\int_a ^b f(x) \operatorname{d}x >0$$

Note that the inverse proposition is not true. Think about $f(x)=\sin(x)$:

$$\int_0 ^{\frac{3\pi}{2}}\sin(x)\operatorname{d}x=1>0$$

But $\sin(\frac{3\pi}{2})=-1<0$.

{{< /admonition >}}

Note that when $0<x<\pi$, we have $f(x)=\frac{x^n(p-qx)^n}{n!}<\frac{\pi^np^n}{n!}$ and $\sin(x)\leq 1$. So,

$$A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x<\int_0 ^\pi \frac{\pi^np^n}{n!}\times 1\operatorname{d}x$$

Show that $\int_0 ^\pi \frac{\pi^np^n}{n!}\times 1\operatorname{d}x=\frac{\pi^{n+1}p^n}{n!}$.

Note that

$$\lim\limits_{n\rightarrow+\infin}\frac{\pi^{n+1}p^n}{n!}=0$$

{{< admonition type=info title="Beyond A Level Syllabus" open=false >}}

$$\lim_{n\rightarrow+\infin}\frac{a^n}{n!}=0(a\isin\mathbb{R})$$

{{< /admonition >}}

So when $n$ is sufficient large, we have

$$A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x<\int_0 ^\pi \frac{\pi^np^n}{n!}\times 1\operatorname{d}x=\frac{\pi^{n+1}p^n}{n!}<1$$

So finally, $A$ satisfies

$$0<A<1$$

But in $(14)$, you have proved that $A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x=F(0)+F(\pi)\isin\mathbb{Z}$, we all know that there is no integer between 0 and 1, here the contradiction arises. So our assumption is wrong.

{{< admonition type=quote title="Assumption at the beginning" open=true >}}
Assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors.
{{< /admonition >}}

And thus we have proved that $\pi$ is irrational and cannot be written as $\frac{p}{q}$.

## Historical researches

TODO

## Extension problem: How about number $e$?