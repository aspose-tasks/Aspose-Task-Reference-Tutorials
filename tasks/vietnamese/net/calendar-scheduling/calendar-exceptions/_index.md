---
date: 2026-04-13
description: Tìm hiểu cách xóa ngoại lệ lịch trong Aspose.Tasks cho .NET và kiểm tra
  ngày ngoại lệ khi quản lý lịch trình ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Xóa ngoại lệ lịch bằng Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Xóa ngoại lệ lịch với Aspose.Tasks
url: /vi/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xóa Ngoại Lệ Lịch với Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học cách **xóa ngoại lệ lịch** và quản lý các ngoại lệ lịch khác trong Aspose.Tasks bằng .NET framework. Các ngoại lệ lịch cho phép bạn mô hình hoá ngày lễ, đóng cửa tạm thời, hoặc bất kỳ khoảng thời gian đặc biệt nào mà lịch làm việc bình thường thay đổi. Hiểu cách thêm, truy vấn và loại bỏ các ngoại lệ này là cần thiết để lập kế hoạch dự án chính xác, đặc biệt khi làm việc với các kịch bản **lập lịch lịch ASP.NET**.

## Câu trả lời nhanh
- **Phương pháp chính để loại bỏ một ngoại lệ là gì?** Sử dụng phương thức `Delete()` trên đối tượng `CalendarException`.  
- **Lớp nào kiểm tra ngày so với một ngoại lệ?** `CalendarException.CheckException()`—hữu ích để **kiểm tra ngày ngoại lệ**.  
- **Tôi có cần giấy phép để chạy mã không?** Có, cần một giấy phép Aspose.Tasks hợp lệ cho môi trường sản xuất.  
- **Tôi có thể thêm nhiều ngoại lệ vào một lịch không?** Chắc chắn; bộ sưu tập `Exceptions` hỗ trợ nhiều mục.  
- **Phiên bản .NET được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Ngoại lệ lịch là gì?

Một **ngoại lệ lịch** đại diện cho sự lệch khỏi lịch làm việc thông thường—nghĩ như một quy tắc nói “vào những ngày này, giờ làm việc khác nhau hoặc không có giờ làm việc”. Trong Aspose.Tasks, mỗi ngoại lệ có thể có thời gian làm việc riêng, mẫu lặp lại và các cờ chỉ ra ngày có làm việc hay không.

## Tại sao quản lý ngoại lệ lịch trong Lập lịch ASP.NET?

- **Dòng thời gian chính xác:** Dự án tự động tôn trọng ngày lễ và các thời gian đóng cửa đặc biệt, ngăn ngừa thời hạn không thực tế.  
- **Linh hoạt:** Bạn có thể định nghĩa mẫu hàng ngày, hàng tuần, hàng tháng hoặc hàng năm, phù hợp với lịch doanh nghiệp thực tế.  
- **Tự động hóa:** Kiểm tra ngày ngoại lệ bằng chương trình cho phép bạn xây dựng logic lập lịch động trong các ứng dụng ASP.NET.

## Yêu cầu trước

- Kiến thức cơ bản về lập trình C#.  
- Visual Studio (bất kỳ phiên bản mới nào).  
- Thư viện Aspose.Tasks for .NET đã được thêm vào dự án (qua NuGet hoặc tham chiếu thủ công).  

## Nhập không gian tên

Đầu tiên, nhập các không gian tên bạn sẽ cần:

```csharp
using Aspose.Tasks;
using System;
```

## Bước 1: Xóa ngoại lệ lịch

Việc loại bỏ một ngoại lệ không mong muốn rất đơn giản. Đoạn mã dưới đây tải một dự án, chọn lịch đầu tiên, hiển thị thông tin cơ bản, xóa ngoại lệ đầu tiên, và sau đó hiển thị số lượng đã cập nhật.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Mẹo chuyên nghiệp:** Luôn kiểm tra chỉ mục ngoại lệ tồn tại trước khi gọi `Delete()` để tránh `IndexOutOfRangeException`.

