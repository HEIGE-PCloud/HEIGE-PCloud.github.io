---
title: "How to prove $\\pi$ is an irrational number?"
subtitle: "Beyond A Level Mathematics"
date: 2021-02-27T13:42:08Z
tags: [Mathematics]
categories: [Beyond A Level Mathematics]
draft: false
---

## Preface

You have leaned how to prove $\sqrt{2}$ is an irrational number, how about another famous number $\pi$? The number $\pi$ is very useful in our daily life. You need it to calculate the perimeter and area of a circle, you need it in trigonometry and geometry as well. You might have heard that just like $\sqrt{2}$, $\pi$ is an irrational number too. But how can you prove this? Let's start our journey from an easier question: How to define number $\pi$?   

{{< admonition type=tip title="Rewind" open=true >}}
How to prove $\sqrt{2}$ is an irrational number is covered in A Level Mathematics Student Book 2, Chapter 1 - Proof and mathematical communication, Section 2 - Proof by contradiction.
{{< /admonition >}}

## How to define number $\pi$

Unlike $\sqrt{2}$, which can be defined as the length of the diagonal of a square with side length $1$, the number $\pi$ is related to a more complicated shape - circle. You might know that the perimeter of a circle is $2\pi r$ and its area is $\pi r^2$, so we can try to work out the value of $\pi$ with the help of a circle.

### Define by the area of a circle

![Approximate circle with polygons](/images/BAM/BAM-1/approximate-circle-with-polygons.svg "Approximate circle with polygons")

Note that we can approximate a circle with a regular polygon. When the number of sides increases, you can see the approximation of both perimeter and area being more accurate. When the number of sides tends to infinity, we can say the "polygon" becomes a "circle", and the area of the "polygon" is equal to the area of the "circle". This is a picture of a regular 100-gon, it looks very similar to a circle.

![A regular 100-gon](/images/BAM/BAM-1/regular-100-gon.svg "A regular 100-gon")

And here is the question: given a regular polygon with $n$ sides, what is its area?

![A $n$-side polygon always  consists of $n$ triangles](/images/BAM/BAM-1/regular-decagon-with-triangles.svg "A $n$-side polygon always  consists of $n$ triangles")

Note that with a $n$-side polygon, it always consists of $n$ triangles. So the angle $\alpha=\frac{n}{360\degree}$. And the overall area of the polygon is equal to the sum of the area of the $n$ triangles.

![](/images/BAM/BAM-1/triangle.svg "$S_{\triangle}=\frac{1}{2}r^2\sin(\alpha)$")

For each triangle, its area $S_{\triangle}=\frac{1}{2}r^2\sin(\alpha)$. So the area of the regular polygon $S=n\times S_{\triangle}=\frac{n}{2}r^2\sin(\frac{360}{n})$.

{{< admonition type=tip title="Rewind" open=true >}}
How to find the area of a triangle through two sides and their angle is covered in A Level Mathematics Student Book 1, Chapter 11 - Triangle geometry, Section 3 - Area of a triangle.
{{< /admonition >}}

So now we let the number of sides $n$ tends to infinity to get the exact value of $\pi$.

$$
\begin{aligned}
    \pi r^2=&\lim_{n\to +\infty}\frac{n}{2}r^2\sin\left(\frac{360\degree}{n}\right)\\\\ 
        \pi=&\lim_{n\to +\infty}\frac{\sin\left(\frac{360\degree}{n}\right)n}{2}
\end{aligned}
$$

With this formula, we can work out the value of $\pi$ quite easily. Use your calculator to check, when $n=1000$, $\pi\approx3.141571983\cdots$, which is correct to $4$ decimal places. When you increase $n$, the result will be more accurate.

{{< admonition type=question title="Extension question" open=true >}}
Use the perimeter of the polygon to work out another formula of number $\pi$.
{{< /admonition >}}

### Define by the equation of a circle

We can put the circle in a coordinate axis, here is a unit circle with equation $x^2+y^2=1$. Let's see how this can help us.

