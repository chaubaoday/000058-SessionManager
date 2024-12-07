+++
title = "Dọn dẹp tài nguyên  "
date = 2021
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

Để tránh các chi phí không cần thiết, hãy xóa các tài nguyên mà bạn đã tạo trong quá trình bài tập bắt đầu này. Các bước sau đây sẽ xóa HTTP API, hàm Lambda và các tài nguyên liên quan.

### Để xóa bảng DynamoDB:

1. Mở [bảng điều khiển DynamoDB](https://console.aws.amazon.com/dynamodb/).

 + Chọn bảng của bạn.

 + Chọn **Delete table**.

 + Xác nhận lựa chọn của bạn và chọn **Delete**

 ![VPC](/images/delete/d1.png)

 ![VPC](/images/delete/d2.png)

#### Để xóa một HTTP API:

2. Đăng nhập vào [bảng điều khiển API Gateway](https://console.aws.amazon.com/apigateway).

 + Trên trang **APIs**, chọn một **API**. Chọn **Actions**, sau đó chọn **Delete**.

 + Chọn **Delete**.

 ![VPC](/images/delete/d4.png)

 ![VPC](/images/delete/d5.png)

#### Để xóa một hàm Lambda:

3. Đăng nhập vào [bảng điều khiển Lambda](https://console.aws.amazon.com/lambda).

 + Trên trang **Functions**, chọn một **hàm**. Chọn **Actions**, sau đó chọn **Delete**.

 + Chọn **Delete**.

 ![VPC](/images/delete/d6.png)

 ![VPC](/images/delete/d7.png)


#### Để xóa vai trò thực thi của hàm Lambda:

4. Trong [bảng điều khiển AWS Identity and Access Management], mở trang Roles.

 + Chọn vai trò của hàm, ví dụ, **http-crud-tutorial-role.**

 + Chọn **Delete role**.

 + Chọn Yes, **delete**

 ![VPC](/images/delete/d8.png)

 ![VPC](/images/delete/d9.png)



