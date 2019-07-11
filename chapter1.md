---
title: 'Chapter Title Here'
description: 'Chapter description goes here.'
free_preview: true
---

## The effect of diversification

```yaml
type: NormalExercise
key: fec7f8f3e6
xp: 100
```

In this exercise you're going to compare performance of four individual stocks, to a portfolio of the same four stocks. You'll see that 2 out of the four stocks will under-perform over a time period of roughly four years, and two will perform quite well. The stocks you're going to investigate are General Electric, JP Morgan, Microsoft and Proctor & Gamble. Let's do a little game: pick one stock to invest in, then, let's see how it would have performed over time.There's a 50-50 chance whether you'll pick a winning stock, versus a losing stock. Let's look at the data and see whether your stock is one of strong performers. Available is a data set called `stock_returns` containing the cumulative returns of these four stocks over time, plus a portfolio of these stocks.

`@instructions`


`@hint`


`@pre_exercise_code`
```{python}

```

`@sample_code`
```{python}

```

`@solution`
```{python}
import pandas as pd
pd.DataFrame([1, 2, 3])
```

`@sct`
```{python}
Ex().check_function('pandas.DataFrame').check_args('data').has_equal_value()
success_msg("Well done!")
```

---

## The effect of diversification

```yaml
type: TabExercise
key: 947a8d8664
xp: 100
```

In this exercise you're going to compare performance of four individual stocks, to a portfolio of the same four stocks. You'll see that 2 out of the four stocks will under-perform over a time period of roughly four years, and two will perform quite well. The stocks you're going to investigate are General Electric, JP Morgan, Microsoft and Proctor & Gamble. Let's do a little game: pick one stock to invest in, then, let's see how it would have performed over time.There's a 50-50 chance whether you'll pick a winning stock, versus a losing stock. Let's look at the data and see whether your stock is one of strong performers. Available is a data set called `stock_returns` containing the cumulative returns of these four stocks over time, plus a portfolio of these stocks.

`@pre_exercise_code`
```{python}
import numpy as np
import pandas as pd
import matplotlib
import matplotlib.pyplot as plt
from urllib.request import urlretrieve
url = 'https://assets.datacamp.com/production/repositories/4745/datasets/bee1460940560e2833519271de9440cc8c4a57d5/compare_pct_returns.csv'
urlretrieve(url, 'compare_pct_returns.csv')

stock_returns=pd.read_csv('compare_pct_returns.csv')
stock_returns=stock_returns.set_index('date')

def plot_pct_returns(df):
    fig, ax = plt.subplots()
    ax.plot(df.index, df.MSFT, marker='', color='green', linewidth=2, label="MSFT")
    ax.plot(df.index, df.portfolio, linewidth=2, linestyle='dashed', color='skyblue', label='portfolio')
    ax.plot(df.index, df.PG, marker='', color='pink', linewidth=2, label="PG")
    ax.plot(df.index, df.JPM, color='yellow', linewidth=2, label='JPM')
    ax.plot(df.index, df.GE, color='red', linewidth=2, label='GE')
    ax.xaxis.set_major_locator(matplotlib.dates.YearLocator())
    #ax.xaxis.set_minor_locator(matplotlib.dates.MonthLocator((1,4,7,10)))
    ax.xaxis.set_major_formatter(matplotlib.dates.DateFormatter("\n%Y"))
    #ax.xaxis.set_minor_formatter(matplotlib.dates.DateFormatter("%b"))
    plt.setp(ax.get_xticklabels(), rotation=0, ha="center")
    plt.legend()
    plt.show()

```

***

```yaml
type: NormalExercise
key: eb8a55bf61
xp: 100
```

`@instructions`


`@hint`


`@sample_code`
```{python}
# Check beginning and end of dataset
stock_returns.____()
stock_returns.____()
```

`@solution`
```{python}
# Check beginning and end of dataset
stock_returns.head()
stock_returns.tail()
```

`@sct`
```{python}
Ex().check_function('stock_returns.head')
Ex().check_function('stock_returns.tail')
```

***

```yaml
type: NormalExercise
key: 75205fc8f3
```

`@instructions`


`@hint`


`@sample_code`
```{python}
# Check beginning and end of dataset
stock_returns.head()
stock_returns.tail()

# Plot percentage returns
plot_pct_returns(____)
```

`@solution`
```{python}
# Check beginning and end of dataset
stock_returns.head()
stock_returns.tail()

# Plot percentage returns
plot_pct_returns(stock_returns)
```

`@sct`
```{python}
Ex().check_function('plot_pct_returns').check_args(0).has_equal_value()
```

---

## Insert exercise title here

```yaml
type: VideoExercise
key: 6a9f13e8f3
xp: 50
```

`@projector_key`
b3c7e8655ac2c144e980bfe04ca1a1f5

---

## Insert exercise title here

```yaml
type: VideoExercise
key: bda7ec31e0
xp: 50
```
