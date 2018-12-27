[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

**Exercise 5.1** In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters _μ_ = 178 cm and _σ_ = 7.7 cm for men, and _μ_ = 163 cm and _σ_ = 7.3 cm for women.

In order to join Blue Man Group, you have to be male between 5'10" and 6'1" (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use scipy.stats.norm.cdf.

First, I imported the necessary modules.

```
import thinkstats2
import brfss
```

I then read the BRFSS data into a dataframe.

```
df = brfss.ReadBrfss()
```

