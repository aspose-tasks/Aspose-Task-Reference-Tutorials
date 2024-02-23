---
title: Lưu MS Project Options Primavera với Aspose.Tasks
linktitle: Tùy chọn lưu Primavera cho Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá cách lưu các tùy chọn MS Project cho Primavera một cách liền mạch bằng Aspose.Tasks for .NET. Thực hiện theo hướng dẫn từng bước của chúng tôi.
type: docs
weight: 14
url: /vi/net/saving-options/primavera-save-options/
---
## Giới thiệu
Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc liền mạch với các tệp Microsoft Project trong ứng dụng .NET của họ. Một trong những chức năng chính mà nó cung cấp là khả năng lưu các tùy chọn MS Project cho Primavera, một phần mềm quản lý dự án phổ biến. Trong hướng dẫn này, chúng ta sẽ đi sâu vào cách đạt được điều này bằng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Hiểu biết cơ bản về C# và .NET framework.
-  Aspose.Tasks cho .NET được cài đặt trong môi trường phát triển của bạn. Nếu không, bạn có thể tải xuống[đây](https://releases.aspose.com/tasks/net/).
- Một tệp MS Project mẫu để thử nghiệm.

## Nhập không gian tên
Trước tiên, hãy nhập các không gian tên cần thiết vào mã C# của chúng ta:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Bước 1: Tải tệp dự án MS
Bắt đầu bằng cách tải tệp MS Project mà bạn định làm việc vào ứng dụng C# của mình. Bạn có thể thực hiện việc này bằng cách sử dụng`Project` lớp được cung cấp bởi Aspose.Tasks.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Bước 2: Xác định tùy chọn lưu Primavera
Tiếp theo, tạo các tùy chọn lưu Primavera và tùy chỉnh chúng theo yêu cầu của bạn. Bước này liên quan đến việc chỉ định các tham số như tiền tố ID hoạt động, hậu tố, số gia và liệu có đánh số lại ID hoạt động hay không.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## Bước 3: Lưu tùy chọn dự án MS cho Primavera
 Bây giờ bạn đã tải tệp dự án và xác định các tùy chọn lưu Primavera, đã đến lúc lưu các tùy chọn cho Primavera. Sử dụng`Save` phương pháp được cung cấp bởi`Project` class, chuyển đường dẫn tệp đầu ra mong muốn và các tùy chọn lưu Primavera.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## Phần kết luận
Tóm lại, việc tận dụng Aspose.Tasks cho .NET cho phép các nhà phát triển thao tác liền mạch với các tệp MS Project, bao gồm các tùy chọn lưu cho Primavera. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp chức năng này một cách hiệu quả vào các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tùy chỉnh các tham số khác ngoài ID hoạt động khi lưu các tùy chọn MS Project cho Primavera không?
Trả lời: Có, Aspose.Tasks cung cấp nhiều tùy chọn để tùy chỉnh, bao gồm phân bổ tài nguyên và lập lịch tác vụ.
### Câu hỏi: Aspose.Tasks có hỗ trợ phần mềm quản lý dự án khác ngoài Primavera không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng khác nhau tương thích với các công cụ quản lý dự án phổ biến như Oracle Primavera, Microsoft Project Server, v.v.
### Câu hỏi: Aspose.Tasks có phù hợp cho cả dự án quy mô nhỏ và cấp doanh nghiệp không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks được thiết kế để đáp ứng nhu cầu của các nhà phát triển làm việc trên các dự án thuộc mọi quy mô, mang lại khả năng mở rộng và hiệu suất mạnh mẽ.
### Hỏi: Tôi có thể dùng thử Aspose.Tasks miễn phí trước khi mua hàng không?
 Trả lời: Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/) để khám phá các tính năng và khả năng của nó.
### Câu hỏi: Tôi có thể nhận hỗ trợ ở đâu nếu gặp sự cố hoặc có thắc mắc khi sử dụng Aspose.Tasks?
Trả lời: Bạn có thể tìm kiếm sự trợ giúp từ cộng đồng Aspose.Tasks và nhóm hỗ trợ trên[diễn đàn](https://forum.aspose.com/c/tasks/15).