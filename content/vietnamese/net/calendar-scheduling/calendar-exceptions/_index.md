---
title: Xử lý ngoại lệ lịch trong Aspose.Tasks
linktitle: Xử lý ngoại lệ lịch trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý các ngoại lệ lịch trong Aspose.Tasks dành cho .NET với các ví dụ và hướng dẫn từng bước.
type: docs
weight: 12
url: /vi/net/calendar-scheduling/calendar-exceptions/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý các ngoại lệ lịch trong Aspose.Tasks bằng .NET framework. Các trường hợp ngoại lệ về lịch cho phép chúng tôi xác định các ngày hoặc giai đoạn đặc biệt trong lịch dự án khi lịch làm việc thông thường bị thay đổi, chẳng hạn như ngày lễ hoặc thời gian đóng cửa tạm thời. Chúng tôi sẽ đề cập đến các phương pháp khác nhau để xử lý các ngoại lệ của lịch theo từng bước bằng cách sử dụng Aspose.Tasks cho .NET.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Visual Studio được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.Tasks cho .NET đã được thêm vào dự án của bạn.

## Nhập không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết cho dự án của chúng ta:

```csharp
using Aspose.Tasks;
using System;


```

## Bước 1: Xóa ngoại lệ lịch

Để xóa ngoại lệ lịch, hãy làm theo các bước sau:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Hiển thị thông tin lịch
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Xóa ngoại lệ đầu tiên
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Bước 2: Lấy thời gian làm việc của ngoại lệ lịch

Để truy xuất thời gian làm việc của ngoại lệ lịch, hãy làm theo các bước sau:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Hiển thị thông tin lịch và ngoại lệ
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Nhận thời gian làm việc và hiển thị chi tiết
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Bước 3: Xác định ngoại lệ lịch

Để thêm hoặc xóa ngoại lệ lịch, hãy làm theo các bước sau:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Tạo một ngoại lệ lịch mới
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Đặt chi tiết ngoại lệ
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Kiểm tra xem một ngày có phải là ngoại lệ không
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Thêm ngoại lệ vào lịch
    calendar.Exceptions.Add(exception);

    // Xóa ngoại lệ nếu tồn tại
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Thêm một ngoại lệ mới
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // In ngoại lệ
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Phần kết luận

Trong bài viết này, chúng tôi đã đề cập đến nhiều khía cạnh khác nhau của việc xử lý ngoại lệ lịch trong Aspose.Tasks dành cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể quản lý hiệu quả các trường hợp ngoại lệ trong lịch trình dự án của mình, đảm bảo trình bày chính xác về giờ làm việc và các sự kiện đặc biệt.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể thêm nhiều ngoại lệ vào một lịch không?

Câu trả lời 1: Có, bạn có thể thêm nhiều ngoại lệ vào lịch để phù hợp với nhiều ngày hoặc khoảng thời gian đặc biệt khác nhau.

### Câu hỏi 2: Làm cách nào để kiểm tra xem một ngày cụ thể có phải là ngoại lệ không?

 A2: Bạn có thể sử dụng`CheckException()` phương pháp để xác minh xem một ngày cụ thể có thuộc trường hợp ngoại lệ hay không.

### Câu hỏi 3: Có thể xóa ngoại lệ hiện có khỏi lịch không?

 Câu trả lời 3: Có, bạn có thể loại bỏ các ngoại lệ bằng cách truy cập vào`Exceptions` bộ sưu tập lịch và sử dụng`Remove()` phương pháp.

### Câu hỏi 4: Những loại ngoại lệ lịch nào được hỗ trợ?

Câu trả lời 4: Aspose.Tasks hỗ trợ nhiều loại ngoại lệ khác nhau, bao gồm ngoại lệ hàng ngày, hàng tuần, hàng tháng và hàng năm, mang lại sự linh hoạt trong việc xác định các quy tắc ngoại lệ.

### Câu hỏi 5: Tôi có thể tùy chỉnh giờ làm việc cho những ngày ngoại lệ cụ thể không?

Câu trả lời 5: Có, bạn có thể xác định thời gian làm việc tùy chỉnh cho từng ngày ngoại lệ riêng lẻ bằng các phương pháp thích hợp do Aspose.Tasks cung cấp.