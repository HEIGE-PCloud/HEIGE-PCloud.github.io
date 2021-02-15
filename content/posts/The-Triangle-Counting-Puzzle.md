---
title: The Triangle Counting Puzzle
date: 2020-10-23T22:04:09Z
tags: [Mathematics]
draft: false
---


# The beginning of the story

> A fun journey to an integer sequence.

Everything started from the Puzzle 137 from [www.puzzleoftheweek.com](http://www.puzzleoftheweek.com). I was not interested in those kindergarten-ish questions at first, but found this one is quite fun at the end.

<!-- more -->

<iframe src="https://drive.google.com/file/d/1AeL1S_7PyV-OGhbslY4hsn9xAp02785O/preview" width="640" height="480"></iframe>

# Starter

Counting the number of the triangles is pretty easy, and I recommend this puzzle to your any 3 year old cousins to "develop their early mathematical thinking".

There are 27 triangles when the height is 4:

$$
27=\underbrace{\underbrace{(1+2+3+4)}_ {height=1}+\underbrace{(1+2+3)}_ {height=2}+(1+2)+(1)}_ {triangle\ facing\ up}+\underbrace{(1+2+3)+(1)}_ {triangle\ facing\ down}
$$

Suppose the largest triangle has the height $n$, it is obvious that the largest triangle facing up has the height $n$ as well.

So the number of triangles facing up satisfies the equation:

$$\sum_{i=1}^{n} \sum_{j=1}^{i} j$$

However, the number of triangles facing down is a little bit different. Because the down triangles cannot utilize the top space of the large triangle, the max size is not fixed. By looking at the different cases when $n$ is an odd or an even number, we can get this equation for triangles facing down:

$$
\begin{cases}
\sum_{i=1}^{\frac{n-1}{2}} \sum_{j=1}^{2i}j \ (n\ is\ odd) \\\\ 
\sum_{i=1}^{(\frac{n}{2})} \sum_{j=1}^{2i-1}j \ (n\ is\ even) \\\\ 
\end{cases}
$$

Hence we have got the entire equation to solve the problem:

$$
\begin{cases}
\sum_{i=1}^{n} \sum_{j=1}^{i} j + \sum_{i=1}^{\frac{n-1}{2}} \sum_{j=1}^{2i}j \ (n\ is\ odd) \\\\ 
\sum_{i=1}^{n} \sum_{j=1}^{i} j + \sum_{i=1}^{(\frac{n}{2})} \sum_{j=1}^{2i-1}j \ (n\ is\ even) \\\\ 
\end{cases}
$$

Which **is** ugly, but it is actually working. If you know a little bit about programming, this is just a nested `for` loop.

The equation is still complex, though you can use some program or calculator to help you solve this just like the Python code bellow.

```python
def Triangle_Counting_Puzzle(n: int) -> int:
    x = 0
    if n % 2 == 1:
        for i in range(1, n + 1):
            for j in range(1, i + 1):
                x += j
        for i in range(1, int((n - 1) / 2) + 1):
            for j in range(1, 2 * i + 1):
                x += j
    else:
        for i in range(1, n + 1):
            for j in range(1, i + 1):
                x += j
        for i in range(1, int(n / 2) + 1):
            for j in range(1, 2 * i):
                x += j
    return x

n = int(input())
print(Triangle_Counting_Puzzle(n))
```

The result for $n=100$ is $256275$. We can save this for checking in the future.

# Deal with the double sum

There are three double sum in our equation, and actually, we can transform all of them into polynomials, here is my approach.

## For triangles facing up

For the first one:

$$
\begin{aligned}
&\sum_{i=1}^{n} \sum_{j=1}^{i} j\\\\ 
=&\frac{1}{2}(1+n)n+\frac{1}{2}(1+n-1)(n-1)+\cdots+\frac{1}{2}(1+1)\times1\\\\ 
=&\frac{1}{2}\left[(n+1)n+n(n-1)+\cdots+2\times1\right]\\\\ 
=&\frac{1}{2}\left[n^2+n+(n-1)^2+(n-1)+\cdots+1^2+1\right]\\\\ 
=&\frac{1}{2}\left[(1^2+2^2+\cdots+n^2)+(1+2+\cdots+n)\right]
\end{aligned}
$$

We come to two nice equations which we can handle.

$$
1^2+2^2+\cdots+n^2=\frac{1}{6}n(n+1)(2n+1)\tag{1}
$$
$$
1+2+\cdots+n=\frac{1}{2}(1+n)n\tag{2}
$$

I think you must have heard about the genius [Gauss' story](https://www.nctm.org/Publications/Teaching-Children-Mathematics/Blog/The-Story-of-Gauss/#) about working out the sum of an arithmetic sequence. So I will only prove the $(1)$ about the sum of a sequence of consecutive integer squares. It is quite an important result.

There are multiple approaches towards this, the most common one is to prove by induction. This is actually a pretty good chance to practice the ability of proving by induction, so you may try this by yourself. But proving by induction has a serious issue - you need to know or at least guess out the conclusion before you can prove it, which is very hard in this case if you don't know the conclusion before. So I am going to introduce an alternative approach.

#### Lemma 1 $\sum_{i=1}^{n}i^2=\frac{1}{6}n(n+1)(2n+1)$

Consider $1^3,2^3,...n^3,(n+1)^3$

$$
\begin{cases}
1^3&=(0+1)^3=0^3+3\times0^2\times1+3\times0\times1^2+1^3\\\\ 
2^3&=(1+1)^3=1^3+3\times1^2\times1+3\times1\times1^2+1^3\\\\ 
&\cdots\\\\ 
n^3&=(n-1+1)^3=(n-1)^3+3\times(n-1))^2\times1+3\times(n-1))\times1^2+1^3\\\\ 
(n+1)^3&=(n+1)^3=n^3+3\times n^2\times1+3\times n\times1^2+1^3\\\\ 
\end{cases}
$$

