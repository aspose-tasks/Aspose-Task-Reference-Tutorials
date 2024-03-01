---
title: Quản lý bộ sưu tập lịch trong Aspose.Tasks
linktitle: Quản lý bộ sưu tập lịch trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý bộ sưu tập lịch trong Aspose.Tasks cho .NET một cách hiệu quả. Tạo, sửa đổi và thao tác lịch một cách dễ dàng.
type: docs
weight: 11
url: /vi/net/calendar-scheduling/calendar-collection/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý bộ sưu tập lịch trong Aspose.Tasks cho .NET. Lịch đóng một vai trò quan trọng trong quản lý dự án, xác định ngày làm việc, ngày lễ và các trường hợp ngoại lệ. Aspose.Tasks cung cấp chức năng mạnh mẽ để thao tác lịch trong dự án của bạn.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Visual Studio: Cài đặt Visual Studio hoặc bất kỳ IDE tương thích nào khác để phát triển .NET.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết để làm việc với Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Tạo lịch mới

###  Bước 1: Khởi tạo một cái mới`Project` object.
```csharp
var project = new Project();
```

### Bước 2: Thêm lịch vào bộ sưu tập lịch của dự án.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Bước 3: Lặp lại các lịch và hiển thị tên của chúng.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Thay thế Lịch bằng Lịch Mới

### Bước 1: Tải một dự án hiện có.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Bước 2: Xóa lịch hiện có (nếu có).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Bước 3: Thêm lịch mới.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Lấy lịch theo tên hoặc ID

### Bước 1: Tải dự án.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Bước 2: Truy xuất lịch theo tên hoặc UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Bước 3: Hiển thị chi tiết lịch.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Lặp lại lịch

### Bước 1: Tải dự án.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Bước 2: Truy xuất số lượng lịch.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Bước 3: Lặp lại bộ sưu tập lịch và tên hiển thị.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Làm lịch chuẩn

### Bước 1: Khởi tạo một dự án mới.
```csharp
var project = new Project();
```

### Bước 2: Xác định lịch mới và làm cho nó trở thành tiêu chuẩn.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Bước 3: Lưu dự án.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Phần kết luận

Quản lý bộ sưu tập lịch trong Aspose.Tasks cho .NET là điều cần thiết để quản lý dự án hiệu quả. Với các chức năng được cung cấp, bạn có thể tạo, sửa đổi và thao tác lịch một cách hiệu quả theo yêu cầu dự án của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tạo ngày làm việc tùy chỉnh trong Aspose.Tasks không?

Trả lời 1: Có, bạn có thể tạo ngày làm việc tùy chỉnh bằng cách thêm ngoại lệ vào lịch.

### Câu hỏi 2: Có thể nhập lịch từ tệp Microsoft Project không?

A2: Hoàn toàn có thể, Aspose.Tasks hỗ trợ nhập lịch từ các tệp Microsoft Project.

### Câu hỏi 3: Làm cách nào để xóa lịch cụ thể khỏi dự án?

 A3: Bạn có thể xóa lịch bằng cách lấy nó từ bộ sưu tập rồi gọi`Remove` phương pháp.

### Câu hỏi 4: Aspose.Tasks có hỗ trợ xuất lịch sang các định dạng khác nhau không?

Câu trả lời 4: Có, Aspose.Tasks cho phép xuất lịch sang nhiều định dạng khác nhau như XML, MPP, v.v.

### Câu hỏi 5: Tôi có thể tùy chỉnh giờ làm việc cho những ngày cụ thể trong lịch không?

Câu trả lời 5: Chắc chắn, bạn có thể xác định giờ làm việc cho từng ngày bằng cách sử dụng các ngoại lệ trong lịch.