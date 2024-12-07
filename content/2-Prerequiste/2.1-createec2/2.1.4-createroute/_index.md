---
title : "Create Routes"
date :  "2024-12-05" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Create Routes
Routes define how API requests are sent to backend resources. A route consists of an HTTP method and a resource path, such as GET /items. For this example, we’ll create four routes

 + `GET /items/{id}URL` Value : {{% siteparam "editURL" %}}
 + `GET /itemsURL` Value : {{% siteparam "editURL" %}}
 + `PUT /itemsURL` Value : {{% siteparam "editURL" %}}
 + `DELETE /items/{id}URL` Value : {{% siteparam "editURL" %}}

#### Steps to Create Routes

1. Login to the [API Gateway Console](https://console.aws.amazon.com/apigateway)

2. Select **your API**

![VPC](/images/route/0001.png)

3. Go to **Routes**

4. Click **Create**

![VPC](/images/route/0002.png)

5. For **Method**, choose **GET**.

6. For Path, enter`/items/{id}URL` Value : {{% siteparam "editURL" %}} . The {id} part is a path parameter that API Gateway will extract from the request URL.

7. Click **Create**

![VPC](/images/route/0003.png)

8. Repeat steps 4-7 for **GET /items, DELETE /items/{id}, and PUT /items**

![VPC](/images/route/0005.png.png)