$$
\begin{aligned}
\sum left&= \sum right\\\\ 
\sum_{i=1}^{n+1}i^3&=\sum_{i=0}^{n}i^3+3\sum_{i=0}^{n}i^2+\sum_{i=0}^{n}i+n+1\\\\ 
3\sum_{i=0}^{n}i^2&=(n+1)^3-\frac{3}{2}n(n+1)-(n+1)\\\\ 
3\sum_{i=0}^{n}i^2&=n(n+1)(n+\frac{1}{2})\\\\ 
\sum_{i=1}^{n}i^2&=\frac{1}{6}n(n+1)(2n+1)
\end{aligned}
$$

So

$$
\begin{aligned}
&\sum_{i=1}^{n} \sum_{j=1}^{i} j\\\\ 
=&\frac{1}{2}\left[(1^2+2^2+\cdots+n^2)+(1+2+\cdots+n)\right]\\\\ 
=&\frac{1}{2}\left[\frac{1}{6}n(n+1)(2n+1)+\frac{1}{2}n(n+1)\right]\\\\ 
=&\frac{1}{6}n(n+1)(n+2)
\end{aligned}
$$

## For triangles facing down

### When $n$ is odd

Similarly

$$
\begin{aligned}
&\sum_{i=1}^{\frac{n-1}{2}} \sum_{j=1}^{2i}j\\\\ 
&=\frac{1}{2}\left[(2^2+4^2+\cdots+(n-1)^2)+(2+4+\cdots+(n-1))\right]
\end{aligned}
$$

So we only need to find out the value of $2^2+4^2+\cdots+(n-1)^2$ in this case.

### When $n$ is even

$$
\begin{aligned}
&\sum_{i=1}^{\frac{n}{2}} \sum_{j=1}^{2i-1}j\\\\ 
&=\frac{1}{2}\left[(1^2+3^2+\cdots+(n-1)^2)+(1+3+\cdots+(n-1))\right]
\end{aligned}
$$

We can see that there is a strong relationship between the two cases. Actually, we only need to prove one of the double sum and the other one can be deduced easily.

#### Lemma 2 $\sum_{i=1}^{\frac{n}{2}}(2i-1)^2=\frac{1}{6}n(n-1)(n+1)\ (n\ is\ even)$

$$
\begin{aligned}
&1^2+3^2+\cdots+(n-1)^2\\\\ 
=&(2\times1-1)^2+(2\times2-1)^2+\cdots+(2\times\frac{n}{2}-1)^2\\\\ 
=&4(1^2+2^2+\cdots+(\frac{n}{2})^2)-4(1+2+...+\frac{n}{2})+\frac{n}{2}\\\\ 
=&\frac{1}{3}n(\frac{n}{2}+1)(n+1)-n(\frac{n}{2}+1)+\frac{n}{2}\\\\ 
=&\frac{1}{6}n(n-1)(n+1)\\\\ 
\end{aligned}
$$

#### Lemma 3 $\sum_{i=1}^{\frac{n-1}{2}}(2i)^2=\frac{1}{6}n(n-1)(n+1)\ (n\ is\ odd)$

