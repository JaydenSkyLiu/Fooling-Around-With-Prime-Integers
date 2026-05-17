**Attempt #2:**

**The Expression for the Denominator in the Reciprocal of the Sum of Primes**

**14/05/2026 - 16/05/2026**

&emsp;My second attempt built upon the framework that was the first attempt. This time around, instead of focusing on the reciprocal prime sum, I focused moreso on creating an expression that would add upon the first reciprocal prime sum given $n$. If there was an equation that could somehow fit in the denominator, we would have that ratio change equation we needed in Attempt #1.

$$S_{p}\left(n\right)=\frac{1}{2+f\left(n\right)}$$

&emsp;In order to identify an equation for $f(n)$, I took the denominators from the $S_{p}$ column of the initial table and subtracted 2 from each denominator.

| $S_{p}$ | $d$ |
| :---: | :---: |
| $\frac{1}{2}$ | 0 |
| $\frac{1}{5}$ | 3 |
| $\frac{1}{10}$ | 8 |
| $\frac{1}{17}$ | 15 |
| $\frac{1}{28}$ | 26 |
| $\frac{1}{41}$ | 39 |
| $\frac{1}{58}$ | 56 |
| $\frac{1}{77}$ | 75 |

&emsp;Upon generating a power regression equation for the values, lo and behold.

![](/images/Attempt_2/Attempt_2-Regress1.png)

&emsp;Bingo. A regression equation with an $R^2$ value of 1, indicative that the regression equation is a perfect fit for all values present within the table in the $d$ column.

&emsp;Hence, we may formulate the following equation for $S_{p}(n)$.

$$S_{p}\left(n\right)=\frac{1}{2+0.647927\cdot\left(n^{2.29843}\right)}$$

&emsp;Using the $P(n)$ equation generated in Attempt #1, we may notice that, although the primes are pretty close to their actual values, there must be some rounding for the generated values through $P(n)$.

| $n$ | $P(n)$ | $A_{p}$ |
| :---: | :---: | :---: |
| 1 | 0.647927 | 2 |
| 2 | 2.5393694 | 3 |
| 3 | 4.9065673 | 5 |
| 4 | 7.5851531 | 7 |
| 5 | 10.506413 | 11 |
| 6 | 13.630078 | 13 |
| 7 | 16.929122 | 17 |

&emsp;We can rectify this issue by only rounding the generated values from P(n) with ceiling.

| $n$ | $P(n)$ | $A_{p}$ |
| :---: | :---: | :---: |
| 1 | 1 | 2 |
| 2 | 3 | 3 |
| 3 | 5 | 5 |
| 4 | 8 | 7 |
| 5 | 11 | 11 |
| 6 | 14 | 13 |
| 7 | 17 | 17 |

&emsp;There exists a slight odd discrepancy when $n=4$ and when $n=6$ within this sample size with range of 7, and that shows that our equation, whilst it works, is not a formula for identifying exact primes, made evident when the sample size increases.

| $n$ | $P(n)$ | $A_{p}$ |
| :---: | :---: | :---: |
| 1 | 1 | 2 |
| 2 | 3 | 3 |
| 3 | 5 | 5 |
| 4 | 8 | 7 |
| 5 | 11 | 11 |
| 6 | 14 | 13 |
| 7 | 17 | 17 |
| 8 | 21 | 19 |
| 9 | 24 | 23 |
| 10 | 28 | 29 |
| 11 | 32 | 31 |
| 12 | 36 | 37 |
| 13 | 40 | 41 |
| 14 | 44 | 43 |
| 15 | 48 | 47 |

&emsp;At times, the values may be off by just one integer. Increasing the sample size further increases the magnitude of deviations between the predicted values posed by $P(n)$ and the actual expected values.

| $n$ | $P(n)$ | $A_{p}$ |
| :---: | :---: | :---: |
| 20 | 71 | 71 |
| 30 | 121 | 113 |
| 40 | 177 | 173 |
| 50 | 237 | 229 |
| 60 | 300 | 281 |
| 70 | 367 | 349 |
| 80 | 437 | 409 |
| 90 | 510 | 463 |
| 100 | 585 | 541 |

&emsp;Looking at the $S_{p}(n)$ equation created, and comparing the values by the actual reciprocal sum, it is not difficult to see why there exists a slight fall-off between the actual prime integers and the generated prime integers.

