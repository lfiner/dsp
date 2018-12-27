[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

**Exercise 5.1** In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters _μ_ = 178 cm and _σ_ = 7.7 cm for men, and _μ_ = 163 cm and _σ_ = 7.3 cm for women.

In order to join Blue Man Group, you have to be male between 5'10" and 6'1" (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use scipy.stats.norm.cdf.

First, I imported the necessary module.

```
from scipy.stats import norm
```

The group of interest is men between 5'10" and 6'1", which corresponds to the range 178 cm to 185 cm.


I used norm.cdf to calculate the cumulative percentage of values up to (but not including 178) cm &mdash; in other words, up to 177 cm. I used the _μ_ and _σ_ values for men from the BRFSS to shift and scale the normal distribution used.

```
lt178 = norm.cdf(177, 178, 7.7)
```

And then I calculated the cumulative percentage of values up to (and including) 185 cm.

```
le185 = norm.cdf(185, 178, 7.7)
```

Finally, I calculated the difference.

```
diff = le185 - lt178
```

The result: 

```
Percent of men between 178 and 185 cm inclusive: 0.37
```