$$
\begin{aligned}
&2^2+4^2+\cdots+(n-1)^2\\\\ 
=&1^2+2^2+\cdots+n^2-(1^2+3^2+\cdots+n^2)\\\\ 
=&\sum_{i=1}^{n}i^2-\sum_{i=1}^{\frac{n+1}{2}}(2i-1)^2\\\\ 
=&\frac{1}{6}n(n+1)(2n+1)-\frac{1}{6}n(n+1)(n+2)\\\\ 
=&\frac{1}{6}n(n+1)(n-1)
\end{aligned}
$$

So when $n$ is odd

$$
\begin{aligned}
&\sum_{i=1}^{\frac{n-1}{2}} \sum_{j=1}^{2i}j\\\\ 
=&\frac{1}{2}(\frac{1}{6}n(n+1)(n-1)+\frac{1}{4}(n+1)(n-1))\\\\ 
=&\frac{1}{24}(n-1)(n+1)(2n+3)\\\\ 
\end{aligned}
$$

$$
\begin{aligned}
&\sum_{i=1}^{n} \sum_{j=1}^{i} j + \sum_{i=1}^{\frac{n-1}{2}} \sum_{j=1}^{2i}j\\\\ 
=&\frac{1}{6}n(n+1)(n+2)+\frac{1}{24}(n-1)(n+1)(2n+3)\\\\ 
=&\frac{1}{8}(n+1)(2n^2+3n-1)\\\\ 
\end{aligned}
$$

And when $n$ is even

$$
\begin{aligned}
&\sum_{i=1}^{\frac{n}{2}} \sum_{j=1}^{2i-1}j\\\\ 
=&\frac{1}{2}(\frac{1}{6}n(n+1)(n-1)+\frac{1}{4}n^2)\\\\ 
=&\frac{1}{24}n(2n-1)(n+2)\\\\ 
\end{aligned}
$$

$$
\begin{aligned}
&\sum_{i=1}^{n} \sum_{j=1}^{i} j + \sum_{i=1}^{\frac{n}{2}} \sum_{j=1}^{2i-1}j\\\\ 
&=\frac{1}{6}n(n+1)(n+2)+\frac{1}{24}n(2n-1)(n+2)\\\\ 
&=\frac{1}{8}n(n+2)(2n+1)\\\\ 
\end{aligned}
$$

## Final result

After a lot of calculations on some long equations, we finally get our elegant result.

$$
\begin{cases}
\frac{1}{8}(n+1)(2n^2+3n-1)\ n\ is\ odd\\\\ 
\frac{1}{8}n(n+2)(2n+1)\ n\ is\ even\\\\ 
\end{cases}
$$

And since

$$
\begin{aligned}
\frac{1}{8}n(n+2)(2n+1)&=\frac{1}{8}(2n^3+5n^2+2n)\\\\ 
\frac{1}{8}(n+1)(2n^2+3n-1)&=\frac{1}{8}(2n^3+5n^2+2n-1)\\\\ 
&=\frac{1}{8}n(n+2)(2n+1)-\frac{1}{8}\\\\ 
&=\lfloor \frac{1}{8}n(n+2)(2n+1) \rfloor
\end{aligned}
$$

So the height $n$ relates to the number of triangles $x$ satisfy:

$$x=\lfloor \frac{1}{8}n(n+2)(2n+1)\rfloor$$

When $n=100$, the number is $256275$, which is the same as the result from our "double sum" Python program.

# The ending and more

By searching the sequence $1,5,13,27,\cdots$ on [oeis.org](https://oeis.org), you can find the sequence [A002717](https://oeis.org/A002717), which is exactly what we have proved today. There are some interesting information on that page about some other research on the sequence and the triangle counting problem.

An alternative approach: [Ralph E. Edwards et al., Problem 889: A well-known problem, Math. Mag., 47 (1974), 289-292.](https://www.jstor.org/stable/2688056?seq=5#metadata_info_tab_contents)

Some history and other fancy proves: [M. E. Larsen, The eternal triangle - a history of a counting problem, College Math. J., 20 (1989), 370-392.](http://web.math.ku.dk/~mel/mel.pdf)

By comparison, my approach did not actually explain the double sum's correctness very strictly. When transforming the double sum into the polynomial, it is also more straightforward and "brute force" instead of looking for more properties from the triangles.

But overall, it is still a nice and enjoyable journey and here are some further questions which you can think about:

1. How to prove the correctness of the double sum strictly?
2. We have proved $\sum_{i=1}^{n}i^2$, how about $\sum_{i=1}^{n}i^3$ or $\sum_{i=1}^{n}i^k$?
3. How about $\sum_{i=1}^{n}\frac{1}{i}$?