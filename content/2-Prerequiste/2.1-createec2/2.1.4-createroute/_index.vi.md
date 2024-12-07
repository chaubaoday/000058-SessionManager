---
title : "Tạo các Route"
date :  "2024-12-05" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Tạo các Route
Routes là cách để gửi các yêu cầu API đến các tài nguyên backend. Một route bao gồm hai phần: phương thức HTTP và đường dẫn tài nguyên, ví dụ: GET /items. Đối với API ví dụ này, chúng ta tạo bốn route:

 + `GET /items/{id}URL` Value : {{% siteparam "editURL" %}}
 + `GET /itemsURL` Value : {{% siteparam "editURL" %}}
 + `PUT /itemsURL` Value : {{% siteparam "editURL" %}}
 + `DELETE /items/{id}URL` Value : {{% siteparam "editURL" %}}

#### Để tạo các route:

1. Đăng nhập vào [Bảng điều khiển API Gateway](https://console.aws.amazon.com/apigateway)

2. Chọn **API của bạn**

![VPC](/images/route/0001.png)

3. Chọn **Routes**.

4. Chọn **Create** 

![VPC](/images/route/0002.png)

5. Đối với **Method**, chọn **GET**.

6. Đối với Path, nhập`/items/{id}URL` Value : {{% siteparam "editURL" %}} . Phần {id} ở cuối đường dẫn là một tham số đường dẫn mà API Gateway sẽ lấy từ đường dẫn yêu cầu khi một khách hàng gửi yêu cầu.

7. Chọn **Create**

![VPC](/images/route/0003.png)

8. Repeat steps 4-7 for **GET /items, DELETE /items/{id}, and PUT /items**

![VPC](/images/route/0005.png.png)