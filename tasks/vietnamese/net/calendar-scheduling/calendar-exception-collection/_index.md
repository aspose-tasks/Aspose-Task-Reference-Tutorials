---
date: 2026-04-09
description: Tìm hiểu cách thiết lập lịch chuẩn và quản lý ngày nghỉ dự án trong các
  dự án .NET của bạn bằng Aspose.Tasks để lên lịch chính xác.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Thiết lập Lịch chuẩn và Xử lý các ngoại lệ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Thiết lập Lịch chuẩn và Xử lý các ngoại lệ trong Aspose.Tasks
url: /vi/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Lịch Chuẩn và Xử Lý Ngoại Lệ trong Aspose.Tasks

## Giới thiệu

Lập lịch chính xác là nền tảng của bất kỳ dự án thành công nào, và các kế hoạch thực tế thường phải lệch khỏi lịch làm việc mặc định vì các ngày lễ, sự kiện đặc biệt hoặc các đợt ngừng hoạt động bất ngờ. Aspose.Tasks cho .NET giúp bạn dễ dàng **set standard calendar** và sau đó thêm các ngoại lệ tùy chỉnh lên trên. Trong hướng dẫn này, bạn sẽ học cách tải lịch dự án, đặt lịch chuẩn và quản lý các ngày nghỉ dự án thông qua tính năng Calendar Exception Collection.

## Câu trả lời nhanh
- **set standard calendar** làm gì? Nó đặt lại lịch về thời gian làm việc mặc định (9 AM‑5 PM, Thứ Hai‑Thứ Sáu) trước khi bạn thêm các ngoại lệ tùy chỉnh.  
- **Phương thức nào xóa các ngoại lệ hiện có?** `Calendar.Exceptions.Clear()` loại bỏ tất cả các ngoại lệ đã định nghĩa trước đó.  
- **Làm thế nào để thêm một ngày nghỉ?** Tạo một `CalendarException` với `DayWorking = false` và thêm nó vào bộ sưu tập.  
- **Có cần tải lại dự án sau khi thay đổi không?** Không, các thay đổi được áp dụng trực tiếp lên đối tượng `Project` trong bộ nhớ.  
- **Cần những thư viện nào?** Aspose.Tasks cho .NET (bất kỳ phiên bản .NET hỗ trợ nào) và các không gian tên `System`.

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

