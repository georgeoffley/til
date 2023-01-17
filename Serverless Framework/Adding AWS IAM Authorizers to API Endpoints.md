# Adding AWS IAM Authorizers to API Endpoints

---
## Docs and Source
[Source Here](https://www.serverless.com/framework/docs/providers/aws/events/apigateway#http-endpoints-with-aws_iam-authorizers)

---
## Explanation and Notes
You can use the `authorizer` property in your `serverless.yml` to make the caller submit the IAM user’s access keys to authenticate before running a lambda.

You would do this by setting `authorizer: aws_iam` within the `http` block in the function.

For example, we used this to make it so that the caller of the endpoint needs to have the specified role in invoking the lambda. This will be used to make sure whoever is calling the admin endpoints for the partner service is authenticated to do so.

---


#serverless