[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

**Exercise 2.4** Using the variable `totalwgt_lb`, investigate whether first babies are lighter or heavier than others. Compute Cohen's _d_ to quantify the diffence between the groups. How does it compare to the difference in pregnancy length?


First, I imported the necessary modules.

```
import math
import nsfg
```

Then, I loaded the NSFG data into a dataframe.

```
preg = nsfg.ReadFemPreg()
```

I then created two new dataframes containing the birthweights for first births and other births.

```
births = preg[preg.outcome == 1]
firsts = births.totalwgt_lb[births.birthord == 1]
others = births.totalwgt_lb[births.birthord != 1]
```

I looked at the mean birthweight for each group.

```
print('Mean weight of first births:', firsts.mean())
print('Mean weight of other births:', others.mean())
```

The results:

```
Mean weight of first births: 7.201094430437772
Mean weight of other births: 7.325855614973262
```

So the difference is about a tenth of a pound. Seems small. 
I then calculated Cohen's _d_ for this difference.

I defined the Cohen effect size function (provided by ThinkStats).

```
def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d
```

Finally, I calculated Cohen's _d_.

```
print("Cohen's d:", CohenEffectSize(firsts, others))
```

The result:

```
Cohen's d: -0.088672927072602
```

This figure, while larger (in an absolute-value sense) than the _d_ value for pregnancy length (0.029 as reported in ThinkStats), is still small. (Cohen [suggested](http://staff.bath.ac.uk/pssiw/stats2/page2/page14/page14.html) that anything less than |0.2| is a small effect size.) This suggests that the difference in birthweight between the two groups is not substantively significant.
