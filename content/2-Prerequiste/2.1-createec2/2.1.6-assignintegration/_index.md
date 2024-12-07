---
title : "Assign Integrations to Routes"
date :  "2024-12-05" 
weight : 6
chapter : false
pre : " <b> 2.1.6 </b> "
---

In this example, you’ll use the same Lambda integration for all routes. Once the integration is assigned to each route, the Lambda function will be invoked whenever a request is made to your API

#### Steps to Assign Integrations to Routes:

1.Log in to the [API Gateway Console.](https://console.aws.amazon.com/apigateway).

2. Select **your API**.

3. Choose **Routes** from the left menu.

4. Select **a route to assign the integration**.

5. Under **Choose an existing integration**,select the Lambda function`http-crud-tutorial-functionURL` Value : {{% siteparam "editURL" %}}.

6.Click **Attach integration**.

![VPC](/images/assignintegration/in5.png)

![VPC](/images/assignintegration/in6.png)

![VPC](/images/assignintegration/in7.png)

7. **Repeat steps 4-6 for all routes**

![VPC](/images/assignintegration/in8.png)
