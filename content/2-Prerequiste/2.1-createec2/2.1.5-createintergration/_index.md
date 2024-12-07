---
title : "Create an Integration"
date :  "2024-12-05" 
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

#### Create an Integration
To connect a route to a backend resource, you need to create an integration. In this example, you’ll configure a Lambda integration that handles all API routes. This integration ensures incoming requests are routed to the Lambda function for processing, making it the core of your API.

1.Log in to the [ API Gateway Console.](https://console.aws.amazon.com/apigateway).

2. Select **your API**

![VPC](/images/integration/in1.png)

3.Go to **Integrations**.

4. Click **Manage integrations**, then select **Create**

![VPC](/images/integration/in2.png)

5. Skip the option**Attach this integration to a route**. this will be done in the next step.

6. For **Integration type**, choose **Lambda function**.

7. In **Lambda function**, enter the name of your Lambda function `http-crud-tutorial-functionURL` Value : {{% siteparam "editURL" %}}

8. Click  **Create**.

![VPC](/images/integration/in3.png)