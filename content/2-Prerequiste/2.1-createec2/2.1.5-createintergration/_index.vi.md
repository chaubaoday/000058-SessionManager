---
title : "Tạo một Tích hợp (Integration)"
date :  "2024-12-05" 
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

#### Tạo một Tích hợp (Integration)
Để kết nối một route với tài nguyên backend, bạn cần tạo một tích hợp. Trong ví dụ này, bạn sẽ thiết lập một tích hợp Lambda dùng chung cho tất cả các route trong API. Tích hợp này đảm bảo rằng các yêu cầu gửi đến sẽ được chuyển đến hàm Lambda để xử lý, trở thành trung tâm hoạt động của API.

1. Đăng nhập vào [Bảng điều khiển API Gateway](https://console.aws.amazon.com/apigateway).

2. Chọn **API của bạn**

![VPC](/images/integration/in1.png)

3. Chọn **Integrations**.

4. Chọn  **Manage integrations**, sau đó chọn **Create**

![VPC](/images/integration/in2.png)

5. Bỏ qua **Attach this integration to a route**. Bạn sẽ hoàn thành việc này trong bước sau.

6. Đối với **Integration type**, chọn **Lambda function**.

7. Đối với **Lambda function**, nhập .`http-crud-tutorial-functionURL` Value : {{% siteparam "editURL" %}}

8. Chọn **Create**.

![VPC](/images/integration/in3.png)