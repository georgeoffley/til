# Query Operation for DynamoDB Document Client Class

---
## Docs and Source

[CLI Docs for Query](https://docs.aws.amazon.com/cli/latest/reference/dynamodb/query.html)
[Node SDK Query Docs](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/DynamoDB/DocumentClient.html#query-property)

---
## Explanation and Notes

The `KeyConditionExpression` ”specifies the key values for items to be retrieved by the `Query` action.”

This is what performs an equality test on a single partition key value. So in my case, I used this to search the `partition` field.

The `ExpressionAttributeNames` is a field where you can map the names of the fields you’re querying. So in my case, I used this to map the `#pk` value to the `partition` field. This replaces the `#pk` value with `partition` at run time. This is required because `partition` is a reserved keyword in DynamoDB. There are a ton of reserved keywords so this is an important thing to remember.

The `ExpressionAttributesValues` field maps the `:pk` value to the value you need in the `KeyConditionExpression` field. In my case, I used it to map the `:pk` value to the `partition#value` value.

---
## Code Example

```JavaScript
ddbClient.query({
	TableName: tableName,
	KeyConditionExpression: '#pk = :pk',
	ExpressionAttributeNames: {
	  '#pk': 'partition'
	},
	ExpressionAttributeValues: {
	  ':pk': 'account#fbo'
	},
});
```


#aws 
	#dynamodb 