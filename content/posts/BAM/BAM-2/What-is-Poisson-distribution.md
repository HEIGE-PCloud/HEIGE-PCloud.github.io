---
title: "What is Poisson distribution?"
subtitle: "Beyond A Level Mathematics #2"
draft: false
date: 2021-03-24T16:44:25Z

tags: [Mathematics]
categories: [Beyond A Level Mathematics]

hiddenFromHomePage: false
hiddenFromSearch: false
---

You have learnt Poisson distribution in AS Further Statistics but you may still have many questions. Where does that complex probability mass function come from? Why it has the same variance and expectation?

This post will answer all these questions.

<!--more-->

## What is Poisson distribution

>**Example**
>
>Recordable accidents occur in a factory at an average rate of seven every year, independently of each other. Find the probability that in a given year exactly three recordable accidents occurred.

This is the same example in the textbook (Worked Example 3.1). I would like to use it as a good example to explain how we develop the Poisson distribution. So let's consider it without any knowledge you have known about Poisson distribution. What we know is that seven accidents happen each year on average. What we need to find is the probability that in a given year, exact three accidents occurred.

The answer is not that straightforward. But we can add a further condition to make it a little bit easier. We **assume** that "there is a maximum of 1 accident happen every month."

Here is a possible configuration that three accidents happen this year.

| Jan | Feb | Mar | Apr | May | Jun | Jul | Aug | Sep | Oct | Nov | Dec |
|-----|-----|-----|-----|-----|-----|-----|-------|---|-----|-----|-----|
| ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |

Now the model can fit into the binomial distribution we have learnt before because

- The number of trials is fixed, twelve months
- Each outcome can be classified as either "Accident" or "Safe"
- Accidents are independent of each other
- The probability of an accident is the same every month

What is the probability for each month? We have the average for twelve months is seven, so for one month, it is $\frac{7}{12}$.

So let's set up the binomial distribution:

$$X\sim\operatorname{B}\left(12, \frac{7}{12}\right)$$

Now we can calculate the probability of having three accidents every year **under our assumption**.

$$P(X=3)=\binom{12}{3}\left(\frac{7}{12}\right)^{3}\left(1-\frac{7}{12}\right)^{9}\approx0.0165$$

But this answer is not quite correct for the original question. We manually add a condition that there is only one accident each month, which might not be the case. It is possible to have more accidents each month so the probability we calculated is a lot less than the real value.

A possible configuration we missed:

| Jan | Feb | Mar | Apr | May | Jun | Jul | Aug | Sep | Oct | Nov | Dec |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌❌❌ | ✅ | ✅ | ✅ |

{{< admonition type=quote title="Sad Sad September" open=false >}}
{{< youtube 032Vq9J8b7c >}}
{{< /admonition >}}
But if there needs to have more than one accidents each month, the binomial distribution does not work any more, because there are more than 2 outcomes each month (no accident, one accident, two accidents, ...). And the solution is quite simple, we can divide the time into smaller intervals, for example, we divide a year into 365 intervals for 365 days instead of only 12 intervals. And the probability under this condition is $P(X=3)=\binom{365}{3}\frac{7}{365}^{3}(1-\frac{7}{365})^{362}\approx0.0512$ which is a great improvement than the twelve months configuration. And actually, it is quite close to the correct answer $0.0521$. However, the same issue occurs again, if you are unlucky enough, you can still have more than one accident every day, in which case the binomial distribution ignores those probabilities and result in a smaller overall probability. So we need to keep dividing, divide the time into **infinite** pieces.

Let's generalize the question a little bit. For a fixed period (one year in this example), we divide it into $n$ periods. With an average rate $\lambda$ (7 accidents on average), the probability of having an accident in each period is $\frac{\lambda}{n}$. We need to divide the time into infinite periods, so we let $n\to+\infty$.

$$P(X=x)=\lim_{n\to+\infty}\binom{n}{x}\left(\frac{\lambda}{n}\right)^{x}\left(1-\frac{\lambda}{n}\right)^{n-x}$$

We have got a very complex limit to solve, let's see what we can do here. The first thing we can do is expand the binomial coefficient into multiplications.

$$P(X=x)=\lim_{n\to+\infty}\frac{n(n-1)(n-2)\cdots(n-x+1)}{x!}\cdot\frac{\lambda^{x}}{n^{x}}\cdot\left(1-\frac{\lambda}{n}\right)^{n-x}$$

Notice that $x$ and $\lambda$ are constants, so we can take them out from the limit.

$$P(X=x)=\frac{\lambda^{x}}{x!}\cdot\lim_{n\to+\infty}\frac{n}{n}\cdot\frac{n-1}{n}\cdots\frac{n-x+1}{n}\left(1-\frac{\lambda}{n}\right)^{-x}\left(1-\frac{\lambda}{n}\right)^{n}$$

