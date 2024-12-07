---
title : "Tạo bảng DynamoDB "
date :  "2024-12-05" 
weight : 1 
chapter : false
pre : " <b> 2.1.1 </b> "
---

Bạn sẽ sử dụng một bảng DynamoDB để lưu trữ dữ liệu cho API của mình. Mỗi mục sẽ có một ID duy nhất, mà chúng ta sẽ sử dụng làm khóa phân vùng (partition key) cho bảng.

#### Để tạo một bảng DynamoDB:
1. Mở [bảng điều khiển DynamoDB ](https://console.aws.amazon.com/dynamodb)
  + Chọn **Create table**.

   ![VPC](/images/dynamodb/01.png)

  + Đối với **Table name**, nhập **http-crud-tutorial-items**.
  + Đối với **Partition key**, nhập **id**.

   ![VPC](/images/dynamodb/02.png)

  + Chọn **Create table**.

   ![VPC](/images/dynamodb/03.png)

#### Tạo thành công một bảng DynamoDB:

   ![VPC](/images/dynamodb/04.png)




