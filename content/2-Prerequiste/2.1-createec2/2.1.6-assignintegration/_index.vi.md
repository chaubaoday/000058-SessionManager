---
title : "Gán Tích hợp vào Các Route"
date :  "2024-12-05" 
weight : 6
chapter : false
pre : " <b> 2.1.6 </b> "
---

Đối với API ví dụ này, bạn sử dụng cùng một tích hợp Lambda cho tất cả các route. Sau khi gán tích hợp cho tất cả các route của API, hàm Lambda của bạn sẽ được gọi khi một khách hàng gọi bất kỳ route nào của bạn.

#### Để gán tích hợp vào các route:

1. Đăng nhập vào [Bảng điều khiển API Gateway](https://console.aws.amazon.com/apigateway).

2. Chọn **API của bạn**.

3. Chọn **Integrations**.

4. Chọn **một route**.

5. Dưới **Choose an existing integration**, chọn `http-crud-tutorial-functionURL` Value : {{% siteparam "editURL" %}}.

6. Chọn **Attach integration**.

![VPC](/images/assignintegration/in5.png)

![VPC](/images/assignintegration/in6.png)

![VPC](/images/assignintegration/in7.png)

7. **Lặp lại các bước 4-6 cho tất cả các route**

![VPC](/images/assignintegration/in8.png)
