---
title: Tỷ lệ dự án MS chính với Aspose.Tasks
linktitle: Bộ sưu tập mức giá trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý tỷ lệ trong tệp MS Project bằng Aspose.Tasks cho .NET. Hướng dẫn từng bước để quản lý tài nguyên hiệu quả.
weight: 11
url: /vi/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tỷ lệ dự án MS chính với Aspose.Tasks

## Giới thiệu
Chào mừng bạn đến với hướng dẫn của chúng tôi về cách quản lý tỷ lệ trong MS Project bằng Aspose.Tasks for .NET! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình làm việc với các mức giá trong tệp MS Project của bạn bằng Aspose.Tasks. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu phát triển .NET, hướng dẫn này sẽ cung cấp cho bạn hướng dẫn từng bước để xử lý hiệu quả các tỷ lệ trong dự án của bạn.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
### 1. Đã cài đặt Visual Studio
Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình. Bạn có thể tải xuống từ trang web nếu bạn chưa có.
### 2. Aspose.Tasks cho .NET
 Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[trang mạng](https://releases.aspose.com/tasks/net/).
### 3. Kiến thức cơ bản về C# và .NET
Làm quen với ngôn ngữ lập trình C# và kiến thức cơ bản về .NET framework để hiểu rõ hơn về các ví dụ mã được cung cấp trong hướng dẫn này.
## Nhập không gian tên
Trong dự án C# của bạn, hãy nhập các vùng tên cần thiết để sử dụng các chức năng của Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Bây giờ, hãy chia từng ví dụ thành nhiều bước:
## Bước 1: Tải tệp dự án MS
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Ở đây chúng ta tạo một cái mới`Project` đối tượng bằng cách tải tệp MS Project hiện có.
## Bước 2: Thêm tài nguyên và đặt công việc cũng như mức giá
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Chúng tôi thêm tài nguyên mới vào dự án, đặt loại của nó là công việc, số lượng công việc và tỷ lệ tiêu chuẩn.
## Bước 3: Thêm giá vào tài nguyên
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Chúng tôi thêm mức giá vào tài nguyên chỉ định ngày bắt đầu và ngày kết thúc, mức giá tiêu chuẩn và định dạng mức giá.
## Bước 4: In thông tin về giá
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Bước này in thông tin về tỷ lệ liên quan đến tài nguyên.
## Bước 5: Cập nhật tỷ giá
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Chúng tôi cập nhật ngày kết thúc của một mức giá cụ thể.
## Bước 6: Xóa giá
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Bước này loại bỏ tất cả các mức giá của một loại cụ thể.
## Bước 7: Lặp lại các tỷ lệ còn lại
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Cuối cùng, chúng tôi lặp lại các tỷ lệ còn lại sau khi loại bỏ.
## Phần kết luận
Tóm lại, hướng dẫn này đã cung cấp cho bạn hướng dẫn toàn diện về cách quản lý tỷ lệ trong tệp MS Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo hướng dẫn từng bước được nêu trong hướng dẫn này, bạn có thể xử lý hiệu quả các tỷ lệ trong dự án của mình, đảm bảo quản lý tài nguyên chính xác.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với phần mềm quản lý dự án khác không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ tích hợp với nhiều phần mềm quản lý dự án khác nhau, bao gồm MS Project, Primavera, v.v.
### Câu hỏi: Aspose.Tasks dành cho .NET có tương thích với các phiên bản khác nhau của tệp MS Project không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks for .NET hỗ trợ làm việc với các tệp MS Project thuộc nhiều phiên bản khác nhau, đảm bảo tính linh hoạt và khả năng tương thích.
### Câu hỏi: Aspose.Tasks dành cho .NET có cung cấp tài liệu và hỗ trợ không?
 Trả lời: Có, bạn có thể tìm thấy tài liệu toàn diện và quyền truy cập vào các diễn đàn hỗ trợ trên Aspose.Tasks[trang mạng](https://reference.aspose.com/tasks/net/).
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks cho .NET trước khi mua không?
Trả lời: Có, bạn có thể sử dụng bản dùng thử miễn phí Aspose.Tasks dành cho .NET để đánh giá các tính năng và khả năng tương thích của nó với yêu cầu của bạn.
### Câu hỏi: Làm cách nào tôi có thể mua giấy phép Aspose.Tasks cho .NET?
 Trả lời: Bạn có thể mua giấy phép Aspose.Tasks cho .NET từ[trang mạng](https://purchase.aspose.com/temporary-license/)cung cấp các tùy chọn cấp phép linh hoạt phù hợp với nhu cầu của bạn.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
