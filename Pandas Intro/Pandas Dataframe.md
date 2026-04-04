```python
# ============================================
# Pandas DataFrame Object - Learning Notes
# With Expected Outputs
# ============================================

import pandas as pd
import numpy as np


# ============================================
# 1. Creating DataFrame from 3D array
# ============================================

# Creating a 3D numpy array (shape = 1,3,3)
arr = np.array([
    [
        [1,2,3],
        [4,5,6],
        [7,8,9]
    ]
])

# reshape converts 3D -> 2D
df2 = pd.DataFrame(arr.reshape(3,3))

# Expected Output
#    0  1  2
# 0  1  2  3
# 1  4  5  6
# 2  7  8  9


# ============================================
# 2. Creating DataFrame with custom columns & index
# ============================================

df = pd.DataFrame(
    np.array(
        [
            [1,2,3],
            [4,5,6],
            [7,8,9]
        ]
    ),
    columns=["alpha","beta","cappa"],
    index=["A","B","C"]
)

# Expected Output
#    alpha  beta  cappa
# A      1     2      3
# B      4     5      6
# C      7     8      9


# ============================================
# 3. Renaming columns
# ============================================

df.columns = ["Test","Check","Mat"]

# Expected Output
#    Test  Check  Mat
# A     1      2    3
# B     4      5    6
# C     7      8    9


# ============================================
# 4. Creating DataFrame from dictionary
# ============================================

df_dict = pd.DataFrame(
    {
        "a":[1,2,3],
        "b":[4,5,6],
        "c":[7,8,9]
    }
)

# Expected Output
#    a  b  c
# 0  1  4  7
# 1  2  5  8
# 2  3  6  9


# ============================================
# 5. Column Selection
# ============================================

df["Test"]

# Expected Output (Series)
# A    1
# B    4
# C    7
# Name: Test, dtype: int64


df[["Test","Check"]]

# Expected Output (DataFrame)
#    Test  Check
# A     1      2
# B     4      5
# C     7      8


type(df["Test"])

# Expected Output
# pandas.core.series.Series


# ============================================
# 6. loc - Label based selection
# ============================================

location_value = df.loc["A","Test"]

# Expected Output
# 1


df.loc["A"]

# Expected Output
# Test     1
# Check    2
# Mat      3
# Name: A, dtype: int64


# ============================================
# 7. iloc - Position based selection
# ============================================

df.iloc[0]

# Expected Output
# Test     1
# Check    2
# Mat      3
# Name: A, dtype: int64


# ============================================
# 8. Continuous slicing using loc
# ============================================

df.loc["B":,"Check":]

# Expected Output
#    Check  Mat
# B      5    6
# C      8    9


# ============================================
# 9. Non-continuous selection using loc
# ============================================

df.loc[["A","B"],["Check","Mat"]]

# Expected Output
#    Check  Mat
# A      2    3
# B      5    6


# ============================================
# 10. Non-continuous selection using iloc
# ============================================

df.iloc[[0,2],[1,2]]

# Expected Output
#    Check  Mat
# A      2    3
# C      8    9


# ============================================
# 11. Mixed slicing using iloc
# ============================================

df.iloc[[0,2],1:]

# Expected Output
#    Check  Mat
# A      2    3
# C      8    9


df.iloc[0:,1:]

# Expected Output
#    Check  Mat
# A      2    3
# B      5    6
# C      8    9
```