1. **Aspose.Tasks cho .NET** – tải về [tại đây](https://releases.aspose.com/tasks/net/).  
2. Kiến thức cơ bản về **C#** – bạn sẽ viết một vài đoạn mã ngắn.  
3. Môi trường phát triển như **Visual Studio** hoặc **JetBrains Rider**.

## Nhập không gian tên

Các chỉ thị `using` này cho phép bạn truy cập các lớp cần thiết để thao tác lịch.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Ngoại lệ Lịch là gì?

*Ngoại lệ lịch* đại diện cho một khoảng thời gian mà lịch làm việc bình thường bị thay đổi – ví dụ, ngày nghỉ toàn công ty hoặc lịch làm thêm tạm thời. Bằng cách thêm ngoại lệ vào lịch, bạn có thể mô hình hoá các ràng buộc thực tế mà không cần thay đổi lịch cơ bản.

## Cách Đặt Lịch Chuẩn trong Aspose.Tasks

Bước đầu tiên là tải tệp dự án của bạn và lấy lịch mà bạn muốn làm việc.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Bước 1: Xóa Các Ngoại Lệ Hiện Tại và Đặt Lại Thành Lịch Chuẩn

Trước khi thêm các quy tắc mới, nên xóa mọi ngoại lệ cũ và **set standard calendar**. Điều này đảm bảo một nền tảng sạch sẽ.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Bước 2: Định Nghĩa Ngoại Lệ Thời Gian Làm Việc

Đôi khi bạn cần tạo một lịch tạm thời (ví dụ, giờ làm việc kéo dài cho một đợt ra mắt sản phẩm). Đoạn mã dưới đây định nghĩa một ngoại lệ thời gian làm việc kéo dài vài ngày và bao gồm hai khoảng thời gian làm việc mỗi ngày.

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

### Bước 3: Thêm Ngoại Lệ Thời Gian Không Làm Việc (Ngày Nghỉ)

Để **manage project holidays**, tạo các ngoại lệ mà `DayWorking` là `false`. Ví dụ dưới đây thêm một khối ngày nghỉ kéo dài hai ngày.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Bước 4: Hiển Thị Các Ngoại Lệ Lịch (Xác Nhận)

Sau khi thêm ngoại lệ, bạn thường muốn kiểm tra chúng đã được ghi lại đúng chưa. Vòng lặp sau in chi tiết của mỗi ngoại lệ ra console.

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

### Bước 5: Xóa Tất Cả Các Ngoại Lệ (Dọn Dẹp)

Nếu bạn cần đưa lịch trở lại trạng thái ban đầu, có thể xóa mọi ngoại lệ một cách lập trình.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Các Vấn Đề Thường Gặp và Giải Pháp

| Vấn đề | Lý do | Giải pháp |
|-------|--------|-----|
| Các ngoại lệ không xuất hiện sau khi lưu | Dự án không được lưu sau khi thay đổi | Gọi `project.Save("output.mpp")` sau khi thực hiện các thay đổi. |
| Các ngoại lệ chồng lên nhau gây giờ làm việc không mong muốn | Aspose.Tasks sử dụng ngoại lệ được thêm cuối cùng cho các khoảng thời gian chồng lấn | Sắp xếp các lời gọi `Add` một cách cẩn thận hoặc điều chỉnh mức ưu tiên thủ công. |
| `MakeStandardCalendar` đặt lại thời gian làm việc tùy chỉnh | Nó cố ý xóa các thời gian tùy chỉnh; cần thêm lại chúng sau khi gọi | Thêm các đối tượng `WorkingTime` tùy chỉnh của bạn sau khi gọi `MakeStandardCalendar`. |

## Câu Hỏi Thường Gặp

**Q: Tôi có thể thêm nhiều ngoại lệ vào một lịch duy nhất không?**  
A: Có, bạn có thể thêm nhiều ngoại lệ vào lịch bằng phương thức `AddRange`.

**Q: Làm thế nào để xử lý các ngoại lệ lặp lại, chẳng hạn ngày nghỉ hàng tuần?**  
A: Bạn có thể tính toán các ngoại lệ lặp lại bằng chương trình và thêm chúng vào lịch bằng logic tùy chỉnh.

**Q: Có thể nhập các ngoại lệ lịch từ nguồn bên ngoài không?**  
A: Có, bạn có thể đọc các ngoại lệ lịch từ các nguồn bên ngoài như cơ sở dữ liệu hoặc tệp CSV và tích hợp chúng vào dự án của mình.

**Q: Điều gì xảy ra nếu có các ngoại lệ chồng lấn trong lịch?**  
A: Aspose.Tasks cho .NET cho phép bạn xử lý các ngoại lệ chồng lấn bằng cách định nghĩa mức ưu tiên hoặc giải quyết xung đột dựa trên yêu cầu dự án của bạn.

**Q: Tôi có thể tùy chỉnh thời gian làm việc cho từng ngày trong một ngoại lệ không?**  
A: Có, bạn có thể chỉ định thời gian làm việc tùy chỉnh cho các ngày riêng lẻ trong một ngoại lệ để đáp ứng nhu cầu lập lịch cụ thể.

## Kết luận

Bằng cách **set standard calendar** trước và sau đó thêm các ngoại lệ tùy chỉnh, bạn sẽ có toàn quyền kiểm soát lịch trình dự án, giúp dễ dàng **manage project holidays** và bất kỳ thời gian đặc biệt nào khác. Calendar Exception Collection trong Aspose.Tasks cung cấp một cách tiếp cận sạch sẽ, lập trình để mô hình hoá các lịch thực tế trực tiếp trong ứng dụng .NET của bạn.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}