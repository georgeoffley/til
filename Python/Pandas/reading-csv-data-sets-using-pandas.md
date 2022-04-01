# Reading CSV Data sets using Pandas

[Source](https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html)

```python
df = pd.read_csv('file.csv')
```

You can also set things like reading with no headers like below.

```python
df = pd.read_csv('file.csv', header=None)
```

You can also bring in specific columns into the data frame if you choose.

```python
data = pd.read_csv('file.csv')
df = DataFrame(data, columns = ['column'])
```