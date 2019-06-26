[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

```python
agepreg, totalwgt_lb = live.agepreg, live.totalwgt_lb
thinkplot.Scatter(agepreg, totalwgt_lb, alpha=0.1, s=10)
thinkplot.Config(xlabel='Age of mother (years)',
                 ylabel='Baby weight (lb)',
                 axis=[10, 50, 2, 14],
                 legend=False)
```

```python
bins = np.arange(10, 50)
indices = np.digitize(agepreg, bins)
groups = live.groupby(indices)

mean_ages = [group.agepreg.mean() for i, group in groups]
cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in groups]
for percent in [75, 50, 25]:
    weights = [cdf.Percentile(percent) for cdf in cdfs]
    label = '%dth' % percent
    thinkplot.Plot(mean_ages, weights, label=label)
    
thinkplot.Config(xlabel='Age of mother (years)',
                 ylabel='Baby weight (lb)',
                 axis=[10, 45, 5, 9],
                 legend=True)
```
Ignoring the clear outliers, there is a slight increase in baby weight with older mothers, but this effect levels-off by about age 30.

```python
Corr(agepreg, totalwgt_lb), SpearmanCorr(agepreg, totalwgt_lb)
```
(0.06883397035410908, 0.09461004109658226)

The correlations show the slight positive correlation that can be seen on the scatter plot.
