---
title: Nắm vững thời gian làm việc trong Aspose.Tasks
linktitle: Bộ sưu tập Thời gian làm việc trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá sức mạnh của Aspose.Tasks dành cho .NET trong việc quản lý các mốc thời gian của dự án một cách hiệu quả. Tùy chỉnh lịch, đặt thời gian làm việc và hợp lý hóa các dự án của bạn một cách dễ dàng.
type: docs
weight: 14
url: /vi/net/time-recurrence-configuration/working-time-collection/
---
## Giới thiệu
Bạn đang muốn nắm vững nghệ thuật quản lý thời gian làm việc trong Aspose.Tasks cho .NET? Đừng tìm đâu xa! Trong hướng dẫn từng bước này, chúng ta sẽ đi sâu vào những điểm phức tạp của việc thu thập thời gian làm việc bằng Aspose.Tasks, giúp bạn xử lý lịch tùy chỉnh một cách hiệu quả và hợp lý hóa các mốc thời gian dự án của mình.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu cuộc hành trình này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[Trang phát hành Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Môi trường làm việc: Thiết lập môi trường phát triển phù hợp, tốt nhất là sử dụng IDE tương thích .NET.
## Nhập không gian tên
Trong dự án của bạn, hãy nhập các không gian tên cần thiết để truy cập các chức năng của Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Bây giờ, hãy chia hướng dẫn thành nhiều bước để đảm bảo trải nghiệm học tập suôn sẻ.
## Bước 1: Tạo Lịch tùy chỉnh
Bắt đầu bằng cách tạo một dự án mới và thêm lịch tùy chỉnh vào đó:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Bước 2: Xác định ngày làm việc
Thiết lập ngày làm việc mặc định từ thứ Hai đến thứ Sáu:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Bước 3: Cấu hình thời gian làm việc thứ bảy
Quy định thời gian làm việc thứ bảy:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Bước 4: In thời gian làm việc thứ bảy
In thời gian làm việc đã định cấu hình cho Thứ Bảy:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Bước 5: Cấu hình Thời gian làm việc Chủ nhật
Xác định thời gian làm việc ngày chủ nhật:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Bước 6: In Thời gian làm việc Chủ Nhật
In thời gian làm việc đã định cấu hình cho Chủ nhật:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Bước 7: Thêm ngày tùy chỉnh vào lịch
Bao gồm thứ bảy và chủ nhật được cấu hình trong lịch:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Bước 8: Duyệt qua thời gian làm việc
Duyệt qua thời gian làm việc và hiển thị chúng cho từng ngày trong lịch:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Bây giờ bạn đã điều hướng thành công qua các bước, bạn đã được trang bị để khai thác sức mạnh của Aspose.Tasks dành cho .NET trong việc quản lý thời gian làm việc một cách hiệu quả.
## Phần kết luận
Việc nắm vững việc thu thập thời gian làm việc trong Aspose.Tasks cho phép bạn tùy chỉnh lịch dự án, đảm bảo lập lịch chính xác và sử dụng tài nguyên hiệu quả. Tự tin đi sâu vào các dự án của bạn, được trang bị kiến thức thu được từ hướng dẫn toàn diện này.
## Các câu hỏi thường gặp
### Aspose.Tasks có phù hợp để quản lý dự án quy mô lớn không?
Có, Aspose.Tasks được thiết kế để xử lý các dự án có quy mô khác nhau, cung cấp các tính năng mạnh mẽ để quản lý dự án hiệu quả.
### Tôi có thể tích hợp Aspose.Tasks với các thư viện .NET khác không?
Chắc chắn! Aspose.Tasks tích hợp liền mạch với các thư viện .NET khác, nâng cao tính linh hoạt và khả năng tương thích của nó.
### Aspose.Tasks được cập nhật bao lâu một lần?
 Aspose.Tasks được cập nhật thường xuyên để kết hợp các tính năng, cải tiến mới và cải tiến khả năng tương thích. Kiểm tra[trang phát hành](https://releases.aspose.com/tasks/net/) để biết những cập nhật mới nhất.
### Có bản dùng thử miễn phí cho Aspose.Tasks không?
 Có, bạn có thể khám phá Aspose.Tasks với bản dùng thử miễn phí bằng cách truy cập[liên kết này](https://releases.aspose.com/).
### Tôi có thể tìm kiếm sự hỗ trợ cho Aspose.Tasks ở đâu?
 Nếu có bất kỳ thắc mắc hoặc trợ giúp nào, hãy truy cập[Diễn đàn hỗ trợ Aspose.Tasks](https://forum.aspose.com/c/tasks/15).