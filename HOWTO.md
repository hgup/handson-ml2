# `sklearn`

- `sklearn.model_selection` when you want to choose which exact model to choose, you perform operations like **splitting** the data. This module allows you to do so.
- `sklearn.impute` to impute missing values.

# `pandas` tricks

- `pd.cut()` helps you cut data based on a criteria

## `pd.DataFrame`

- \#concept **axis** refers to the row, column or a higher dimensional point (e.g. `axis=0` refers to rows, `axis=1` refers to columns. `axis=3` can refer to time, if we have data across years and each row corresponds to the same entity.)

- `loc` and `iloc` have this commonly known distinction that the first is used to index by **label** but the latter by `index`.
  - But also know that when we take a subset of the **dataframe** (say, main) (lets say while test-train splitting of the data), the original `index` values of main df is preserved as the labels of the subsets.
  - e.g. `main = [1,2,3,4,5,6,7]` are the default labels (for an unlabelled df main), and upon splitting it we get subsets `A = [1,3,4,5]` and `B = [2,6,7]`
  - So now note that we cannot do `A.loc[range(1,5)]` since we don't have **label** 2 in our `A`. But `A.iloc[range(1,5)]` will definitely work since indices are always in sequence.

## `pd.Series`

- `pd.Series.apply()` applies a function to each element of the series and returns another series with the output of each of those function call in the same order.

- if you want the "label" to each of the items in a pandas series, its actually called `index`

## `pandas.plotting`

```python
housing.plot(kind="scatter",x='longitude',y='latitude',alpha=.4,
             s=housing['population']/100, label="population",
             c="median_house_value", colorbar=True, cmap=plt.get_cmap('jet'))
```
  - `s` is the radius of the circle.
  - `alpha` opacity.
  - `c` is the color (always give the name of the property (e.g. `"population"` instead of `housing['population']` whenever possible, here we needed to make an adjustment to the size).
  - `cmap` gives us the color map.


`scatter_matrix` is used to plot correlation maps.


# `numpy` tricks

## `np.ndarray`

- **N-dimensional array**
- Use `iloc` to reference by index
- Use `loc` to reference by label (==check this==: It is also possible to pass in an index, if label for the data is not available)