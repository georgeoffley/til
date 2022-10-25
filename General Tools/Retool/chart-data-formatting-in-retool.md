# Chart Data Formatting in Retool

Good sources
- https://community.retool.com/t/bug-in-pie-charts/4360/2
https://docs.retool.com/docs/build-charts-graphs

Data being fed into a chart needs to be in a specific format to work. _**A table like format**_.

Either an object with multiple same-length arrays, representing columns in a table,  giving the values and labels. Like below:

```javascript
// Objects with same length arrays all of which is its own column in a table
{
  "date": [
    "2022-03-01",
    "2022-03-01",
    "2022-04-01",
    "2022-04-01",
    "2022-04-01"
  ],
  "animal": ["dog", "cat", "frog", "cat", "dog"],
  "count": [4, 6, 10, 3, 2]
}
```

Or an array with tabular objects. So each object having matching properties like a table. Like below:

```javascript
// Array of objects with matching properties representing columns in a table
[
  { "date": "2022-03-01", "animal": "dog", "count": 4 },
  { "date": "2022-03-01", "animal": "cat", "count": 6 },
  { "date": "2022-04-01", "animal": "frog", "count": 10 },
  { "date": "2022-04-01", "animal": "cat", "count": 3 },
  { "date": "2022-04-01", "animal": "dog", "count": 2 }
]
```

#GeneralTools 
	#Retool 