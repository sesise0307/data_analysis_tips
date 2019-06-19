# EDA

* [pandas-profiling](https://github.com/pandas-profiling/pandas-profiling)

# Grouping

* Average every _n_ rows

```python
df.groupby(np.arange(df.shape[0]) // n).mean()
```

* Group by months

```python
df.groupby(pd.Grouper(freq='1M'))
```

* Group by range

```python
df.groupby(pd.cut(df[feature], bins, include_lowest=True))
```
or
```python
df.groupby(pd.cut(df[feature], bins, right=False))
```