![](/images/BAM/BAM-1/unit-circle.svg "$x^2+y^2=1$")

{{< admonition type=tip title="Rewind" open=true >}}
The equation of a circle is covered in A Level Mathematics Student Book 1, Chapter 6 - Coordinate geometry, Section 4 - equation of a circle.
{{< /admonition >}}

The circle has a equation of $x^2+y^2=1$, if we only take the positive values of $y$, we can obtain the equation of the upper semicircle.

$$
\begin{aligned}
    x^2+y^2=&1\\\\ 
    y^2=&1-x^2\\\\ 
    y=&\sqrt{1-x^2}
\end{aligned}
$$

We can work out the area of the upper semicircle by integrating its equation. Because its area is half of the entire circle, so now the area of the circle can be calculated as well.

$$\pi r^2=2\int_{-1}^{1}\sqrt{1-x^2}\operatorname{d}x$$

And since it is an unit circle, its radius is $1$. So we can have another equation of $\pi$.

$$\pi=2\int_{-1}^{1}\sqrt{1-x^2}\operatorname{d}x$$

You can input this expression into your calculator, and a very accurate value of $\pi$ will be produced. If you want to calculate it by hand somehow, you can use the trapezium rule.

{{< admonition type=tip title="Rewind" open=true >}}
The trapezium rule is covered in A Level Mathematics Student Book 2, Chapter 15 - Numerical integration, Section 2 - The trapezium rule.
{{< /admonition >}}

### Rational or Irrational?

You can see that there are several different ways to define and work out the value of the number $\pi$, but these methods dose not seem to help proving its irrationality at all. Actually, whether the number $\pi$ is rational is a very hard question. Around 250 BC, the ancient Greeks have already had an algorithm to approximate $\pi$ with arbitrary accuracy. But not until 2000 years later, in 1761, the first proof of $\pi$ is an irrational number is proposed by Johann Heinrich Lambert.

Lambert's proof is based on continued fraction expansion and is quite complex. Today, I would like to introduce another proof proposed by Ivan Niven published in June 1947. It is only one page and you can read it here.

