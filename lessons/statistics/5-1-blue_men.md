[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```python
import scipy.stats

mu = 178
sigma = 7.7

dist = scipy.stats.norm(loc=mu, scale=sigma)

lower = (5*12 + 10) * 2.54
upper = (6*12 + 1) * 2.54

dist.cdf(upper) - dist.cdf(lower)
```

0.34274683763147457

34.3% of men in the US are between 5'10" and 6'1".
