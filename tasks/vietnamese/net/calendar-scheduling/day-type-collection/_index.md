---
title: Quản lý bộ sưu tập loại ngày trong Aspose.Tasks
linktitle: Quản lý bộ sưu tập loại ngày trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý bộ sưu tập loại ngày một cách hiệu quả trong Aspose.Tasks for .NET. Tạo, sửa đổi và thao tác ngoại lệ lịch một cách dễ dàng.
weight: 28
url: /vi/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý bộ sưu tập loại ngày trong Aspose.Tasks

## Giới thiệu

 Aspose.Tasks for .NET cung cấp chức năng mạnh mẽ để quản lý bộ sưu tập loại ngày, rất quan trọng để xác định các ngoại lệ lịch hàng tuần trong các ứng dụng quản lý dự án. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng`DayTypeCollection` lớp một cách hiệu quả. 

## Điều kiện tiên quyết

Trước khi chúng ta tiếp tục phần hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# và các khái niệm .NET framework.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình:

```csharp
using Aspose.Tasks;
using System;


```

Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước:

## Bước 1: Tải dự án và lịch truy cập

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Bước này khởi tạo một phiên bản dự án mới và truy xuất lịch theo UID của nó.

## Bước 2: Lặp lại các ngoại lệ của lịch

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Ở đây, chúng tôi lặp lại từng ngoại lệ của lịch và in tên của nó cũng như các loại ngày liên quan.

## Bước 3: Sửa đổi ngoại lệ lịch

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Bước này trình bày cách sửa đổi các ngoại lệ của lịch bằng cách thêm, xóa hoặc cập nhật loại ngày.

## Bước 4: Tạo và thao tác ngoại lệ lịch mới

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

Ở bước cuối cùng này, chúng tôi tạo các ngoại lệ lịch mới và thao tác chúng bằng cách thêm và sao chép các loại ngày.

## Phần kết luận

 Tóm lại, việc quản lý bộ sưu tập loại ngày trong Aspose.Tasks cho .NET là điều cần thiết để xác định và sửa đổi các ngoại lệ lịch hàng tuần trong các ứng dụng quản lý dự án. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể sử dụng hiệu quả`DayTypeCollection` lớp để xử lý các hoạt động lịch khác nhau.

## Câu hỏi thường gặp

### Câu hỏi 1: Có thể sử dụng Aspose.Tasks cho .NET để tạo biểu đồ Gantt theo chương trình không?

Câu trả lời 1: Có, Aspose.Tasks for .NET cung cấp API để tạo và thao tác biểu đồ Gantt trong các ứng dụng .NET.

### Câu hỏi 2: Aspose.Tasks dành cho .NET có tương thích với cả .NET Core và .NET Framework không?

Câu trả lời 2: Có, Aspose.Tasks for .NET hỗ trợ cả .NET Core và .NET Framework.

### Câu hỏi 3: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?

 A3: Bạn có thể nhận được hỗ trợ bằng cách truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) nơi bạn có thể đặt câu hỏi và tương tác với những người dùng khác.

### Câu hỏi 4: Aspose.Tasks dành cho .NET có cung cấp bản dùng thử miễn phí không?

 Câu trả lời 4: Có, bạn có thể dùng thử miễn phí Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/).

### Câu hỏi 5: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho .NET không?

 Câu trả lời 5: Có, giấy phép tạm thời có sẵn để mua từ[trang web giả định](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
