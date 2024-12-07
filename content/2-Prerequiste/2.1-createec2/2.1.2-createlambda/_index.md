---
title : "Create a Lambda Function"
date :  "2024-12-05" 
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---


Create a Lambda function to handle the backend for your API, performing Create, Read, Update, and Delete (CRUD) operations on DynamoDB. The function uses events from API Gateway to determine the appropriate action. For simplicity, this guide uses a single function, though it's best practice to create separate functions for each route

#### Create a Lambda Function:
1.Log in to the [ Lambda Console](https://console.aws.amazon.com/lambda)
  + 2.Click **Create function**
  + 3.For **Function name**, enter **http-crud-tutorial-function**.
  
   ![VPC](/images/lambda/1.png)


  + 4.For **Runtime**, select the latest supported version of **Node.js** or **Python**.

  + 5.Under **Permissions**,click **Change default execution role**.

  ![VPC](/images/lambda/2.png)

  + 6.Choose **Create a new role from AWS policy templates**.
  + 7.For **Role name**,enter **http-crud-tutorial-role-demo**.

  + 8.For **Policy templates**,select **Simple microservice permissions**.To grant the Lambda function access to DynamoDB.
  + 9.Click **Create function**.

  ![VPC](/images/lambda/3.png)

  
  ![VPC](/images/lambda/4.png)

  + 10.Open the function in the code editor, replace its contents with the code below, and click Deploy to update the function.
  
  
```
import { DynamoDBClient } from "@aws-sdk/client-dynamodb";
import {
  DynamoDBDocumentClient,
  ScanCommand,
  PutCommand,
  GetCommand,
  DeleteCommand,
} from "@aws-sdk/lib-dynamodb";

const client = new DynamoDBClient({});

const dynamo = DynamoDBDocumentClient.from(client);

const tableName = "http-crud-tutorial-items";

export const handler = async (event, context) => {
  let body;
  let statusCode = 200;
  const headers = {
    "Content-Type": "application/json",
  };

  try {
    switch (event.routeKey) {
      case "DELETE /items/{id}":
        await dynamo.send(
          new DeleteCommand({
            TableName: tableName,
            Key: {
              id: event.pathParameters.id,
            },
          })
        );
        body = `Deleted item ${event.pathParameters.id}`;
        break;
      case "GET /items/{id}":
        body = await dynamo.send(
          new GetCommand({
            TableName: tableName,
            Key: {
              id: event.pathParameters.id,
            },
          })
        );
        body = body.Item;
        break;
      case "GET /items":
        body = await dynamo.send(
          new ScanCommand({ TableName: tableName })
        );
        body = body.Items;
        break;
      case "PUT /items":
        let requestJSON = JSON.parse(event.body);
        await dynamo.send(
          new PutCommand({
            TableName: tableName,
            Item: {
              id: requestJSON.id,
              price: requestJSON.price,
              name: requestJSON.name,
            },
          })
        );
        body = `Put item ${requestJSON.id}`;
        break;
      default:
        throw new Error(`Unsupported route: "${event.routeKey}"`);
    }
  } catch (err) {
    statusCode = 400;
    body = err.message;
  } finally {
    body = JSON.stringify(body);
  }

  return {
    statusCode,
    body,
    headers,
  };
};
```

![VPC](/images/lambda/5.png)

#### Lambda Function Successfully Created
![VPC](/images/lambda/6.png)