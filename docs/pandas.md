# Tips

* [Data School's top 25 pandas tricks](https://nbviewer.jupyter.org/github/justmarkham/pandas-videos/blob/master/top_25_pandas_tricks.ipynb)
* [A Comprehensive Guide to Pandas’ Advanced Features in 20 Minutes](https://towardsdatascience.com/learn-advanced-features-for-pythons-main-data-analysis-library-in-20-minutes-d0eedd90d086)

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

# Etc
## tqdm integration
```python
import pandas as pd
import numpy as np
from tqdm import tqdm

df = pd.DataFrame(np.random.randint(0, 100, (100000, 6)))

# Register `pandas.progress_apply` and `pandas.Series.map_apply` with `tqdm`
# (can use `tqdm_gui`, `tqdm_notebook`, optional kwargs, etc.)
tqdm.pandas(desc="my bar!")

# Now you can use `progress_apply` instead of `apply`
# and `progress_map` instead of `map`
df.progress_apply(lambda x: x**2)
# can also groupby:
# df.groupby(0).progress_apply(lambda x: x**2)
```
