# Module Management
## Reload
```python
import importlib
importlib.reload(module)
```

# Etc
## tqdm integration
```python
from tqdm import tnrange, tqdm_notebook
from time import sleep

for i in tnrange(3, desc='1st loop'):
    for j in tqdm_notebook(range(100), desc='2nd loop'):
        sleep(0.01)
```