| $A_{sp}$ | $S_{p}(n)$ |
| :---: | :---: |
| 0.5 | 0.5 |
| 0.2 | 0.2 |
| 0.1 | 0.1 |
| 0.0588235294 | 0.058823529 |
| 0.0357142857 | 0.035714286 |
| 0.0243902439 | 0.024390244 |
| 0.0172413793 | 0.017241379 |
| 0.012987013 | 0.012658228 |

&emsp;At around $n=8$, there is a significant deviation between $A_{sp}$ and $S_{p}(n)$. In fraction form, $A_{sp}$ is 1/77 when $n=8$, whereas $S_{p}(n)$ is 1/79 when $n=8$. This deviation translates over to our $P(n)$ equation, in which the generated prime created with $P(n)$ is offset to the actual prime number by 2.

&emsp;My initial thought was that, perchance, our sample size of prime integers wasn’t large enough, so I decided to increase the sample size to find a better match for $S_{p}(n)$.

| $n$ | $A_{p}$ | $S_{p}(n)$ | $d$ |
| :---: | :---: | :---: | :---: |
| 100 | 541 | $\frac{1}{24133}$ | 24131 |
| 110 | 601 | $\frac{1}{29897}$ | 29895 |
| 120 | 659 | $\frac{1}{36227}$ | 36225 |
| 130 | 733 | $\frac{1}{43201}$ | 43199 |
| 140 | 809 | $\frac{1}{50887}$ | 50885 |
| 150 | 863 | $\frac{1}{59269}$ | 59267 |
| 160 | 941 | $\frac{1}{68341}$ | 68339 |
| 170 | 1013 | $\frac{1}{78149}$ | 78147 |
| 180 | 1069 | $\frac{1}{88585}$ | 88583 |
| 190 | 1151 | $\frac{1}{99685}$ | 99683 |
| 200 | 1223 | $\frac{1}{111587}$ | 111585 |

&emsp;Running the same power regression process as with the previous dataset, we get the following equation.

![](/images/Attempt_2/Attempt_2-Regress2.png)

&emsp;There is quite a substantial difference between the regression equation generated with the new larger dataset compared to the previous smaller dataset, however. Whilst the first $S_{p}(n)$ equation, without the ceiling function, was $S_{p}\left(n\right)=\frac{1}{2+0.647927\left(n^{2.2984}\right)}$, the new $S_{p}(n)$ equation is $S_{p}\left(n\right)=\frac{1}{2+0.928914\left(n^{2.20778}\right)}$.

&emsp;We may also begin to notice that there is a deviation between the $P(n)$ equation that used the first $S_{p}(n)$ formula, compared to the $P(n)$ equation that used the second $S_{p}(n)$ formula.

![](/images/Attempt_2/Attempt_2-Graph1.png)

&emsp;We can also compare our graphs with the actual $n^{\text{th}}$ prime value.

![](/images/Attempt_2/Attempt_2-Graph2.png)

&emsp;But wait—previously, I also used the ceiling function with the first $P(n)$ equation to turn continuous values into discrete integers. Using that function, we get the following graph when the ceiling function is employed both for the first $P(n)$ equation and the second $P(n)$ equation.

![](/images/Attempt_2/Attempt_2-Graph3.png)

&emsp;…okay, admittedly, it’s confusing to interpret, but it seems as though the first $P(n)$ function was closer to the initial values than the second function. However, we also need to look at the larger scope and compare the accuracies of the first $P(n)$ function and the second $P(n)$ function as $n$ increases.

![](/images/Attempt_2/Attempt_2-Graph4.png)

&emsp;Although initially the first P(n) equation seemed to match the primes closer than the second P(n) equation, as n grows larger, the second P(n) equation seemed more accurate than the first. However, it’s still not the best at generating primes.

| $n$ | $P(n)$ | $A_{p}$ |
| :---: | :---: | :---: |
| 100 | 531 | 541 |
| 110 | 596 | 601 |
| 120 | 662 | 659 |
| 130 | 730 | 733 |
| 140 | 798 | 809 |
| 150 | 867 | 863 |
| 160 | 939 | 941 |
| 170 | 1010 | 1013 |
| 180 | 1083 | 1069 |
| 190 | 1156 | 1151 |
| 200 | 1230 | 1223 |

&emsp;Although our generated prime values are pretty close to the actual prime integers at $n$, what I wish to attain is a formula for finding an exact prime, not a formula for finding primes close enough to their actual values, so this won’t slide. A larger sample size for prime integers may be required to further advance the process of Attempt #2.
