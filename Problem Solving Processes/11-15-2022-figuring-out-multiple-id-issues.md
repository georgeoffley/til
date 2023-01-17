# Multiple ID Issues

### Project
Work Project

### Date
11/15/2022

### Technology
- AWS
- Serverless Framework

### The Problem

When creating this API endpoint, I ran into a bunch of issues. They broke down into two issues:
-   The `body` HTTP event was passing in as `null` for the API calls
-   I was getting a `resource not found` error when calling the endpoint.

### The Process
-   After coding up the logic, I sent some test user IDs over the API endpoint. I got errors saying that the window object was not defined. Which made no sense since nothing was using a `window` object
-   Continued testing until I figured out there was a weird import reaching out to something in the `node_modules` directory. Got rid of that.
-   Then noticed when sending stuff through the API I was getting a destructuring error. Looking through the code, I realized that I was using the a function we have for getting parameters out of URLs. I needed the function for getting information out of the `JSON` body of the message.
-   I was still getting those odd destructuring errors. So I put a `console.log()` message in the logic so I can see the request coming in. It turns out that the body of the HTTP message was coming up as null.
-   Turns out that serverless framework, for what reason I do not know, doesn’t accept body payloads for `GET` HTTP methods.
-   I looked forever for a solution until I finally gave up (as I spent at least two hours researching) and just switched it to `POST`.
-   So, after just focusing on getting everything working using a method I know works, I started getting errors from AWS saying the “resource was not found”
-   So I took a look at the [spec](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/DynamoDB/DocumentClient.html#batchGet-property) for the `batchGet()` function I was using from the AWS SDK.
-   They put the table names into the `RequestedItems` block for that function. So I put a string in there for the table name and was able to get the records back.

### Solution
Final code looked like this:

```JavaScript
const readMultipleUsers = async ({usersTableName, docClient, Ids}) => {
  const rtnUsers = [];

  // Set up query params
  const usrKeys = [];
  Ids.map((id) => {
    usrKeys.push({"id": id});
  })

  const res = await docClient
  .batchGet({
    RequestItems: {
      [usersTableName]: {
        Keys: usrKeys,
      }
    }
  })
  .promise();

  res.Responses[usersTableName].forEach((item) => rtnUsers.push(item));

  return rtnUsers;
}
  }
```



#ProblemSolving