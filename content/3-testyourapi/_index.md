---
title : "Test Your API"
date :  "2024-12-05" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

To ensure your API is working correctly `curlURL` Value : {{% siteparam "editURL" %}}commands to interact with it.

#### Steps to Retrieve the API URL

 1. Log in to the[ API Gateway Console](https://console.aws.amazon.com/apigateway).

 2. Select **your API**.

 3. Note the **URL gọi API** của bạn. displayed on the **Details page**

 ![VPC](/images/check_api/c1.png)

 4.Copy the full API Invoke URL. It should look like:  ` https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/URL` Value : {{% siteparam "editURL" %}}

#### Create or Update an Item:

 + Use the following command to create or update an item. This command sends a request body with an ID, price, and name
 ```
 curl -X "PUT" -H "Content-Type: application/json" -d "{\"id\": \"123\", \"price\": 12345, \"name\": \"myitem\"}" https://f5abcd. execute-api.ap-southeast-1.amazonaws.com/ 
 ```

#### Retrieve All Items:

 + Use this command to list all items.

 ```
 curl https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/items
 ```

#### Retrieve a Single Item by ID:

 + Use this command to get a specific item by its ID
 ```
 curl https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/items/123
 ```

#### Delete an Item:

 + Use this command to delete an item by its ID.
 ```
 curl -X "DELETE" https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/items/123
 ```
 
