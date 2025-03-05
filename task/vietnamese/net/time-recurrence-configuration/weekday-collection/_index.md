---
title: Nắm vững các ngày trong tuần trong Aspose.Tasks
linktitle: Bộ sưu tập các ngày trong tuần trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá sức mạnh của Aspose.Tasks dành cho .NET trong việc quản lý các ngày trong tuần một cách dễ dàng. Tùy chỉnh ngày làm việc, loại bỏ ngày cuối tuần và tạo lịch chuyên dụng một cách dễ dàng.
type: docs
weight: 11
url: /vi/net/time-recurrence-configuration/weekday-collection/
---
## Giới thiệu
Aspose.Tasks for .NET là một thư viện mạnh mẽ hỗ trợ thao tác hiệu quả dữ liệu quản lý dự án. Trong hướng dẫn này, chúng ta sẽ khám phá bộ sưu tập các ngày trong tuần trong Aspose.Tasks, cho phép bạn tùy chỉnh ngày làm việc, loại bỏ các ngày cuối tuần và tạo lịch chuyên dụng để đáp ứng yêu cầu dự án của bạn. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới, hướng dẫn từng bước này sẽ hướng dẫn bạn quy trình làm việc với các ngày trong tuần trong Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Cài đặt thư viện Aspose.Tasks cho .NET. Bạn có thể tải nó xuống từ[Trang tải xuống Aspose.Tasks cho .NET](https://releases.aspose.com/tasks/net/).
- Làm quen với ngôn ngữ lập trình C#.
- Môi trường phát triển tích hợp (IDE) như Visual Studio.
## Nhập không gian tên
Bắt đầu bằng cách nhập các không gian tên cần thiết vào dự án C# của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Bước 1: Tạo một phiên bản dự án
Khởi tạo dự án Aspose.Tasks mới:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Bước 2: Truy cập Lịch
Truy xuất lịch dự án:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Bước 3: Tùy chỉnh các ngày trong tuần
Xóa các ngày trong tuần hiện có và đặt ngày làm việc mặc định:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Thêm các ngày trong tuần khác tương tự...
```
## Bước 4: Thêm thời gian làm việc
Thêm thời gian làm việc cho các ngày trong tuần cụ thể:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Bước 5: Hiển thị thông tin lịch
Xuất chi tiết lịch ra bàn điều khiển:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Hiển thị từng ngày trong tuần và thời gian làm việc...
```
## Bước 6: Xóa ngày cuối tuần
Bỏ thứ bảy và chủ nhật khỏi các ngày trong tuần:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Bước 7: Hiển thị thời gian làm việc được cập nhật
Đầu ra cập nhật thời gian làm việc sau khi loại bỏ các ngày cuối tuần:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Hiển thị từng ngày trong tuần và thời gian làm việc được cập nhật...
```
## Bước 8: Tạo Lịch 24 giờ
Tạo lịch 24 giờ và sao chép các ngày trong tuần:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá các khả năng mạnh mẽ của Aspose.Tasks dành cho .NET trong việc quản lý các ngày trong tuần trong lịch dự án. Từ việc tùy chỉnh ngày làm việc đến tạo lịch 24 giờ chuyên biệt, Aspose.Tasks đơn giản hóa quy trình, mang lại sự linh hoạt và khả năng kiểm soát trong quản lý dự án.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với các ngôn ngữ lập trình khác không?
Trả lời: Aspose.Tasks chủ yếu hỗ trợ các ngôn ngữ .NET, nhưng nó cũng cung cấp các phiên bản cho Java.
### Câu hỏi: Có bản dùng thử miễn phí Aspose.Tasks cho .NET không?
 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[Trang phát hành Aspose.Tasks](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?
 Đáp: Hãy ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ cộng đồng hoặc cân nhắc mua một gói hỗ trợ.
### Câu hỏi: Tôi có thể tìm tài liệu toàn diện về Aspose.Tasks cho .NET ở đâu?
 Đáp: Hãy tham khảo[Aspose.Tasks cho tài liệu .NET](https://reference.aspose.com/tasks/net/) để biết thông tin chi tiết.
### Câu hỏi: Làm cách nào để có được giấy phép tạm thời cho Aspose.Tasks cho .NET?
 Đáp: Bạn có thể xin giấy phép tạm thời từ[trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).