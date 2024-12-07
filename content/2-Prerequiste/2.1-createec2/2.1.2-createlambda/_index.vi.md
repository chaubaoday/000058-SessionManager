---
title : "Tạo hàm Lambda"
date :  "2024-12-05" 
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---


Tạo một hàm Lambda để xử lý backend cho API, thực hiện các thao tác Tạo, Đọc, Cập nhật và Xóa (CRUD) trên DynamoDB. Hàm này sử dụng sự kiện từ API Gateway để xác định hành động phù hợp. Để đơn giản, hướng dẫn này sử dụng một hàm duy nhất, nhưng theo nguyên tắc tốt nhất, bạn nên tạo các hàm riêng cho từng route.

#### Tạo hàm Lambda:
1.Đăng nhập vào [Bảng điều khiển Lambda](https://console.aws.amazon.com/lambda)
  + 2.Chọn **Create function**
  + 3.Đối với Function name, nhập **http-crud-tutorial-function**.
  
   ![VPC](/images/lambda/1.png)


  + 4.Đối với **Runtime**, chọn **Node.js** hoặc **Python phiên bản mới nhất** được hỗ trợ.

  + 5.Dưới **Permissions**, chọn **Change default execution role**.

  ![VPC](/images/lambda/2.png)

  + 6.Chọn **Create a new role from AWS policy templates**.
  + 7.Đối với **Role name**, nhập **http-crud-tutorial-role-demo**.

  + 8.Đối với **Policy templates**, chọn **Simple microservice permissions**. Chính sách này cấp quyền cho hàm Lambda để tương tác với DynamoDB.

  + 9.Chọn **Create function**.

  ![VPC](/images/lambda/3.png)

  
  ![VPC](/images/lambda/4.png)

  + 10.Mở hàm Lambda trong trình chỉnh sửa mã của bảng điều khiển, và thay thế nội dung hiện tại bằng mã sau. Chọn Deploy để cập nhật hàm của bạn.
  
  
```
import { DynamoDBClient } from "@aws-sdk/client-dynamodb";
import {
  DynamoDBDocumentClient,
  ScanCommand,
  PutCommand,
  GetCommand,
  DeleteCommand,
} from "@aws-sdk/lib-dynamodb";

const client = new DynamoDBClient({});

const dynamo = DynamoDBDocumentClient.from(client);

const tableName = "http-crud-tutorial-items";

export const handler = async (event, context) => {
  let body;
  let statusCode = 200;
  const headers = {
    "Content-Type": "application/json",
  };

  try {
    switch (event.routeKey) {
      case "DELETE /items/{id}":
        await dynamo.send(
          new DeleteCommand({
            TableName: tableName,
            Key: {
              id: event.pathParameters.id,
            },
          })
        );
        body = `Deleted item ${event.pathParameters.id}`;
        break;
      case "GET /items/{id}":
        body = await dynamo.send(
          new GetCommand({
            TableName: tableName,
            Key: {
              id: event.pathParameters.id,
            },
          })
        );
        body = body.Item;
        break;
      case "GET /items":
        body = await dynamo.send(
          new ScanCommand({ TableName: tableName })
        );
        body = body.Items;
        break;
      case "PUT /items":
        let requestJSON = JSON.parse(event.body);
        await dynamo.send(
          new PutCommand({
            TableName: tableName,
            Item: {
              id: requestJSON.id,
              price: requestJSON.price,
              name: requestJSON.name,
            },
          })
        );
        body = `Put item ${requestJSON.id}`;
        break;
      default:
        throw new Error(`Unsupported route: "${event.routeKey}"`);
    }
  } catch (err) {
    statusCode = 400;
    body = err.message;
  } finally {
    body = JSON.stringify(body);
  }

  return {
    statusCode,
    body,
    headers,
  };
};
```

![VPC](/images/lambda/5.png)

#### Tạo thành công hàm Lambda
![VPC](/images/lambda/6.png)