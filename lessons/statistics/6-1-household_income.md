[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

```
Median(sample), Mean(sample), Skewness(sample), PearsonMedianSkewness(sample)
```
(51226.45447894046, 74278.70753118733, 4.949920244429583, 0.7361258019141782)

```
cdf[Mean(sample)]
```
66% of households report a taxable income below the mean.

```
log_sample = InterpolateSample(income_df, log_upper=7.0) # Assume upper bound of $10 million
sample = np.power(10, log_sample)
Median(sample), Mean(sample), Skewness(sample), PearsonMedianSkewness(sample), cdf[Mean(sample)]
```
(51226.45447894046,
 124267.39722164685,
 11.603690267537793,
 0.39156450927742087,
 0.8565630665207663)
 
The median is unaffected by the assumed upper bound, but all other statistics are strongly affected by this one assumption.