[A simple proof that $\pi$ is irrational](https://projecteuclid.org/journals/bulletin-of-the-american-mathematical-society-new-series/volume-53/issue-6/A-simple-proof-that-pi-is-irrational/bams/1183510788.full)

But the actual ideas behind it is way more than one page, but don't worry, I will guide you through it. I have designed an approachable question so that you can first try to prove it by yourself before reading the explained proof. Hope you enjoy it.

## Try to prove it yourself!

> This question is designed to split the original long proof into small and approachable questions. Just take it as a longer STEP question. Through proving by your own hands, you can better appreciate the beauty of mathematics. You can check your answer by reading the explained proof below, or you can just skip it if you want. But I still strongly recommend you to have a go by yourself!😀

Assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors.

Let $f(x)=\frac{x^n(p-qx)^n}{n!}(n\isin\natnums)$

1. Expand $(p-qx)^n$, use the symbol $\sum$ to write up your answer.

2. Show that $f(x)=\sum\limits_{m=n}^{2n}\frac{a_mx^m}{n!}(a_m,m\isin\Z,n\leq m\leq 2n)$. Express $a_m$ in terms of $m,n,p,q$.

Consider the $k^{th}$ derivative $(\frac{ax^m}{n!})^{(k)}(k\isin\natnums)$.

3. When $k=1$, find $(\frac{ax^m}{n!})'$.

4. State the value of $(\frac{ax^m}{n!})^{(k)}$ when $k>m$.

5. When $k=m$, find $(\frac{ax^m}{n!})^{(k)}$.

6. When $k<m$, find $(\frac{ax^m}{n!})^{(k)}$.

7. Show that $f^{(k)}(0)\isin\Z$ for all $k\isin\natnums$.

Consider function $f(\pi-x)$.

8. Show that $f(x)=\frac{x^nq^n(\pi-x)^n}{n!}$.

9. Show that $f(x)=f(\pi-x)$.

10. Show that $f^{(k)}(\pi)=(-1)^{k}f^{(k)}(0)\isin\Z$

Let $F(x)=f(x)-f^{(2)}(x)+f^{(4)}(x)-f^{(6)}(x)+\cdots+(-1)^nf^{(2n)}(x)$.

11. Show that $F(x)+F''(x)=f(x)$.

12. Show that $\frac{\operatorname{d}}{\operatorname{d}x}[F'(x)\sin(x)-F(x)\cos(x)]=f(x)\sin(x)$.

13. Show that $A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x=F(0)+F(\pi)\isin\Z$.

When $0<x<\pi$, given that

- If $f(x)>0$ then $\int_a ^b f(x) \operatorname{d}x>0$
- If $0<f(x)<g(x)$ then $0<\int_a ^b f(x) \operatorname{d}x<\int_a ^b g(x) \operatorname{d}x$
- $\lim\limits_{n\to+\infin}\frac{\pi^{n+1}p^n}{n!}=0$

14. Show $A>0$.

15. Show $A<1$.

16. Hence, or otherwise, find the contradiction and show that $\pi$ is an irrational number.

## How to prove $\pi$ is an irrational number

We use proof by contradiction to prove that $\pi$ is an irrational number.

### Prove that $A$ is an integer

So at the first step, we assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors. This step is exactly the same when you try to proof $\sqrt{2}$ is irrational. But unlike $\sqrt{2}$, which you can simply square it to get a nice integer $2$, the number $\pi$ is actually a lot harder to work with. So if the next few steps does not make a lot of sense for you, just keep on reading, and you will get there at the end!

Next, we construct a function $f(x)=\frac{x^n(p-qx)^n}{n!}(n\isin\natnums)$. Note that the term $(p-qx)^n$ can be expanded by using the binomial expansion.

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
    f(x)=&\frac{x^n(p-qx)^n}{n!}(n\isin\natnums)\\\\ 
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

$$a_m=\binom{n}{m-n}p^{2n-m}(-q)^{m-n}\isin \Z$$

Why we say this is a better form? It is because that **the coefficient $a_m$ before $x^m$ is an integer**. This property will be used later.

Now, let's consider each individual term in this sum: $\left(\frac{ax^m}{n!}\right)$. What about its $k$th derivative $\left(\frac{ax^m}{n!}\right)^{(k)}$? It turns out that based on the different value of $k$, there are three different cases.

- When $k>m$, it is obvious that $\left(\frac{ax^m}{n!}\right)^{(k)}=0$.

- When $k=m$, $\left(\frac{ax^m}{n!}\right)^{(k)}=\frac{m!a}{n!}$.

- When $k<m$, $\left(\frac{ax^m}{n!}\right)^{(k)}=\frac{m(m-1)\cdots(m-k+1)ax^{m-k+1}}{n!}$.

Now if we consider the $k$th derivative of $f(0)$.

- When $k>m$, $f^{(k)}(0)=0+0+\cdots+0=0$ is an integer.

- When $k=m$, $f^{(k)}(0)=\sum\limits_{m=n}^{2n}\frac{m!a_m}{n!}$. And because $m\geq n$, so $\frac{m!}{n!}$ is an integer. We know that $a_m$ is an integer as well. So that $f^{(k)}(0)$ is an integer.

- When $k<m$, $f^{(k)}(0)=0+0+\cdots+0=0$ is an integer.

**So for any $k\isin\natnums$, $f^{(k)}(0)\isin\Z$.**

Now let's consider function $f(\pi-x)$. First, we can simply transform the origin function into a more helpful shape.

$$f(x)=\frac{x^n(p-qx)^n}{n!}=\frac{x^nq^n(\pi-x)^n}{n!}$$

And we find that 

$$f(\pi-x)=\frac{(\pi-x)^nq^n(\pi-\pi+x)^n}{n!}=\frac{x^nq^n(\pi-x)^n}{n!}=f(x)$$

Now we calculate the $k$th derivative of both $f(x)$ and $f(\pi-x)$:

$$
\begin{aligned}
    f(x)=&f(\pi-x)\\\\ 
    f^{(k)}(x)=&(-1)^{k}f^{(k)}(\pi-x)
\end{aligned}
$$

So $f^{(k)}(0)=(-1)^{k}f^{(k)}(\pi)$. As we have already known that $f^{(k)}(0)\isin\Z$, then **we can deduce that for any $k\isin\natnums$, $f^{(k)}(\pi)\isin\Z$**.

> Let's pause for a while at this point. You might feel quite messy now, thinking "Why we do this?", "Where does $f(x)$ come from?". Let's make it clear, all we have done by now are two things:
> 1. We **define** $f(x)=\frac{x^n(p-qx)^n}{n!}(n\isin\natnums)$.
> 2. We have **proved** that $f^{(k)}(0)\isin\Z$, $f^{(k)}(\pi)\isin\Z$ for any $k\isin\natnums$. This helps us to construct the contradiction later on.

Now, let's keep moving on. We define a new function $F(x)$.

$$F(x)=f(x)-f^{(2)}(x)+f^{(4)}(x)-f^{(6)}(x)+…+(-1)^nf^{(2n)}(x)$$

The function $F(x)$ has some interesting properties.

$$
\begin{aligned}
    F(x)+F''(x)=f(x)-&f^{(2)}(x)+f^{(4)}(x)-f^{(6)}(x)+…+(-1)^nf^{(2n)}(x)\\\\ 
    +&f^{(2)}(x)-f^{(4)}(x)+f^{(6)}(x)+…-(-1)^{n}f^{(2n)}(x)+(-1)^{n+2}f^{(2n+2)}(x)
\end{aligned}
$$

$$F(x)+F''(x)=f(x)+(-1)^{n+2}f^{(2n+2)}(x)$$

As what we have proved before, because $2n+2>m$, so $(-1)^{n+2}f^{(2n+2)}(x)=0$. So we have

$$F(x)+F''(x)=f(x)$$

Now we consider the number $A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x$. To work out this integral, we shall do it inversely by considering this derivative $\frac{\operatorname{d}}{\operatorname{d}x}[F'(x)\sin(x)-F(x)\cos(x)]$.

$$
\begin{aligned}
    \frac{\operatorname{d}}{\operatorname{d}x}[F'(x)\sin(x)-F(x)\cos(x)]=&F''(x)\sin(x)+F'(x)\cos(x)-F'(x)\cos(x)+F(x)\sin(x)\\\\ 
    =&F''(x)\sin(x)+F(x)\sin(x)\\\\ 
    =&\sin(x)(F(x)+F''(x))\\\\ 
    =&f(x)\sin(x)
\end{aligned}
$$

Now we have found the primitive of $f(x)\sin(x)$. So we can work out the definite integral.

$$
\begin{aligned}
    \int_0 ^\pi f(x)\sin(x)\operatorname{d}x=&\left[F'(x)\sin(x)-F(x)\cos(x)\right]_{0}^{\pi}\\\\ 
    =&F'(\pi)\sin(\pi)-F(\pi)\cos(\pi)-F'(0)\sin(0)+F(0)\cos(0)
    =&F(0)+F(\pi)
\end{aligned}
$$

$$
\begin{aligned}
    F(0)=&\sum_{i=0}^{n}(-1)^{i}f^{(2i)}(0)\\\\ 
    F(\pi)=&\sum_{i=0}^{n}(-1)^{i}f^{(2i)}(\pi)\\\\ 
    \because& f^{(k)}(0)\isin\Z\\\\ 
    \because& f^{(k)}(\pi)\isin\Z\\\\ 
    \therefore& F(0), F(\pi)\isin\Z\\\\ 
    \therefore& A=F(0)+F(\pi)\isin\Z
\end{aligned}
$$

Now we have shown that $A$ is an integer. And then we will try to show that $A$ cannot be an integer, so the contradiction is constructed.

### Prove that $A$ is not an integer

Before we can do that, there are three axioms we need to prove in advance:
1. If $f(x)>0$ then $\int_a ^b f(x) \operatorname{d}x>0$
2. If $0<f(x)<g(x)$ then $0<\int_a ^b f(x) \operatorname{d}x<\int_a ^b g(x) \operatorname{d}x$
3. $\lim\limits_{n\to+\infin}\frac{\pi^{n+1}p^n}{n!}=0$

Unluckily, to proof them strictly need something beyond the A Level syllabus. You can read the strict proof bellow if you are interested, or you can just take them for now and keep moving on.

#### Axiom 1

We need to prove for $a<b$, if $f(x)>0$ then $\int_a ^b f(x) \operatorname{d}x>0$.

{{< admonition type=info title="Beyond A Level Syllabus" open=false >}}

The strict proof of this result contains topics beyond the A Level syllabus. You can just skip it if it does not make any sense to you. Or you can think that when the value of a function is always bigger than $0$, then the area between the function and the x-axis will always be positive.

To prove it strictly, a good approach is to go back to the definition of the definite integral.

Suppose $f(x)$ is a bounded function with domain $[a,b]$. Randomly choose a partition of interval $[a,b]$, we call it

$$P:a=x_0<x_1<\cdots<x_n=b$$

Randomly choose point $\xi_i\isin[x_{i-1},x_i]$. The length of the interval $[x_{i-1},x_i]$ is $\Delta x_i=x_i-x_{i-1}$, let $\lambda=\max\limits_{1\leq i\leq n}(\Delta x_i)$. When $\lambda\to0$, the limit

$$\lim_{\lambda\to0}\sum_{i=0}^{n}f(\xi_i)\Delta x_i=\int_{a}^{b}f(x)\operatorname{d}x$$

And now we have $f(x)>0$, $\Delta x_i>0$. So

$$\int_{a}^{b}f(x)\operatorname{d}x=\lim_{\lambda\to0}\sum_{i=0}^{n}f(\xi_i)\Delta x_i>0$$

Axiom 1 is proved.

Note that the inverse proposition is not true. Think about $f(x)=\sin(x)$

$$\int_0 ^{\frac{3\pi}{2}}\sin(x)\operatorname{d}x=1>0$$

But $\sin(\frac{3\pi}{2})=-1<0$.

{{< /admonition >}}


#### Axiom 2

We need to prove if $0<f(x)<g(x)$ then $0<\int_a ^b f(x) \operatorname{d}x<\int_a ^b g(x) \operatorname{d}x$. With the help of Axiom 1, this part is relatively easy.

Let $h(x)=g(x)-f(x)>0$, based on Axiom 1,

$$
\begin{aligned}
    \int_{a}^{b}h(x)\operatorname{d}x&>0\\\\ 
    \int_{a}^{b}g(x)-f(x)\operatorname{d}x&>0\\\\ 
    \int_{a}^{b}g(x)\operatorname{d}x-\int_{a}^{b}f(x)\operatorname{d}x&>0\\\\ 
    0<\int_a ^b f(x) \operatorname{d}x&<\int_a ^b g(x) \operatorname{d}x
\end{aligned}
$$

Axiom 2 is proved.

#### Axiom 3

We need to prove $\lim\limits_{n\to+\infin}\frac{a^n}{n!}=0(a\isin\R^{+})$.

{{< admonition type=info title="Beyond A Level Syllabus" open=false >}}

Let $t\isin\natnums$ satisfies $t-1\leq a<t$, so $\frac{a}{t}<1$.

$$\lim_{n\to+\infty}\frac{a^n}{n}=\lim_{n\to+\infty}\frac{a}{n}\frac{a}{n-1}\cdots\frac{a}{t}\frac{a}{t-1}\cdots\frac{a}{2}\frac{a}{1}$$

Let $K=\frac{a}{t-1}\cdots\frac{a}{2}\frac{a}{1}$ is a constant.

$$0<\lim_{n\to+\infty}\frac{a}{n}\frac{a}{n-1}\cdots\frac{a}{t}<\lim_{n\to+\infty}\left(\frac{a}{t}\right)^{n-t+1}=0$$

Based on the squeeze theorem, we have

$$\lim\limits_{n\to+\infin}\frac{a^n}{n!}=K\times\lim_{n\to+\infty}\frac{a}{n}\frac{a}{n-1}\cdots\frac{a}{t}=K\times0=0$$

Axiom 3 is proved.

{{< /admonition >}}

#### Determine the range of $A$

When $0<x<\pi$, $x^n>0$, $q^n>0$, $(\pi-x)^n>0$, $n!>0$, $\sin(x)>0$ so $f(x)\sin(x)>0$. Based on Axiom 1, we can say

$$A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x>0$$

Note that when $0<x<\pi$, we have $f(x)=\frac{x^n(p-qx)^n}{n!}<\frac{\pi^np^n}{n!}$ and $\sin(x)\leq 1$.

$$f(x)\sin(x)<\frac{\pi^np^n}{n!}\times1$$

And based on Axiom 2, we have

$$A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x<\int_0 ^\pi \frac{\pi^np^n}{n!}\times 1\operatorname{d}x=\frac{\pi^{n+1}p^n}{n!}$$

$$\therefore A<\frac{\pi^{n+1}p^n}{n!}$$

And based on Axiom 3, we have

$$\lim\limits_{n\to+\infin}\frac{\pi^{n+1}p^n}{n!}=\pi\times\lim\limits_{n\to+\infin}\frac{(\pi p)^n}{n!}=\pi\times0=0$$

So we can say $\exist N>0,\forall n(n>N), \frac{\pi^{n+1}p^n}{n!}<1$, which means when $n$ gets sufficiently large, $\frac{\pi^{n+1}p^n}{n!}$ will smaller than $1$. And now we have 

$$A<\frac{\pi^{n+1}p^n}{n!}<1$$

So finally, the range of $A$ is

$$0<A<1$$

### Construct the contradiction

We have proved that $A=\int_0 ^\pi f(x)\sin(x)\operatorname{d}x=F(0)+F(\pi)\isin\Z$ and $A$ has the range $0<A<1$. We all know that there is no integer between $0$ and $1$, here the contradiction arises, which means our assumption is wrong.

{{< admonition type=quote title="Assumption at the beginning" open=true >}}
Assume that $\pi=\frac{p}{q}$ where $p$ and $q$ are integers with no common factors.
{{< /admonition >}}

And thus we have proved that $\pi$ is irrational and cannot be written as $\frac{p}{q}$.

## Further reading

1. [***Numbers***](https://books.google.com/books?id=Z53SBwAAQBAJ&pg=PA123): This book explains more ways of introducing the number $\pi$.
2. [***A simple proof that $\pi$ is irrational***](https://projecteuclid.org/journals/bulletin-of-the-american-mathematical-society-new-series/volume-53/issue-6/A-simple-proof-that-pi-is-irrational/bams/1183510788.full): The original proof from Ivan Niven.
3. [***Proof that $\pi$ is irrational***](https://en.wikipedia.org/wiki/Proof_that_%CF%80_is_irrational): This page summarizes some other ways of proving $\pi$ is irrational.

## Extension problem: How about the number $e$?

You have learned something about the number $e=2.71828$ when you solve logarithms and exponential models questions.

{{< admonition type=tip title="Rewind" open=true >}}
The natural logarithm is covered in A Level Mathematics Student Book 1, Chapter 7 - Logarithms.

The exponential models is covered in A Level Mathematics Student Book 1, Chapter 8 - Exponential models.
{{< /admonition >}}

The number $e$ is another irrational number. How can you prove it?

Or more interestingly, consider $\sqrt{e}$, $e^2$, $e^e$, $e^{\pi}$, are they irrational numbers as well?