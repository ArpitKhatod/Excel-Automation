1. Load Data
Power Query: Get Data → CSV
Pandas: df = pd.read_csv("file.csv")

2. Remove Columns
Power Query: Remove Columns
Pandas: df = df.drop(["col1","col2"], axis=1)

3. Keep Columns
Power Query: Choose Columns
Pandas: df = df[["col1","col2"]]

4. Filter Rows
Power Query: Filter rows where Sales > 100
Pandas: df = df[df["Sales"] > 100]

5. Rename Column
Power Query: Rename Column
Pandas: df = df.rename(columns={"Old":"New"})

6. Add Custom Column
Power Query: Add Column → Custom Column
Pandas: df["New"] = df["A"] + df["B"]

7. Conditional Column
Power Query: If Sales > 100 then High else Low
Pandas: df["Type"] = np.where(df["Sales"] > 100, "High", "Low")

8. Change Data Type
Power Query: Change Type → Date
Pandas: df["Date"] = pd.to_datetime(df["Date"])

9. Replace Values
Power Query: Replace Values
Pandas: df["Region"] = df["Region"].replace("US","USA")

10. Remove Duplicates
Power Query: Remove Duplicates
Pandas: df = df.drop_duplicates()

11. Sort
Power Query: Sort Ascending
Pandas: df = df.sort_values("Sales")

12. Group By
Power Query: Group By Customer → Sum Sales
Pandas: df.groupby("Customer")["Sales"].sum()

13. Merge Queries
Power Query: Merge Queries (Left Join)
Pandas: pd.merge(df1, df2, on="ID", how="left")

14. Append Queries
Power Query: Append Queries
Pandas: pd.concat([df1, df2])

15. Split Column
Power Query: Split Column by delimiter
Pandas: df[["A","B"]] = df["Name"].str.split("-", expand=True)

16. Trim / Clean
Power Query: Transform → Format → Trim
Pandas: df["Name"] = df["Name"].str.strip()

17. Upper / Lower
Power Query: UPPERCASE
Pandas: df["Name"] = df["Name"].str.upper()

18. Pivot
Power Query: Pivot Column
Pandas: df.pivot(index="Date", columns="Product", values="Sales")

19. Unpivot
Power Query: Unpivot Columns
Pandas: pd.melt(df, id_vars=["Date"])

20. Fill Down
Power Query: Fill Down
Pandas: df.fillna(method="ffill")

21. Fill Up
Power Query: Fill Up
Pandas: df.fillna(method="bfill")

22. Extract Year
Power Query: Date → Year
Pandas: df["Year"] = df["Date"].dt.year

23. Extract Month
Power Query: Date → Month
Pandas: df["Month"] = df["Date"].dt.month

24. Column from Example
Power Query: Column from example
Pandas: df["New"] = df["Text"].str[:3]

25. Index Column
Power Query: Add Index
Pandas: df.reset_index()
OR
df["Index"] = range(len(df))

---------------------------------
MOST USED (Power Query → Pandas)
---------------------------------
Remove columns → drop()
Filter rows → df[condition]
Add column → df["new"]
Group by → groupby()
Merge → merge()
Append → concat()
Split column → str.split()
Replace → replace()
Sort → sort_values()
Change type → astype()
Fill down → fillna(ffill)
Pivot → pivot_table()

---------------------------------
FULL TRANSFORMATION (PIPELINE)
---------------------------------
Power Query:
Load → Filter → Add Column → Group → Sort

Pandas:

df = (
    pd.read_csv("sales.csv")
    .query("Sales > 100")
)

df["Profit"] = df["Sales"] - df["Cost"]

df = (
    df.groupby("Region")
      .sum()
      .sort_values("Sales", ascending=False)
)
