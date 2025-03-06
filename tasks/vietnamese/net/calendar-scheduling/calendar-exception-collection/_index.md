---
title: Bộ sưu tập ngoại lệ lịch trong Aspose.Tasks
linktitle: Bộ sưu tập ngoại lệ lịch trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý hiệu quả các ngoại lệ lịch trong dự án .NET của bạn bằng Aspose.Tasks, đảm bảo quản lý tài nguyên và lập kế hoạch chính xác.
type: docs
weight: 13
url: /vi/net/calendar-scheduling/calendar-exception-collection/
---
## Giới thiệu

Trong quản lý dự án, việc lập kế hoạch chính xác là rất quan trọng để thành công. Tuy nhiên, các tình huống trong thế giới thực thường yêu cầu có độ lệch so với lịch trình tiêu chuẩn do ngày lễ, sự kiện đặc biệt hoặc các yếu tố khác. Aspose.Tasks for .NET cung cấp một giải pháp mạnh mẽ để quản lý các ngoại lệ đó thông qua tính năng Bộ sưu tập ngoại lệ lịch của nó. Hướng dẫn này sẽ hướng dẫn bạn từng bước trong quá trình sử dụng chức năng này.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1.  Aspose.Tasks for .NET: Đảm bảo bạn đã cài đặt thư viện. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/net/).
2. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ hữu ích trong việc hiểu các ví dụ.
3. Môi trường phát triển: Thiết lập môi trường phát triển ưa thích của bạn, chẳng hạn như Visual Studio hoặc JetBrains Rider.

## Nhập không gian tên

Trước khi bắt đầu làm việc với Aspose.Tasks cho .NET, bạn cần nhập các vùng tên cần thiết vào dự án của mình. Bước này cho phép bạn truy cập các lớp và phương thức cần thiết để quản lý các ngoại lệ của lịch.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước:

## Bước 1: Tải dự án và truy xuất lịch

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Trong bước này, chúng tôi tải tệp dự án và truy xuất lịch mong muốn theo UID của nó.

## Bước 2: Xóa các ngoại lệ hiện có và đặt lịch chuẩn

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Bước này sẽ xóa mọi ngoại lệ hiện có khỏi lịch và đặt nó thành cấu hình tiêu chuẩn.

## Bước 3: Xác định và thêm ngoại lệ thời gian làm việc

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Bước này xác định ngoại lệ về thời gian làm việc với ngày bắt đầu và ngày kết thúc cụ thể, cùng với thời gian làm việc trong những ngày đó và thêm ngày đó vào lịch.

## Bước 4: Xác định và thêm ngoại lệ về thời gian không làm việc

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Thêm nhiều ngoại lệ nếu cần

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Bước này xác định các trường hợp ngoại lệ về thời gian không làm việc, chẳng hạn như ngày lễ và thêm chúng vào lịch.

## Bước 5: Hiển thị ngoại lệ lịch

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Bước này hiển thị các ngoại lệ lịch đã thêm cùng với thông tin chi tiết của chúng.

## Bước 6: Xóa tất cả ngoại lệ

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Cuối cùng, bước này sẽ loại bỏ tất cả các ngoại lệ khỏi lịch.

## Phần kết luận

Quản lý ngoại lệ lịch là rất quan trọng để lập kế hoạch dự án chính xác. Aspose.Tasks for .NET đơn giản hóa tác vụ này bằng cách cung cấp một bộ tính năng toàn diện, bao gồm Bộ sưu tập ngoại lệ lịch. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể xử lý hiệu quả các tình huống lập kế hoạch khác nhau trong dự án của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể thêm nhiều ngoại lệ vào một lịch không?

 Đáp 1: Có, bạn có thể thêm nhiều ngoại lệ vào lịch bằng cách sử dụng`AddRange` phương pháp.

### Câu hỏi 2: Làm cách nào để xử lý các trường hợp ngoại lệ định kỳ, chẳng hạn như ngày nghỉ hàng tuần?

Câu trả lời 2: Bạn có thể lập trình tính toán các ngoại lệ định kỳ và thêm chúng vào lịch bằng logic tùy chỉnh.

### Câu hỏi 3: Có thể nhập ngoại lệ lịch từ các nguồn bên ngoài không?

Câu trả lời 3: Có, bạn có thể đọc các ngoại lệ trong lịch từ các nguồn bên ngoài như cơ sở dữ liệu hoặc tệp CSV và tích hợp chúng vào dự án của bạn.

### Câu hỏi 4: Điều gì xảy ra nếu có các ngoại lệ trùng lặp trong lịch?

Câu trả lời 4: Aspose.Tasks dành cho .NET cho phép bạn xử lý các ngoại lệ chồng chéo bằng cách xác định mức độ ưu tiên hoặc giải quyết xung đột dựa trên yêu cầu dự án của bạn.

### Câu hỏi 5: Tôi có thể tùy chỉnh thời gian làm việc mỗi ngày trong một trường hợp ngoại lệ không?

Câu trả lời 5: Có, bạn có thể chỉ định thời gian làm việc tùy chỉnh cho từng ngày trong một ngoại lệ để đáp ứng nhu cầu lập lịch cụ thể.