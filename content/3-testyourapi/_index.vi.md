---
title : "Kiểm tra API của bạn"
date :  "2024-12-05" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

Để đảm bảo rằng API của bạn đang hoạt động, bạn sử dụng `curlURL` Value : {{% siteparam "editURL" %}}.

Để lấy URL để gọi API của bạn:

 1. Đăng nhập vào [bảng điều khiển API Gateway](https://console.aws.amazon.com/apigateway).

 2. Chọn **API** của bạn.

 3. Ghi lại **URL gọi API** của bạn. Nó xuất hiện dưới **Invoke URL** trên trang **Details**.

 ![VPC](/images/check_api/c1.png)

 4. Sao chép URL gọi API của bạn. URL đầy đủ trông giống như ` https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/URL` Value : {{% siteparam "editURL" %}}

#### Để tạo hoặc cập nhật một mục:

 + Sử dụng lệnh sau để tạo hoặc cập nhật một mục. Lệnh này bao gồm một body yêu cầu với ID, giá, và tên của mục.
 ```
 curl -X "PUT" -H "Content-Type: application/json" -d "{\"id\": \"123\", \"price\": 12345, \"name\": \"myitem\"}" https://f5abcd. execute-api.ap-southeast-1.amazonaws.com/ 
 ```

#### Để lấy tất cả các mục:

 + Sử dụng lệnh sau để liệt kê tất cả các mục.

 ```
 curl https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/items
 ```

#### Để lấy một mục:

 + Sử dụng lệnh sau để lấy một mục theo ID của nó
 ```
 curl https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/items/123
 ```

#### Để xóa một mục:

 + Sử dụng lệnh sau để xóa một mục.
 ```
 curl -X "DELETE" https://f5abcd.execute-api.ap-southeast-1.amazonaws.com/items/123
 ```
 
