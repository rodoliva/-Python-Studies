# Seaborn

From <a href="https://seaborn.pydata.org/" target="_blank">Seaborn</a>

Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.

---

## Regression plot

```python
import seaborn as sns
sns.regplot(x="predictor", y="target", data=df) # predictor and targer are pandas column names
plt.ylim(0,)
```

## Residual plot

```python
import seaborn as sns
sns.residplot(df["predictor"], df["target"]) # predictor and targer are pandas column names
```

## Distribution plot

```python
import seaborn as sns
sns.distplot(df["target"], hist=False, color="r", label="target") # predictor and targer are pandas column names
sns.distplot(Yhat, hist=False, color="b", label="fitted values", ax=ax1)
```

---

## Examples

```python
import seaborn as sns
sns.set()
tips = sns.load_dataset("tips")
sns.relplot(x="total_bill", y="tip", col="time",
            hue="smoker", style="smoker", size="size",
            data=tips);
```
![Graph20](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph20.png)

```python
dots = sns.load_dataset("dots")
sns.relplot(x="time", y="firing_rate", col="align",
            hue="choice", size="coherence", style="choice",
            facet_kws=dict(sharex=False),
            kind="line", legend="full", data=dots);
```
![Graph21](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph21.png)

```python
fmri = sns.load_dataset("fmri")
sns.relplot(x="timepoint", y="signal", col="region",
            hue="event", style="event",
            kind="line", data=fmri);
```
![Graph22](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph22.png)

```python
sns.lmplot(x="total_bill", y="tip", col="time", hue="smoker",
           data=tips);
```
![Graph23](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph23.png)

```python
sns.catplot(x="day", y="total_bill", hue="smoker",
            kind="swarm", data=tips);
```
![Graph24](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph24.png)

```python
sns.catplot(x="day", y="total_bill", hue="smoker",
            kind="violin", split=True, data=tips);
```
![Graph25](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph25.png)

```python
sns.catplot(x="day", y="total_bill", hue="smoker",
            kind="bar", data=tips);
```
![Graph26](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph26.png)

```python
import matplotlib.pyplot as plt
f, axes = plt.subplots(1, 2, sharey=True, figsize=(6, 4))
sns.boxplot(x="day", y="tip", data=tips, ax=axes[0])
sns.scatterplot(x="total_bill", y="tip", hue="day", data=tips, ax=axes[1]);
```
![Graph27](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph27.png)

```python
sns.relplot(x="time", y="firing_rate", col="align",
            hue="choice", size="coherence", style="choice",
            height=4.5, aspect=2 / 3,
            facet_kws=dict(sharex=False),
            kind="line", legend="full", data=dots);
```
![Graph28](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph28.png)

```python
iris = sns.load_dataset("iris")
sns.jointplot(x="sepal_length", y="petal_length", data=iris);
```
![Graph29](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph29.png)

```python
sns.pairplot(data=iris, hue="species");
```
![Graph30](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph30.png)

```python
sns.set(style="ticks", palette="muted")
sns.relplot(x="total_bill", y="tip", col="time",
            hue="smoker", style="smoker", size="size",
            data=tips);
```
![Graph31](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph31.png)

```python
sns.relplot(x="total_bill", y="tip", col="time",
            hue="size", style="smoker", size="size",
            palette="YlGnBu", markers=["D", "o"], sizes=(10, 125),
            edgecolor=".2", linewidth=.5, alpha=.75,
            data=tips);
```
![Graph32](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph32.png)

```python
g = sns.catplot(x="total_bill", y="day", hue="time",
                height=3.5, aspect=1.5,
                kind="box", legend=False, data=tips);
g.add_legend(title="Meal")
g.set_axis_labels("Total bill ($)", "")
g.set(xlim=(0, 60), yticklabels=["Thursday", "Friday", "Saturday", "Sunday"])
g.despine(trim=True)
g.fig.set_size_inches(6.5, 3.5)
g.ax.set_xticks([5, 15, 25, 35, 45, 55], minor=True);
plt.setp(g.ax.get_yticklabels(), rotation=30);
```
![Graph33](https://raw.githubusercontent.com/rodoliva/Python-Studies/master/Data%20Science/MathPlot/Seaborn/graph33.png)


## Example Gallery

<a href="https://seaborn.pydata.org/examples/index.html">Examples</a>

