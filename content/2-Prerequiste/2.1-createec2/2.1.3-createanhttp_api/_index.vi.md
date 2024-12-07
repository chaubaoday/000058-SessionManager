---
title : "Tạo một API HTTP"
date :  "2024-12-05" 
weight : 3
chapter : false
pre : " <b> 2.1.3 </b> "
---

API HTTP cung cấp một điểm cuối HTTP cho hàm Lambda của bạn. Trong bước này, bạn sẽ tạo một API trống. Trong các bước tiếp theo, bạn sẽ cấu hình các route và tích hợp để kết nối API của bạn với hàm Lambda.

#### Tạo một API HTTP

1. Đăng nhập vào [Bảng điều khiển API Gateway ](https://console.aws.amazon.com/apigateway)

2. Chọn **Create API**, và sau đó đối với **HTTP API**, chọn **Build**.

![VPC](/images/api_http/001.png)

3. Đối với **API name**, nhập **http-crud-tutorial-api-demo**.

4. Chọn **Next**.

![VPC](/images/api_http/002.png)

5. Đối với **Configure routes**, chọn **Next** để bỏ qua việc tạo route. Bạn sẽ tạo các route sau

![VPC](/images/api_http/003.png)

6. Xem xét giai đoạn mà **API Gateway** tạo cho bạn, sau đó chọn **Next**

![VPC](/images/api_http/004.png)

7. Chọn **Create**.

![VPC](/images/api_http/005.png)

#### Tạo một API HTTP thành công:

![VPC](/images/api_http/006.png)