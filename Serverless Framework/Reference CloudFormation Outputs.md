# Reference CloudFormation Outputs in Serverless

---
## Docs and Source
[Source Here](https://www.serverless.com/framework/docs/providers/aws/guide/variables#reference-cloudformation-outputs)

---
## Explanation and Notes
You can reference outputs from CloudFormation stacks using `${cf:another-service-dev.functionPrefix}-hello`. This lets us reference output from CloudFormation and use it to fill out dynamic string values.

---



#aws 
	#cloudformation 