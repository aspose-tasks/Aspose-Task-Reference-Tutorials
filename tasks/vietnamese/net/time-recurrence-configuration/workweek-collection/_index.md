---
title: Tùy chỉnh tuần làm việc trong Aspose.Tasks
linktitle: Bộ sưu tập các tuần làm việc trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách tùy chỉnh tuần làm việc trong Aspose.Tasks cho .NET. Hướng dẫn từng bước để tạo lịch dự án được cá nhân hóa. Tải ngay!
weight: 17
url: /vi/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tùy chỉnh tuần làm việc trong Aspose.Tasks

## Giới thiệu
Chào mừng bạn đến với hướng dẫn của chúng tôi về cách tạo một tuần làm việc tùy chỉnh bằng Aspose.Tasks cho .NET! Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình xác định tuần làm việc được cá nhân hóa cho lịch trong dự án của bạn. Aspose.Tasks là một thư viện mạnh mẽ hỗ trợ các nhà phát triển làm việc hiệu quả với các tài liệu Microsoft Project trong các ứng dụng .NET của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.aspose.com/tasks/net/).
3. Kiến thức cơ bản về C#: Làm quen với kiến thức cơ bản về ngôn ngữ lập trình C#.
## Nhập không gian tên
Trong dự án C# của bạn, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Bước 1: Tạo dự án và lịch
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Bước 2: Xác định Tuần làm việc tùy chỉnh
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Bước 3: Đặt ngày làm việc
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Bước 4: Hiển thị thông tin về tuần làm việc
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Hướng dẫn toàn diện này cho phép bạn tạo và quản lý tuần làm việc tùy chỉnh một cách hiệu quả bằng cách sử dụng Aspose.Tasks for .NET.
## Phần kết luận
Tóm lại, Aspose.Tasks for .NET cung cấp một giải pháp mạnh mẽ để xử lý lịch dự án với các tuần làm việc tùy chỉnh. Bằng cách làm theo hướng dẫn này, bạn đã học được cách tạo và hiển thị thông tin về các tuần làm việc tùy chỉnh trong dự án của mình.
## Câu hỏi thường gặp
### Tôi có thể có nhiều tuần làm việc tùy chỉnh trong một dự án không?
Có, bạn có thể thêm nhiều tuần làm việc tùy chỉnh vào lịch dự án.
### Làm cách nào để sửa đổi tuần làm việc hiện tại?
 Sử dụng được cung cấp`WorkWeek`các thuộc tính và phương pháp để sửa đổi các tuần làm việc hiện có.
### Aspose.Tasks có tương thích với .NET Core không?
Có, Aspose.Tasks hỗ trợ .NET Core.
### Tôi có thể xuất dự án có tuần làm việc tùy chỉnh sang định dạng tệp Microsoft Project không?
Hoàn toàn có thể, Aspose.Tasks cho phép bạn lưu dự án của mình ở nhiều định dạng khác nhau, bao gồm cả Microsoft Project.
### Tôi có thể tìm kiếm hỗ trợ cho các truy vấn liên quan đến Aspose.Tasks ở đâu?
 Tham quan[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) cho bất kỳ hỗ trợ hoặc trợ giúp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
