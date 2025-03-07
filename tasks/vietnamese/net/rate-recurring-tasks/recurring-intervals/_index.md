---
title: Khoảng thời gian định kỳ dự án MS dễ dàng trong Aspose.Tasks
linktitle: Quản lý khoảng thời gian định kỳ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá cách quản lý dễ dàng các khoảng thời gian định kỳ trong MS Project bằng cách sử dụng Aspose.Tasks for .NET.
weight: 12
url: /vi/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Khoảng thời gian định kỳ dự án MS dễ dàng trong Aspose.Tasks

## Giới thiệu
Bạn đang tìm cách quản lý các khoảng thời gian định kỳ một cách hiệu quả trong các tệp Microsoft Project bằng Aspose.Tasks cho .NET? Hướng dẫn toàn diện này sẽ hướng dẫn bạn từng bước thực hiện quy trình, đảm bảo bạn có thể dễ dàng xử lý các khoảng thời gian định kỳ trong dự án của mình. Trước khi đi sâu vào phần hướng dẫn, chúng ta hãy điểm qua một số điều kiện tiên quyết để đảm bảo bạn đã sẵn sàng bắt đầu.
## Điều kiện tiên quyết
Trước khi tiếp tục với hướng dẫn này, hãy đảm bảo bạn có những điều sau:
1. Kiến thức về lập trình C#: Cần có hiểu biết cơ bản về ngôn ngữ lập trình C# và cú pháp của nó.
2. Đã cài đặt Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình để mã hóa và biên dịch các ứng dụng .NET.
3. Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET. Bạn có thể lấy nó từ[đây](https://releases.aspose.com/tasks/net/).

## Nhập không gian tên
Bắt đầu bằng cách nhập các không gian tên cần thiết để truy cập các chức năng do thư viện Aspose.Tasks for .NET cung cấp.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Bây giờ, hãy chia từng ví dụ thành nhiều bước và giải thích chúng một cách chi tiết.
## Bước 1: Khởi tạo đối tượng dự án:
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Ở đây, chúng ta khởi tạo một phiên bản mới của`Project` lớp bằng cách cung cấp đường dẫn đến tệp Microsoft Project.
## Bước 2: Đặt ngày trạng thái:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Bước này đặt ngày trạng thái của dự án thành ngày bắt đầu.
## Bước 3: Truy cập Chế độ xem biểu đồ Gantt:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Chúng tôi truy cập vào chế độ xem Biểu đồ Gantt của dự án.
## Bước 4: Đọc Dòng tiến trình:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Bước này truy xuất khoảng thời gian định kỳ cho các dòng tiến trình từ chế độ xem Biểu đồ Gantt.
## Bước 5: Hiển thị thông tin khoảng thời gian:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Tại đây, chúng tôi hiển thị thông tin về khoảng thời gian, số tuần hàng tuần và ngày hàng tuần.
## Bước 6: Xác định lại khoảng thời gian định kỳ:
```csharp
var newInterval = new RecurringInterval();
```
 Chúng tôi tạo một phiên bản mới của`RecurringInterval` để xác định lại khoảng thời gian định kỳ.
## Bước 7: Đặt dòng tiến độ hàng tháng:
```csharp
// Đặt dòng tiến độ hàng tháng theo ngày.
interval.MonthlyDay = true;
// Đặt số ngày của dòng tiến độ hàng tháng.
interval.MonthlyDayDayNumber = 1;
// Đặt số tháng của dòng tiến độ hàng tháng.
interval.MonthlyDayMonthNumber = 1;
// Đặt các dòng tiến độ theo ngày được xác định trước đầu tiên hoặc cuối cùng.
interval.MonthlyFirstLast = true;
// Đặt loại dòng tiến độ hàng tháng của ngày đầu tiên hoặc ngày cuối cùng.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Đặt số dòng tiến trình trong tháng.
interval.MonthlyFirstLastMonthNumber = 1;
```
Các bước này định cấu hình các dòng tiến trình hàng tháng theo các tham số đã chỉ định.
## Bước 8: Cập nhật dòng tiến độ:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Chúng tôi cập nhật các dòng tiến trình trong chế độ xem Biểu đồ Gantt với khoảng thời gian định kỳ mới được xác định.
## Bước 9: Lưu dự án dưới dạng PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Cuối cùng, chúng tôi lưu dự án với khoảng thời gian định kỳ được cập nhật dưới dạng tệp PDF.

## Phần kết luận
Tóm lại, việc quản lý các khoảng thời gian định kỳ trong các tệp Microsoft Project bằng Aspose.Tasks cho .NET được thực hiện đơn giản với các chức năng toàn diện do thư viện cung cấp. Bằng cách làm theo hướng dẫn từng bước được nêu trong hướng dẫn này, bạn có thể xử lý hiệu quả các khoảng thời gian định kỳ trong dự án của mình, nâng cao năng suất và tổ chức.
### Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho .NET với các ngôn ngữ lập trình khác không?
Có, Aspose.Tasks for .NET có thể được sử dụng với bất kỳ ngôn ngữ nào được .NET hỗ trợ như C# và VB.NET.
### Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?
 Bạn có thể nhận hỗ trợ từ diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho .NET không?
 Có, bạn có thể mua giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm tài liệu đầy đủ về Aspose.Tasks cho .NET ở đâu?
 Các tài liệu đầy đủ có thể được tìm thấy[đây](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
