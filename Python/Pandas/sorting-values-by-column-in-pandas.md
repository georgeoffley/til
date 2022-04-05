# Sorting Values By Column in Pandas

[Source](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sort_values.html)

In Pandas when reading from a CSV into a dataframe you can sort the values in a myriad of ways. One such way is sorting by the columns.

## Example

```python
df.sort_values(by=['column'], ascending=false)
```

Here you pass in the columns you want to sort by. 

You can also add in if you want ascending or descending.