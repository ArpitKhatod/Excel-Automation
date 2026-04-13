🧠 Pandas Visualization — plot() Full Parameter Cheat Sheet


Region_sum = sales_data.groupby("Region")[["Sales","Profit"]].sum().plot(kind="bar",title="Sales by Region",subplots=False,
                                                                         layout =(1,2),
                                                                         sharey=False,
                                                                         legend = True,
                                                                         stacked= True)
---

## BASIC SYNTAX

df.plot(kind="line")

---

## CORE PARAMETERS

kind        = "line", "bar", "barh", "hist", "box", "kde", "area", "scatter"
x           = column for x-axis
y           = column(s) for y-axis
title       = "Chart Title"
figsize     = (width, height)
grid        = True/False

---

## LAYOUT & STRUCTURE

subplots    = True/False   → separate plot per column
layout      = (rows, cols) → works only with subplots=True
sharex      = True/False
sharey      = True/False

---

## LEGEND

legend      = True/False
legend      = "reverse"  → reverse legend order

---

## STACKING

stacked     = True/False  → for bar/area charts

---

## COLORS & STYLE

color       = "red" or ["red","blue"]
colormap    = "viridis", "coolwarm", "Set1"

---

## AXIS CONTROL

xlabel      = "X Label"
ylabel      = "Y Label"
xlim        = (min, max)
ylim        = (min, max)
rot         = 0 / 45 / 90   → rotate labels

---

## MARKERS & LINE STYLE (line plots)

style       = "-" / "--" / ":"
marker      = "o", "x", "*"
linewidth   = 2

---

## BAR SPECIFIC

width       = 0.8
position    = 0.5

---

## HISTOGRAM

bins        = 10
density     = True/False

---

## SCATTER

df.plot(kind="scatter", x="Sales", y="Profit")
s           = size
c           = color column

---

## BOX PLOT

df.plot(kind="box")

---

## AREA PLOT

df.plot(kind="area", stacked=True)

---

## ADVANCED

secondary_y = ["col"] → second axis
logy        = True/False
table       = True → show table below chart

---

## SAVE FIGURE

import matplotlib.pyplot as plt
plt.savefig("chart.png")

---

## MOST USED COMBO (REAL PROJECT)

df.groupby("Region")[["Sales","Profit"]].sum().plot(
kind="bar",
figsize=(10,5),
title="Sales vs Profit",
stacked=True,
rot=45
)

---

## IMPORTANT NOTES

layout works only with subplots=True
stacked works only for bar/area
scatter needs x and y
hist works on single column

---
