---
title: UKMOG 2020 Solution
date: 2020-10-28T17:26:50Z
tags: [Mathematics]
draft: false
---


## Preface

The United Kingdom Mathematical Olympiad for Girls is, well apparently, according to its name, a math competition for girls specifically. Which also means it is a little bit easier than the BMO Round 1, so it is a good opportunity for me to **have an attempt of writing a serious solution** for such competitions. I may keep posting my own solutions to some BMO or IMO questions, or may not.

<!-- more -->

This is the original paper for the [UKMOG 2020](https://bmos.ukmt.org.uk/home/ukmog-2020.pdf).

<!-- {% pdf https://bmos.ukmt.org.uk/home/ukmog-2020-solutions.pdf pdf %} -->

And there is an [official solution](https://bmos.ukmt.org.uk/home/ukmog-2020-solutions.pdf).

<!-- {% pdf https://bmos.ukmt.org.uk/home/ukmog-2020-solutions.pdf pdf %} -->

If there are any conflicts between my solutions and the official one, please take the official one. After all, at the end of the day, it is not me who will mark your paper.

## Problems and solutions

### Problem 1

#### Task 1(a)

Let $p$ and $q$ be different prime numbers, and let $a=p^2$, $b=pq$ and $c=p^3q$. Which of $ab$, $bc$ and $ca$ is a square number? (1 mark)

#### Solution 1(a)

$ab=p^3q$, $bc=p^4q^2=(p^2q)^2$, $ca=p^5q$. So obvious $bc$ is a square number.

A free mark. Yummy~

#### Task 1(b)

Halle would like to place nine of the ten integers $1,2,\cdots,9,10$ into the cell of a $3\times3$ grid in such a way that the three numbers within each row are written in increasing order from left to right and the product of the three numbers within each row is equal to a square number.

Give an example showing that Halle's task is possible. (4 marks)

#### Solution 1(b)

| $1$ | $2$ | $3$ | $4$   | $5$ | $6$        | $7$ | $8$   | $9$   | $10$       |
|:-------:|---------|---------|-----------|---------|----------------|---------|-----------|-----------|-------------|
| $1$ | $2$ | $3$ | $2^2$ | $5$ | $2\times3$ | $7$ | $2^3$ | $3^2$ | $2\times5$ |

First we find all the prime factors for the number from one to ten. Notice we need to fill a $3\times3$ grid, which indicates we should select nine numbers, but now we have ten. So the first step is to abandon one unappropriated number. Since we need the product to be a square number, the number of the prime factors in the product must be an even number. But there is only one $7$ in $1,2,\cdots,10$, so $7$ cannot be selected into the grid.

Similarly, consider the number of $5$: there are only two $5$ - one from $5$ and the other from $10$, so number $5$ and $10$ must in the same row. There is a prime factor $2$ in $10$, so there should be another one or three $2$ to form a square number. So there is only two cases for rows contain $5$ and $10$ 


|   |   |   |
|---|---|---|
| $2$ | $5$ | $10$ |
| ? | ? | ? |
| ? | ? | ? |

|   |   |   |
|---|---|---|
| $5$ | $8$ | $10$ |
| ? | ? | ? |
| ? | ? | ? |

In the first situation, consider $1$. In the row contains $1$, the product of the following numbers have to be a square number. With the numbers left $2,3,4,6,9$, it is easy to find that only $4\times9$ gives us a square number $36$ and the other 3 number left will go into the final row. So now we can obtain one example of the grid:

|         |         |          |
|---------|---------|----------|
| $2$ | $5$ | $10$ |
| $1$ | $4$ | $9$ |
| $3$ | $6$ | $8$ |

#### Task 1(c)

How many different grids can Hale produce? (5 marks)

#### Solution 1(c)

In the second situation, following by the same method, we can obtain the other grid.

|         |         |          |
|---------|---------|----------|
| $5$ | $8$ | $10$ |
| $1$ | $4$ | $9$ |
| $2$ | $3$ | $6$ |

In each grid, the column cannot swap since they have to in an increasing order, but there are no restrictions to the rows. So in each grid there are $P^{3}_{3}=3! =6$ ways to arrange the rows. And in total there are $6\times2=12$ different grids.

#### Comments

It is a really attemptable problem on basic algebra and combinatorics, just try to find some basic properties from the numbers themselves will allow you solve it directly.

### Problem 2

Twelve points, four of which are vertices, lie on the perimeter of a square. The distance between adjacent points is one unit. Some of the points have been connected by straight lines. $B$ is the intersection of two of those lines, as shown in the diagram.

#### Task 2(a)

Find the ratio $AB:AC$. Give your answer in its simplest form. (3 marks)

#### Solution 2(a)

$\sqrt{2^2+3^2}=\sqrt{4+9}=\sqrt{13}$, so $AB:BC:CA=2:3:\sqrt{13}$.

#### Task 2(b)

Find the area of the shaded region. (7 marks)

#### Solution 2(b)

$$
\begin{aligned}
\because& AC=2,AB:BC:CA=2:3:\sqrt{13}\\\\ 
\therefore& AB=\frac{4}{\sqrt{13}},BC=\frac{6}{\sqrt{13}}\\\\ 
\therefore& Area=(\sqrt{13}-\frac{4}{\sqrt{13}}-\frac{6}{\sqrt{13}})^2=\frac{9}{13}
\end{aligned}
$$

#### Comments

Really simple trigonometry.

### Problem 3

#### Task 3(a)

The expression $10xy-2x+5y-1$ factorizes as $(ax+b)(cy+d)$ where $a,b,c,d$ are integers and $a>0$. Find the values of $a,b,c,d$. (1 mark)

#### Solution 3(a)

$$
\begin{aligned}
10xy-2x+5y-1&=(2x+1)(5y-1)\\\\ 
\end{aligned}
$$

$$
\begin{cases}
a&=2\\\\ 
b&=1\\\\ 
c&=5\\\\ 
d&=-1\\\\ 
\end{cases}
$$

#### Task 3(b)

Using the factorization above and considering factor pairs of $99$, find all integer pairs $(x,y)$ such that $10xy-2x+5y=100$. (4 marks)

#### Solution 3(b)

$$
\begin{aligned}
10xy-2x+5y-1&=99\\\\ 
(2x+1)(5y-1)&=99
\end{aligned}
$$

Notice that $2x+1$ and $5y-1$ has to be odd numbers and $5y$ needs to be divided by 5. So we have $5y-1=99,9,-1,-11$.

So for$(x,y)$, we have 4 solutions: $(0,20),(5,2),(-50,0),(-5,-2)$.

#### Task 3(c)

Find all integer pairs $(x,y)$ such that $10xy-2x+5y=100000001$. (5 marks)

#### Solution 3(c)

$$
\begin{aligned}
10xy-2x+5y&=100000001\\\\ 
(2x+1)(5y-1)&=100000000
\end{aligned}
$$

Notice that $2x+1$ cannot divided by 2 and $5y-1$ cannot divided by 5. $100000000=10^8=2^8\times5^8$. In this case, $(2x+1)=5^8$, $(5y-1)=2^8$ or $(2x+1)=-5^8$, $(5y-1)=-2^8$.

Finally, we have one integer solution: $y=-\frac{255}{5}=-51$

#### Comments

Simple algebra and number theory. A lot of zeros...

### Problem 4

Daniel and Alessia each have eight boxes labelled $1$ to $8$, To start, each of them has $n$ balloons, all in their box $1$.

#### Task 4(a)

Alessia is playing a game with her balloons. She may make the following move:

- Choose a box $k$ containing at least two balloons. Pop a single balloon in box $k$ and then move another balloon from box $k$ to box $k+1$.

Find the value of $n$ such that, after a finite number of moves, all that remains is a single balloon in box $8$. (2 marks)

#### Solution 4(a)

$1$ balloon at $8$, so there needs $2$ balloons at $7$, $4$ balloons at $6$... $2^7=128$ balloons at $1$.

#### Task 4(b)

Daniel is playing a different game with his balloons. He may use any combination of the following two moves:

- Pop two balloons in box $k$ and move a third balloon from box $k$ to box $k+1$.
- Pop a single balloon in each of boxes $k$ and $k+1$ and then move another balloon from box $k+1$ to $k+2$.

What is the *smallest* value of $n$ such that after a finite number of moves, all that remains (8 marks)

(i) is a single balloon in box 4?

(ii) is a single balloon in box 8?

#### Solution 4(b)

Looks like a typical dynamic programming problem. 

A deep first search algorithm can solve it:

```cpp
#include <cstring>
#include <iostream>
using namespace std;
int a[8];
void dfs(int u)
{
    bool s = true;
    int t = 7;
    if (a[t] != 1) s = false;
    for (int i = 0; i < 8; i ++)
    {
        if (i == t) continue;
        if (a[i] != 0)
        {
            s = false;
            break;
        }
    }
    if (s)
    {
        cout << u << endl;
        exit(0);
    }
    for (int k = 0; k < 7; k ++)
    {
        if (a[k] >= 3)
        {
            a[k + 1] += 1, a[k] -= 3;
            dfs(u);
            a[k] += 3, a[k + 1] -= 1;
        }
        if (k < 6 && a[k] >= 1 && a[k + 1] >= 2)
        {
            a[k] -= 1, a[k + 1] -= 2, a[k + 2] += 1;
            dfs(u);
            a[k + 2] -= 1, a[k + 1] += 2, a[k] += 1;
        }
    }
}

int main()
{
    int n = 0;
    while (true)
    {
        memset(a, 0, sizeof(a));
        a[0] = n;
        dfs(n);
        n ++;
    }
    return 0;
}
```

Hence we get the smallest $n$ in (i) is $17$ and in (ii) is $577$.

#### Comments

Well, for the second task, just take the approach from the official solution.

You cannot actually get it from the code I provided, the time complexity is too high (it can only handle (i) in reasonable time). The recurrence equation is the proper approach.

### Problem 5

Freya creates a sequence with first term $1$ and each subsequent term $5$ more than the previous term. Hilary creates a different sequence with first term $a$ and each subsequent term $3$ less than the previous term. Both sequences are continued forever.

#### Task 5(a)

There is at least one number that appears in both sequences. Let $c$ be the smallest of those numbers. Find the possible values of $c$. (3 marks)

#### Solution 5(a)

Consider Freya's sequence:

$$1,6,11,16,21,\cdots$$

If $1$ appears in both sequence, no other numbers can be smaller.

If $6$ appears in both sequence, in Hilary's sequence $6,3,0,\cdots$, no other numbers can be smaller.

If $11$ appears in both sequence, in Hilary's sequence $11,8,5,2,-1,\cdots$, no other numbers can be smaller.

If $16$ appears in both sequence, in Hilary's sequence $16,13,10,7,4,1,\cdots$, number $1$ appears again. When the common number $x$ is larger or equal to 16, notice that $x-15$ will also be in both sequences.

So there are three possibilities: $1,6,11$.

#### Task 5(b)

Given that there are exactly $100$ numbers which appear in both sequences, find the possible values of $a$;

Enter the following on the answer sheet: (7 marks)

(i) How many possible values of a are there?

(ii) The smallest possible value of a.

(iii) The largest possible value of a.
 
#### Solution 5(b)

When $1$ is the smallest common term, the largest common term $a$ is equal to $1+15\times99=1486$. $a$ can also be $1489,1492,1495,1498$, but $a$ should smaller than $1+15\times100=1501$ otherwise there will be $101$ common terms.

Similarly, when $6$ is the smallest common term, the largest common term $a$ can equal to $1491,1494,1497,1500,1503$, and when $11$ is the smallest common term, $a$ can equal to $1496,1499,1502,1505,1508$.

So overall, there are $15$ possible values, the smallest possible value is $1486$ and the largest one is $1508$.

#### Comments

Some basic understanding on the arithmetic sequence will help you solve it out.

## Ending

Quite an interesting paper. The problem 4(b) does stuck me for some time, the solution provided seems too 'wordy' instead of some strict proves. I am not quite happy with that and may try to find some other approaches. There might be an update for it. For other questions, they are very attemptable and not too many tricks are needed.

It is very time-consuming to write a full solution like this. Maybe only special questions will be shared in the future.