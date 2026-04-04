```python
# Import NumPy library (used for numerical arrays and fast operations)
import numpy as np

# Import Pandas library (used for Series and DataFrame data structures)
import pandas as pd


# Create a NumPy array from a Python list
# NumPy arrays are faster and more memory efficient than Python lists
np_array = np.array([2, 6, 1, 3])


# Convert NumPy array into a Pandas Series
# Pandas Series = 1D labeled array (default index starts from 0)
pd_series = pd.Series(np_array)

# Output:
# 0    2
# 1    6
# 2    1
# 3    3


# Create Pandas Series with custom index labels
# Instead of default 0,1,2,3 → using a,b,c,d as index
pd_series2 = pd.Series(np_array, index=["a", "b", "c", "d"])

# Output:
# a    2
# b    6
# c    1
# d    3


# Create Pandas Series using dictionary
# Keys become index labels
# Values become data
pd_series3 = pd.Series({"a": 2, "b": 6, "c": 1, "d": 3})

# Output same as above:
# a    2
# b    6
# c    1
# d    3


# Slice the Series starting from position index 2
# IMPORTANT: This is positional slicing (not label-based)
# index position 2 = "c"
pd_series2[2:]

# Output:
# c    1
# d    3
```
