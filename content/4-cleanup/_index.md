+++
title = "Clean Up Resources  "
date = 2021
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

To avoid unnecessary costs, delete the resources you created during this exercise. The following steps will remove the HTTP API, Lambda function, and related resources.

### Delete the DynamoDB Table

1. Go to the [ DynamoDB Console](https://console.aws.amazon.com/dynamodb/).

 + Select your **table**.

 + Click  **Delete table**.

 + Confirm your choice by clicking **Delete**

 ![VPC](/images/delete/d1.png)

 ![VPC](/images/delete/d2.png)

#### Delete the HTTP API

2. Log in to the [API Gateway Console](https://console.aws.amazon.com/apigateway).

 + On the **APIs**,  page, select your **API**. 
 + Click **Actions**, then select**Delete**.

 + Confirm by selecting **Delete**.

 ![VPC](/images/delete/d4.png)

 ![VPC](/images/delete/d5.png)

#### Delete the Lambda Function

3. Go to the [ Lambda Console](https://console.aws.amazon.com/lambda).

 + On the**Functions**, page, select your **function**.Click **Actions**, then select **Delete**.

 + Confirm by selecting **Delete**.

 ![VPC](/images/delete/d6.png)

 ![VPC](/images/delete/d7.png)


#### Delete the Lambda Execution Role

4. Open the [AWS IAM Console](https://us-east-1.console.aws.amazon.com/iam/home#/home)

 + Go to **Roles and select the Lambda role**, for example, **http-crud-tutorial-role**.

 + Click **Delete role**.

 + Confirm by selecting, **delete**

 ![VPC](/images/delete/d8.png)

 ![VPC](/images/delete/d9.png)



