# econ3916-lab04-anomaly-detection# Robust Statistics -- Automated Anomaly Detection

## Objective
I wanted to see which summary statistics hold up when a dataset has extreme
values, and to compare two ways of finding outliers in California Housing data.

## Methodology
- I loaded the California Housing data (20,640 observations).
- I computed six summary measures for house prices: mean, median, trimmed
  mean, standard deviation, IQR, and MAD.
- I built Tukey Fences by hand from the quartiles and the IQR, and used them
  to flag price outliers.
- I ran an Isolation Forest on the other features to find rows that are
  unusual as a combination, not just in one column.
- I compared the rows each method flagged.
- I corrupted 5% of the prices on purpose and recomputed the summary measures
  to see which ones moved.

## Key Findings
- The mean and standard deviation are pulled by extreme values. The median,
  trimmed mean, IQR, and MAD are much less affected.
- Tukey Fences and Isolation Forest mostly flag different observations. Tukey
  looks only at price, while Isolation Forest looks at all the features
  together, so it catches rows with ordinary prices but unusual combinations.
- After 5% contamination, the mean shifted by [YOUR VALUE]%, while the median
  shifted by only [YOUR VALUE]%.
- A flagged observation is not automatically an error. I would check where it
  came from before deciding whether to keep it.
