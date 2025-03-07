---
title: Nắm vững các ngày trong tuần trong Aspose.Tasks cho .NET
linktitle: Xác định các ngày trong tuần trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá sức mạnh của việc xác định các ngày trong tuần trong Aspose.Tasks .NET. Hãy làm theo hướng dẫn chi tiết của chúng tôi để quản lý hiệu quả lịch dự án, tùy chỉnh thời gian làm việc, v.v.
weight: 10
url: /vi/net/time-recurrence-configuration/defining-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nắm vững các ngày trong tuần trong Aspose.Tasks cho .NET

## Giới thiệu
Nếu bạn đang đi sâu vào thế giới quản lý dự án bằng Aspose.Tasks cho .NET, việc hiểu và thao tác các ngày trong tuần là một khía cạnh quan trọng. Quản lý và tùy chỉnh hiệu quả các ngày trong tuần trong lịch dự án của bạn có thể tác động đáng kể đến tiến độ dự án. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình xác định các ngày trong tuần bằng Aspose.Tasks, cung cấp hướng dẫn và ví dụ từng bước để hiểu rõ hơn.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu cuộc hành trình này, hãy đảm bảo bạn có những điều kiện tiên quyết sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình C#.
-  Aspose.Tasks cho thư viện .NET đã được cài đặt. Nếu không, hãy tải xuống từ[đây](https://releases.aspose.com/tasks/net/).
## Nhập không gian tên
Bắt đầu bằng cách nhập các không gian tên cần thiết vào dự án của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Kiểm tra sự bình đẳng trong ngày
```csharp
// Thư mục tài liệu của bạn
String DataDir = "Your Document Directory";
// Tải tập tin dự án
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Truy cập các ngày trong tuần
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Kiểm tra sự bình đẳng dựa trên các thuộc tính khác nhau
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Thêm các câu lệnh đầu ra tương tự cho DayWorking, FromDate, ToDate và WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Sao chép một ngày trong tuần
```csharp
// Tải tập tin dự án
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Tạo một bản sao sâu của ngày trong tuần
var weekDay2 = weekDay1.Clone();
// Thuộc tính đầu ra của cả hai ngày trong tuần
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Thêm các câu lệnh đầu ra tương tự cho DayWorking, FromDate, ToDate và WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Nhận Hash Code của một ngày trong tuần
```csharp
// Tải tập tin dự án
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Thuộc tính đầu ra của cả hai ngày trong tuần
// Thêm các câu lệnh đầu ra tương tự cho DayWorking, FromDate, ToDate và WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Tạo Lịch Mới với các ngày trong tuần được xác định
```csharp
// Tạo một dự án mới
var project = new Project();
// Xác định lịch
var calendar = project.Calendars.Add("Calendar1");
// Thêm ngày làm việc và ngày ngoại lệ
// Thêm các câu lệnh đầu ra tương tự cho FromDate và ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Đặt thời gian làm việc cho thứ Sáu
// Thêm các câu lệnh đầu ra tương tự cho DayWorking, FromDate, ToDate và WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Đặt thời gian làm việc mặc định cho một ngày
```csharp
// Tạo một dự án mới
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Thêm thời gian làm việc mặc định từ Thứ Hai đến Thứ Sáu
// Thêm các câu lệnh đầu ra tương tự cho DayWorking, FromDate, ToDate và WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Lặp lại cho Thứ Ba, Thứ Tư, Thứ Năm và Thứ Sáu
// Đặt ngày không làm việc cho thứ bảy và chủ nhật
// Thêm các câu lệnh đầu ra tương tự cho DayWorking, FromDate, ToDate và WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã đề cập đến các khía cạnh thiết yếu của việc xác định các ngày trong tuần trong Aspose.Tasks cho .NET. Thao tác các ngày trong tuần là một kỹ năng quan trọng để quản lý dự án hiệu quả. Thử nghiệm với các ví dụ được cung cấp, điều chỉnh chúng cho phù hợp với nhu cầu dự án của bạn và khai thác toàn bộ tiềm năng của Aspose.Tasks.
## Câu hỏi thường gặp
### Tôi có thể xác định thời gian làm việc tùy chỉnh cho mỗi ngày không?
Có, bạn có thể đặt thời gian làm việc tùy chỉnh cho các ngày trong tuần cụ thể bằng cách sử dụng các ví dụ được cung cấp.
### Có thể thêm nhiều ngày ngoại lệ vào lịch không?
Tuyệt đối. Sửa đổi mã trong ví dụ thứ tư để bao gồm các ngày ngoại lệ bổ sung.
### Làm cách nào để xóa một ngày cụ thể trong tuần khỏi lịch?
Sử dụng các phương pháp thích hợp do thư viện Aspose.Tasks cung cấp để xóa các ngày trong tuần nếu cần.
### Những thay đổi được thực hiện đối với các ngày trong tuần có tồn tại trong tệp dự án không?
Có, mọi sửa đổi đối với các ngày trong tuần đều được phản ánh trong tệp dự án khi được lưu.
### Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?
Aspose.Tasks hỗ trợ nhiều ngôn ngữ lập trình khác nhau, nhưng các ví dụ ở đây dành riêng cho .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