## Bước 2: Lấy thời gian làm việc của một ngoại lệ lịch

Nếu bạn cần kiểm tra giờ làm việc được định nghĩa cho một ngoại lệ, hãy sử dụng `GetWorkingTime()`. Ví dụ này cũng minh họa cách **kiểm tra ngày ngoại lệ** bằng `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Bước 3: Định nghĩa ngoại lệ lịch

Dưới đây là một quy trình đầy đủ cho thấy cách **thêm**, **kiểm tra**, và **xóa** các ngoại lệ lịch. Lưu ý việc sử dụng `CheckException` để **kiểm tra ngày ngoại lệ** cho một thời điểm cụ thể.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Vấn đề thường gặp & Mẹo

| Vấn đề | Lý do | Giải pháp |
|-------|--------|----------|
| **`IndexOutOfRangeException` khi xóa** | Cố gắng xóa một ngoại lệ không tồn tại. | Kiểm tra `calendar.Exceptions.Count` > chỉ mục trước khi gọi `Delete()`. |
| **Thời gian làm việc không đúng** | Không thiết lập `DayWorking` hoặc `WorkingTimes` đúng cách. | Sử dụng `exception.WorkingTimes.Add(new WorkingTime(...))` để định nghĩa các khoảng thời gian cụ thể. |
| **Ngoại lệ không được nhận diện** | `CheckException` trả về `false` vì ngày nằm ngoài phạm vi đã định. | Kiểm tra lại `FromDate`/`ToDate` và `Type` (Daily, Weekly, v.v.). |

## Câu hỏi thường gặp

**H: Tôi có thể thêm nhiều ngoại lệ vào một lịch duy nhất không?**  
Đ: Có, bạn có thể thêm bao nhiêu ngoại lệ tùy ý để đại diện cho ngày lễ, **cửa sổ bảo trì**, hoặc bất kỳ quy tắc lập lịch đặc biệt nào.

**H: Làm cách nào để **kiểm tra ngày ngoại lệ** cho một ngày cụ thể?**  
Đ: Sử dụng phương thức `CheckException(DateTime date)` trên một thể hiện `CalendarException`. Nó trả về `true` nếu ngày được cung cấp nằm trong phạm vi ngoại lệ.

**H: Có thể loại bỏ một ngoại lệ hiện có khỏi lịch không?**  
Đ: Chắc chắn. Truy cập bộ sưu tập `Exceptions` và gọi `Remove()` hoặc gọi `Delete()` trên đối tượng `CalendarException` cụ thể.

**H: Những loại ngoại lệ lịch nào được hỗ trợ?**  
Đ: Aspose.Tasks hỗ trợ các loại ngoại lệ Daily, Weekly, Monthly và Yearly, cung cấp sự linh hoạt để mô hình hoá hầu hết các mẫu lặp lại.

**H: Tôi có thể tùy chỉnh giờ làm việc cho các ngày ngoại lệ cụ thể không?**  
Đ: Có. Sau khi tạo một ngoại lệ, hãy điền bộ sưu tập `WorkingTimes` của nó bằng các đối tượng `WorkingTime` xác định thời gian bắt đầu và kết thúc cho ngày đó.

## Kết luận

Chúng ta đã đi qua toàn bộ vòng đời của các thao tác **xóa ngoại lệ lịch**, từ việc kiểm tra các ngoại lệ hiện có đến việc thêm mới và kiểm tra ngày. Nắm vững các kỹ thuật này giúp lịch trình dự án của bạn tôn trọng lịch thực tế, làm cho các triển khai lập lịch ASP.NET của bạn trở nên vững chắc và đáng tin cậy.

---

**Cập nhật lần cuối:** 2026-04-13  
**Kiểm tra với:** Aspose.Tasks for .NET (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}