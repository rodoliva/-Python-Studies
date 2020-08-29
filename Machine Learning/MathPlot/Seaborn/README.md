# Seaborn

From <a href="https://seaborn.pydata.org/" target="_blank">Seaborn</a>

Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.

---

```python
import seaborn as sns
sns.set()
tips = sns.load_dataset("tips")
sns.relplot(x="total_bill", y="tip", col="time",
            hue="smoker", style="smoker", size="size",
            data=tips);
```


## Example Gallery

<a href="https://seaborn.pydata.org/examples/index.html">Examples</a>

