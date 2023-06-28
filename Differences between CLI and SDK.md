# Differences between CLI and SDK
---
## Explanation and Notes
Remember that you need to test your operation using the AWS CLI. Just remember that when you write out the expression using the Node SDK, you must omit the dictionary the CLI uses.

CLI: 
```Bash
aws dynamodb query \
--table-name bank-integration-service-data-internal-sandbox \
--key-condition-expression "#pk = :pk" \
--expression-attribute-names '{
    "#pk": "partition"
}'\
--expression-attribute-values '{
    ":pk": { "S": "account#fbo" }
}' \
$LOCAL
```
SDK Code:
```JavaScript
ddbClient.query({
	TableName: tableName,
	KeyConditionExpression: '#pk = :pk',
	ExpressionAttributeNames: {
	  '#pk': 'partition'
	},
	ExpressionAttributeValues: {
	  ':pk': 'partition#value'
	},
});
```

#aws
	#dynamodb