Notice that the limit can be split into a multiplication of two limits.

$$P(X=x)=\frac{\lambda^{x}}{x!}\cdot\lim_{n\to+\infty}\frac{n}{n}\cdot\frac{n-1}{n}\cdots\frac{n-x+1}{n}\left(1-\frac{\lambda}{n}\right)^{-x}\cdot\lim_{n\to+\infty}\left(1-\frac{\lambda}{n}\right)^{n}$$

Let's look into each part individually. For the first limit

$$
\begin{aligned}
   &\lim_{n\to+\infty}\frac{n}{n}\cdot\frac{n-1}{n}\cdots\frac{n-x+1}{n}\left(1-\frac{\lambda}{n}\right)^{-x} \\\\ 
  =&\lim_{n\to+\infty}\frac{n}{n}\cdot\frac{n-1}{n}\cdots\frac{n-x+1}{n}\left(\frac{n-\lambda}{n}\right)^{-x} \\\\ 
  =&\lim_{n\to+\infty}\frac{n}{n}\cdot\frac{n-1}{n}\cdots\frac{n-x+1}{n}\left(\frac{n}{n-\lambda}\right)^{x} \\\\ 
  =&\lim_{n\to+\infty}\frac{n}{n}\cdot\frac{n-1}{n}\cdots\frac{n-x+1}{n}\frac{n^{x}}{(n-\lambda)^{x}} \\\\ 
  =&\lim_{n\to+\infty}\frac{\overbrace{n\cdot(n-1)\cdots(n-x+1)}^{\text{x terms}}}{(n-\lambda)^x} \\\\ 
  =&1
\end{aligned}
$$

For the second limit, things get a little more difficult. It connects to the number $e$.

The definition of $e$ is

$$e=\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^{n}\approx2.71828\ldots$$

In our case, we can transform our second limit to get some help from this.

$$
\begin{aligned}
 &\lim_{n\to+\infty}\left(1-\frac{\lambda}{n}\right)^{n} \\\\ 
=&\lim_{n\to\infty}\left(1+\left(\frac{1}{n\cdot\left(-\frac{1}{\lambda}\right)}\right)\right)^{n} \\\\ 
=&\lim_{n\to\infty}\left(1+\left(\frac{1}{n\cdot\left(-\frac{1}{\lambda}\right)}\right)\right)^{n\cdot(-\frac{1}{\lambda})\cdot(-\lambda)} \\\\ 
=&\left(\lim_{n\to\infty}\left(1+\left(\frac{1}{n\cdot\left(-\frac{1}{\lambda}\right)}\right)\right)^{n\cdot(-\frac{1}{\lambda})}\right)^{-\lambda} \\\\ 
&\text{Let } t=-\frac{n}{\lambda} \text{. Notice that } n\to\infty\text{, }t\to\infty\text{.} \\\\ 
=&\left(\lim_{t\to\infty}\left(1+\frac{1}{t}\right)^{t}\right)^{-\lambda} \\\\ 
=&e^{-\lambda}
\end{aligned}
$$

Now, let's come back to the original limit.

$$
\begin{aligned}
P(X=x)=&\frac{\lambda^{x}}{x!}\cdot\left[\lim_{n\to+\infty}\frac{n}{n}\cdot\frac{n-1}{n}\cdots\frac{n-x+1}{n}\left(1-\frac{\lambda}{n}\right)^{-x}\right]\cdot\left[\lim_{n\to+\infty}\left(1-\frac{\lambda}{n}\right)^{n}\right] \\\\ 
       =&\frac{\lambda^{x}}{x!}\cdot1\cdot e^{-\lambda} \\\\ 
       =&\frac{\lambda^{x}e^{-\lambda}}{x!} 
\end{aligned}
$$

There is only one constant we need to input, $\lambda$, the average rate for the event to happen during a certain period. Here we have the Poisson distribution to model this type of questions.

$$X\sim\operatorname{Po}(\lambda)$$

Where the PMF is

$$\operatorname{P}(X=x)=\frac{\lambda^{x}e^{-\lambda}}{x!}$$

So back to the original question, when $x=3$

$$\operatorname{P}(x=3)=\frac{7^3\cdot e^{-7}}{3!}\approx0.0521$$

## Why Poisson distribution has the same expectation and variance

$$\operatorname{P}(X=x)=\frac{\lambda^{x}e^{-\lambda}}{x!}$$

### Try to prove it yourself

1. Calculate the Maclaurin series of $e^x$.
2. Show that for $X\sim\operatorname{Po}(\lambda)$, $\operatorname{E}(X)=\lambda$.
3. Show that for $X\sim\operatorname{Po}(\lambda)$, $\operatorname{E}(X)=\operatorname{Var}(X)$.

### Maclaurin series

