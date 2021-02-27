---
title: "How to prove $\\pi$ is an irrational number?"
date: 2021-02-27T13:42:08Z
draft: false
---

## Try to prove it yourself!

> This question is designed to split the original long proof into small and approachable questions. Just take it as a longer STEP question. Through proofing by your own hands, you can better appreciate the beauty of mathematics. You can check your answer by reading the explained proof below, or you can just skip it if you want. But I still strongly recommend you to have a go by yourself!😀

Assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors.

Let $f(x)=\frac{x^n(p-qx)^n}{n!}(n\isin\mathbf{N})$

1. Expand $(p-qx)^n$, use the symbol $\sum$ to write up your answer.

2. Show that $f(x)=\sum\limits_{m=n}^{2n}\frac{a_mx^m}{n!}(a_m,m\isin\mathbf{Z},n\leq m\leq 2n)$. Express $a_m$ in terms of $m,n,p,q$.

Consider the $k^{th}$ derivative $(\frac{ax^m}{n!})^{(k)}(k\isin\mathbf{N})$.

3. When $k=1$, find $(\frac{ax^m}{n!})'$.

4. State the value of $(\frac{ax^m}{n!})^{(k)}$ when $k>m$.

5. When $k=m$, find $(\frac{ax^m}{n!})^{(k)}$.

6. When $k<m$, find $(\frac{ax^m}{n!})^{(k)}$.

7. Show that $f^{(k)}(0)\isin\mathbf{Z}$ for all $k\isin\mathbf{Z}$.

Consider function $f(\pi-x)$.

8. Show that $f(x)=\frac{x^nq^n(\pi-x)^n}{n!}$.

9. Show that $f(x)=f(\pi-x)$.

10. Show that $f^{(k)}(\pi)=(-1)^{k}f^{(k)}(0)\isin\mathbf{Z}$

Let $F(x)=f(x)-f^{(2)}(x)+f^{(4)}(x)-f^{(6)}(x)+...+(-1)^nf^{(2n)}(x)$.

11. Show that $F(x)+F''(x)=f(x)$.

12. Show that $\frac{\operatorname{d}}{\operatorname{d}x}[F'(x)\sin(x)-F(x)\cos(x)]=f(x)\sin(x)$.

13. Show that $A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x=F(0)+F(\pi)\isin\mathbf{Z}$.

When $0<x<\pi$, given that

- If $f(x)>0$ then $\int_a ^b f(x) \operatorname{d}x>0$
- If $0<f(x)<g(x)$ then $0<\int_a ^b f(x) \operatorname{d}x<\int_a ^b g(x) \operatorname{d}x$
- $\lim\limits_{n\rightarrow+\infin}\frac{\pi^{n+1}p^n}{n!}=0$

14. Show $A>0$.

15. Show $A<1$.

16. Hence, or otherwise, find the contradiction and show that $\pi$ is an irrational number.

## TODO

Similar to the process of proving $\sqrt{2}$ is not rational, we use proof by contradiction to prove that $\pi$ is an irrational number.

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

$$\lim_{n\rightarrow+\infin}\frac{a^n}{n!}=0(a\isin\mathbf{R})$$

{{< /admonition >}}

So when $n$ is sufficient large, we have

$$A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x<\int_0 ^\pi \frac{\pi^np^n}{n!}\times 1\operatorname{d}x=\frac{\pi^{n+1}p^n}{n!}<1$$

So finally, $A$ satisfies

$$0<A<1$$

But in $(14)$, you have proved that $A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x=F(0)+F(\pi)\isin\mathbf{Z}$, we all know that there is no integer between 0 and 1, here the contradiction arises. So our assumption is wrong.

{{< admonition type=quote title="Assumption at the beginning" open=true >}}
Assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors.
{{< /admonition >}}

And thus we have proved that $\pi$ is irrational and cannot be written as $\frac{p}{q}$.
