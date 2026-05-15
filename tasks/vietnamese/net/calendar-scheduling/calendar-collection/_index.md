---
date: 2026-04-13
description: Tìm hiểu cách thiết lập giờ làm việc và quản lý bộ sưu tập lịch trong
  Aspose.Tasks cho .NET. Nhập lịch từ Microsoft Project, xóa lịch dự án và lấy lịch
  theo tên một cách dễ dàng.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Quản lý bộ sưu tập lịch trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Thiết lập giờ làm việc trong bộ sưu tập Lịch Aspose.Tasks
url: /vi/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt giờ làm việc trong Bộ sưu tập Lịch Aspose.Tasks

Trong hướng dẫn này, bạn sẽ học cách **đặt giờ làm việc** và quản lý bộ sưu tập lịch bằng Aspose.Tasks cho .NET. Lịch xác định các ngày làm việc, ngày nghỉ và các ngoại lệ, vì vậy việc nắm vững chúng cho phép bạn kiểm soát lịch trình dự án một cách chính xác. Chúng tôi cũng sẽ chỉ cho bạn cách nhập lịch từ Microsoft Project, xóa một lịch khỏi dự án và lấy một lịch theo tên.

## Câu trả lời nhanh
- **Lớp chính cho lịch là gì?** `Project.Calendars` collection.  
- **Làm thế nào để đặt giờ làm việc?** Tạo hoặc sửa đổi một đối tượng `Calendar` và định nghĩa `WorkingTime` của nó.  
- **Tôi có thể nhập lịch từ Microsoft Project không?** Có – tải tệp MPP và truy cập các lịch của nó.  
- **Cách xóa một lịch khỏi dự án?** Sử dụng `Project.Calendars.Remove(calendar)`.  
- **Cách lấy một lịch theo tên?** Gọi `Project.Calendars.GetByName("YourCalendar")`.

## Yêu cầu trước

Trước khi bắt đầu, hãy đảm bảo bạn có những thứ sau:

1. Visual Studio: Cài đặt Visual Studio hoặc bất kỳ IDE tương thích nào khác cho phát triển .NET.  
2. Aspose.Tasks for .NET: Tải xuống và cài đặt Aspose.Tasks for .NET từ [here](https://releases.aspose.com/tasks/net/).  
3. Kiến thức cơ bản về C#: Hiểu biết về ngôn ngữ lập trình C# sẽ rất hữu ích.

## Nhập không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết để làm việc với Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Tạo một Lịch mới

### Bước 1: Khởi tạo một đối tượng `Project` mới.
```csharp
var project = new Project();
```

### Bước 2: Thêm lịch vào bộ sưu tập lịch của dự án.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Bước 3: Duyệt qua các lịch và hiển thị tên của chúng.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Cách đặt giờ làm việc cho một lịch?

Để **đặt giờ làm việc**, bạn sửa đổi bộ sưu tập `WorkingTime` của một `Calendar`.  
Ví dụ, bạn có thể định nghĩa một ngày làm việc tiêu chuẩn từ 9 am‑5 pm hoặc thêm các ngoại lệ tùy chỉnh.  
Mã cho việc này giống hệt các ví dụ được trình bày sau khi chúng ta tạo một lịch chuẩn.

## Thay thế một lịch bằng lịch mới

### Bước 1: Tải một dự án hiện có.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Bước 2: Xóa lịch hiện có (nếu tồn tại).  
Điều này minh họa kịch bản **xóa lịch dự án**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Bước 3: Thêm một lịch mới.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Lấy lịch theo Tên hoặc ID

### Bước 1: Tải dự án.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Bước 2: Lấy lịch theo tên hoặc UID.  
Điều này minh họa thao tác **lấy lịch theo tên**.
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

## Duyệt qua các Lịch

### Bước 1: Tải dự án.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Bước 2: Lấy số lượng lịch.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Bước 3: Duyệt qua bộ sưu tập lịch và hiển thị tên.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Tạo một Lịch chuẩn

### Bước 1: Khởi tạo một dự án mới.
```csharp
var project = new Project();
```

### Bước 2: Định nghĩa một lịch mới và đặt nó làm chuẩn.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Bước 3: Lưu dự án.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Các vấn đề thường gặp và giải pháp

- **Không tìm thấy lịch khi sử dụng `GetByName`** – Đảm bảo tên chính xác khớp với cách viết chữ hoa/chữ thường khi lịch được thêm.  
- **Giờ làm việc không được áp dụng** – Sau khi thiết lập `WorkingTime`, nhớ lưu dự án; nếu không các thay đổi chỉ tồn tại trong bộ nhớ.  
- **Nhập lịch từ tệp MPP thất bại** – Kiểm tra tệp nguồn có phải là tệp Microsoft Project hợp lệ và bạn có quyền đọc.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tạo ngày làm việc tùy chỉnh trong Aspose.Tasks không?
A1: Có, bạn có thể tạo ngày làm việc tùy chỉnh bằng cách thêm các ngoại lệ vào lịch.

### Câu hỏi 2: Có thể nhập lịch từ tệp Microsoft Project không?
A2: Chắc chắn, Aspose.Tasks hỗ trợ nhập lịch từ các tệp Microsoft Project.

### Câu hỏi 3: Làm thế nào để xóa một lịch cụ thể khỏi dự án?
A3: Bạn có thể xóa một lịch bằng cách lấy nó từ bộ sưu tập và sau đó gọi phương thức `Remove`.

### Câu hỏi 4: Aspose.Tasks có hỗ trợ xuất lịch sang các định dạng khác không?
A4: Có, Aspose.Tasks cho phép xuất lịch sang nhiều định dạng như XML, MPP, v.v.

### Câu hỏi 5: Tôi có thể tùy chỉnh giờ làm việc cho các ngày cụ thể trong một lịch không?
A5: Chắc chắn, bạn có thể định nghĩa giờ làm việc cho từng ngày riêng lẻ bằng cách sử dụng các ngoại lệ trong lịch.

## Các câu hỏi thường gặp

**Q: Cách tốt nhất để thiết lập lịch ca 24‑giờ là gì?**  
A: Tạo một lịch mới, xóa các mục `WorkingTime` hiện có, và thêm một phạm vi `WorkingTime` duy nhất từ 00:00 đến 24:00 cho mỗi ngày trong tuần.

**Q: Tôi có thể sao chép một lịch từ dự án này sang dự án khác không?**  
A: Có—xuất lịch ra XML bằng `project.Save` và sau đó nhập nó vào dự án khác bằng `new Project(xmlPath)`.

**Q: Làm thế nào để lập trình nhập lịch từ Microsoft Project?**  
A: Tải tệp MPP bằng `new Project("source.mpp")`; các lịch sẽ có sẵn qua `project.Calendars`.

**Q: Có giới hạn số lượng lịch trong một dự án không?**  
A: Thực tế không; bộ sưu tập có thể chứa bao nhiêu lịch tùy thuộc vào bộ nhớ, nhưng nên giữ danh sách hợp lý để hiệu suất tốt.

**Q: Các thay đổi đối với lịch có tự động cập nhật các nhiệm vụ sử dụng nó không?**  
A: Có—các nhiệm vụ liên kết với lịch sẽ phản ánh thời gian làm việc đã cập nhật sau khi bạn lưu dự án.

---

**Last Updated:** 2026-04-13  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}