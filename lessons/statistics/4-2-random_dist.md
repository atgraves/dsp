[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```
random_1000 = np.random.random(size=1000)

random_pmf = thinkstats2.Pmf(random_1000)
thinkplot.Pmf(random_pmf, linewidth=0.1)
thinkplot.Config(xlabel='Random variate', ylabel='PMF')
```

1000 discrete data points are way too many to be visualized in a PMF.

```
random_1000_cdf = thinkstats2.Cdf(random_1000)

thinkplot.Cdf(random_1000_cdf)
thinkplot.Config(xlabel='Random variate', ylabel='CDF')
```
