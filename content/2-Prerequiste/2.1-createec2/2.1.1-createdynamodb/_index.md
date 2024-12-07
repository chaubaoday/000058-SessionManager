---
title : "Create a DynamoDB table"
date : "2024-12-05"
weight : 1
chapter : false
pre : " <b> 2.1.1 </b> "
---

Here’s how to create a DynamoDB table for storing data for your API, with each item having a unique ID that will be used as the partition key for the table.

#### To create a DynamoDB table:

1. [Open the DynamoDB Console](https://console.aws.amazon.com/dynamodb)
  + Select **Create table**.

    ![VPC](/images/dynamodb/01.png)

  + For **Table name**, enter **http-crud-tutorial-items**.
  + For **Partition key**, enter **id**.

    ![VPC](/images/dynamodb/02.png)

  + Select **Create table**.

    ![VPC](/images/dynamodb/03.png)

#### Successfully created a DynamoDB table:

   ![VPC](/images/dynamodb/04.png)
    