{{< admonition type=tip title="Rewind" open=true >}}
The Maclaurin series is covered in A Level Further Mathematics Pure Core Student Book 2, Chapter 8 - Application of calculus, Section 1 - Maclaurin series.
{{< /admonition >}}

The Maclaurin series of a function $\operatorname{f}(x)$ is given by

$$\operatorname{f}(x)=\operatorname{f}(0)+\operatorname{f}'(0)x+\frac{\operatorname{f}''(0)}{2!}x^{2}+\cdots+\frac{\operatorname{f}^{(r)}(0)}{r!}x^{r}+\cdots$$

So for $\operatorname{f}(x)=e^{x}$

$$
\begin{aligned}
  e^{x}=&e^{0}+e^{0}x+\frac{e^{0}x^2}{2!}+\cdots+\frac{e^{0}x^{r}}{r!}+\cdots \\\\ 
       =&1+x+\frac{x}{2!}+\cdots+\frac{x^r}{r!}+\cdots \\\\ 
       =&\sum_{n=0}^{\infty}\frac{x^n}{n!}
\end{aligned}
$$

We will use this series later.


### Expectation

The expectation for a discrete probability distribution is

$$\operatorname{E}(X)=\sum_{i}x_{i}p_{i}$$

To work out the expectation of Poisson distribution, we substitute the PMF into the formulae

$$
\begin{aligned}
  \operatorname{E}(X)=&\sum_{x=0}^{\infty}x\times\operatorname{P}(X=x) \\\\ 
  =&\sum_{x=0}^{\infty}x\times\frac{\lambda^{x}e^{-\lambda}}{x!} \\\\ 
  =&\lambda e^{-\lambda}\sum_{x=1}^{\infty}\frac{\lambda^{x-1}}{(x-1)!} \\\\ 
   &\text{Let }i=x-1\text{.} \\\\ 
  =&\lambda e^{-\lambda}\sum_{i=0}^{\infty}\frac{\lambda^{i}}{i!} \\\\ 
   &\text{Notice }\sum_{i=0}^{\infty}\frac{\lambda^{i}}{i!}=e^{\lambda}\text{.} \\\\ 
  =&\lambda e^{-\lambda}e^{\lambda} \\\\ 
  =&\lambda
\end{aligned}
$$

### Variance

$$\operatorname{Var}(X)=\operatorname{E}(X^{2})-(\operatorname{E}(X))^{2}$$

We need the expression for $\operatorname{E}(X^2)$ before we can work out the expression for variance.

$$
\begin{aligned}
  \operatorname{E}(X^{2})=&\sum_{x=0}^{\infty}x^{2}\times\operatorname{P}(X=x) \\\\ 
  =&\sum_{x=0}^{\infty}x^{2}\times\frac{\lambda^{x}e^{-\lambda}}{x!} \\\\ 
  =&\lambda e^{-\lambda}\sum_{x=1}^{\infty}\frac{x}{(x-1)!}\times\lambda^{x-1} \\\\ 
  =&\lambda e^{-\lambda}\sum_{x=1}^{\infty}\frac{(x-1)+1}{(x-1)!}\times\lambda^{x-1} \\\\ 
  =&\lambda e^{-\lambda}\left(\sum_{x=1}^{\infty}\frac{1}{(x-2)!}\times\lambda^{x-1}+\frac{1}{(x-1)!}\times\lambda^{x-1}\right) \\\\ 
  =&\lambda e^{-\lambda} \left(\lambda\sum_{x=2}^{\infty}\frac{\lambda^{x-2}}{(x-2)!}+\sum_{x=1}^{\infty}\frac{\lambda^{x-1}}{(x-1)!}\right) \\\\ 
   &\text{The same trick here.} \\\\ 
  =&\lambda e^{-\lambda}(\lambda e^{\lambda}+e^{\lambda}) \\\\ 
  =&\lambda^{2}+\lambda
\end{aligned}
$$

And now we have the expression for variance, which is the same as the expectation. Amazing!

$$
\begin{aligned}
    \operatorname{Var}(X)=&\operatorname{E}(X^2)-(\operatorname{E}(X))^{2} \\\\ 
    =&\lambda^{2}+\lambda-\lambda^{2} \\\\ 
    =&\lambda \\\\ 
    =&\operatorname{E}(x)
\end{aligned}
$$

## Extension

### History

Obviously, Poisson distribution is called "Poisson distribution" is because someone named "Poisson" introduced it. His full name is Siméon Denis Poisson (1781–1840) and the distribution was published together with his probability theory in his work *Recherches sur la probabilité des jugements en matière criminelle et en matière civile*(1837).

And here is the [link](https://gallica.bnf.fr/ark:/12148/bpt6k110193z/f218.image) to his original work.

### Parameter estimation

You can estimate the value of the parameter $\lambda$ from a sample. It is a little more complicated. Here is a [link](http://cnx.org/content/m13500/latest/?collection=col10343/latest) about parameter estimation.