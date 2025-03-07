---
title: Xử lý tỷ lệ dự án MS bằng Aspose.Tasks cho .NET
linktitle: Xử lý tỷ lệ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Quản lý thành thạo Tỷ lệ dự án MS một cách dễ dàng bằng cách sử dụng Aspose.Tasks cho .NET. Tự động hóa các tác vụ một cách hiệu quả để quy trình làm việc của dự án trôi chảy hơn.
weight: 10
url: /vi/net/rate-recurring-tasks/handling-rates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xử lý tỷ lệ dự án MS bằng Aspose.Tasks cho .NET

## Giới thiệu
Chào mừng bạn đến với hướng dẫn của chúng tôi về cách xử lý Giá dự án MS bằng Aspose.Tasks cho .NET! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình, đảm bảo bạn có thể quản lý tỷ lệ một cách hiệu quả trong các tài liệu MS Project của mình. Aspose.Tasks for .NET cung cấp các tính năng mạnh mẽ để thao tác các tệp MS Project theo chương trình, cho phép bạn hợp lý hóa các tác vụ quản lý dự án của mình một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1. Đã cài đặt Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình.
2.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về C#: Làm quen với các nguyên tắc cơ bản của ngôn ngữ lập trình C#.
## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết vào dự án C# của mình. Các không gian tên này sẽ cung cấp quyền truy cập vào các lớp và phương thức cần thiết để xử lý Giá dự án MS.
## Bước 1: Nhập không gian tên Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước và hiểu kỹ từng bước.
## Bước 1: Tải tệp dự án
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Trong bước này, chúng tôi đang tải tệp MS Project hiện có có tên "Project1.mpp" bằng cách sử dụng`Project` lớp được cung cấp bởi Aspose.Tasks.
## Bước 2: Thêm tài nguyên và đặt công việc
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Ở đây, chúng tôi thêm một tài nguyên mới có tên "Tài nguyên 1" vào dự án và đặt loại của nó là "Công việc". Chúng tôi cũng xác định thời lượng làm việc cho tài nguyên này.
## Bước 3: Đặt giá tiêu chuẩn
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Ở bước này, chúng tôi đặt mức giá tiêu chuẩn cho nguồn lực là 20 USD/giờ.
## Bước 4: Xác định khoảng thời gian tính lãi
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Ở đây, chúng tôi xác định khoảng thời gian đánh giá cho tài nguyên. Mức 1 được ấn định từ ngày 1 tháng 1 năm 2019 đến ngày 11 tháng 11 năm 2019, với mức tiêu chuẩn và mức làm thêm giờ được chỉ định cụ thể.
## Bước 5: Thêm Kỳ Tính Giá Khác
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Trong bước cuối cùng này, chúng tôi thêm một khoảng thời gian tính giá khác bắt đầu từ ngày 12 tháng 11 năm 2019 đến ngày 31 tháng 12 năm 2019, với mức giá tiêu chuẩn khác và chi phí cho mỗi lần sử dụng được xác định.
Chúc mừng! Bạn đã xử lý thành công Giá dự án MS bằng Aspose.Tasks cho .NET.
## Phần kết luận
Quản lý Giá dự án MS theo chương trình có thể nâng cao đáng kể quy trình quản lý dự án của bạn. Với Aspose.Tasks cho .NET, bạn có khả năng tự động hóa các tác vụ xử lý tốc độ một cách hiệu quả, tiết kiệm thời gian và tài nguyên.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có thể xử lý các cấu trúc dự án phức tạp không?
Trả lời: Có, Aspose.Tasks cung cấp các tính năng mạnh mẽ để xử lý các cấu trúc dự án phức tạp một cách dễ dàng.
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản của tệp MS Project không?
Trả lời: Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp MS Project, đảm bảo khả năng tương thích trên các nền tảng khác nhau.
### Câu hỏi: Tôi có thể sửa đổi các mức giá hiện có trong tệp MS Project bằng Aspose.Tasks không?
Đ: Chắc chắn rồi! Aspose.Tasks cho phép bạn sửa đổi các mức giá hiện có, thêm các mức giá mới và quản lý chúng một cách linh hoạt.
### Câu hỏi: Aspose.Tasks có hỗ trợ tính toán tỷ lệ tùy chỉnh không?
Trả lời: Có, bạn có thể triển khai tính toán tỷ lệ tùy chỉnh bằng Aspose.Tasks để đáp ứng các yêu cầu cụ thể của dự án.
### Câu hỏi: Có diễn đàn cộng đồng hoặc hỗ trợ nào dành cho người dùng Aspose.Tasks không?
 Đ: Có, bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15)để tìm kiếm sự trợ giúp và tương tác với những người dùng khác.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
