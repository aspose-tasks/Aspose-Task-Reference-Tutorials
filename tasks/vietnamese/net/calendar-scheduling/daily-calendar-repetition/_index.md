---
title: Sự lặp lại lịch hàng ngày trong Aspose.Tasks
linktitle: Sự lặp lại lịch hàng ngày trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách tạo các tác vụ định kỳ với lịch lặp lại hàng ngày trong Aspose.Tasks for .NET. Nâng cao hiệu quả quản lý dự án một cách dễ dàng.
type: docs
weight: 25
url: /vi/net/calendar-scheduling/daily-calendar-repetition/
---
## Giới thiệu

 Aspose.Tasks for .NET cung cấp một bộ công cụ mạnh mẽ để quản lý các tác vụ và dự án theo chương trình. Một trong những tính năng đáng chú ý của nó là khả năng xử lý việc lặp lại lịch hàng ngày một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng`DailyCalendarRepetition` class cùng với các lớp liên quan khác để tạo các nhiệm vụ định kỳ với số lần lặp lại hàng ngày dựa trên lịch được chỉ định.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã thiết lập sau:

1.  Cài đặt: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET. Nếu không, bạn có thể tải nó từ[đây](https://releases.aspose.com/tasks/net/).

2. Nhập không gian tên: Nhập các không gian tên cần thiết vào dự án của bạn:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Bước 1: Khởi tạo dự án

Đầu tiên, chúng ta cần tải một dự án hiện có hoặc tạo một dự án mới để làm việc:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Bước 2: Xác định lịch

Tiếp theo, chúng tôi tạo lịch có thời lượng 24 giờ và liên kết nó với dự án:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Bước 3: Đặt tham số tác vụ định kỳ

Bây giờ, hãy đặt tham số cho tác vụ định kỳ của chúng ta. Chúng tôi xác định tên, thời lượng, kiểu lặp lại và phạm vi của nó:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Bước 4: Đặt lịch cho tác vụ

Liên kết lịch đã xác định với nhiệm vụ:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Bước 5: Thêm tác vụ vào dự án

Thêm tác vụ với các tham số đã xác định vào dự án:

```csharp
project.RootTask.Children.Add(parameters);
```

## Bước 6: Lưu dự án

Cuối cùng, lưu dự án với nhiệm vụ định kỳ được thêm vào:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Bây giờ bạn đã tạo thành công một dự án với tác vụ định kỳ được đặt lặp lại hàng ngày dựa trên lịch 24 giờ bằng cách sử dụng Aspose.Tasks for .NET!

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách sử dụng Aspose.Tasks cho .NET để xử lý việc lặp lại lịch hàng ngày một cách hiệu quả. Bằng cách làm theo các bước này, bạn có thể tích hợp liền mạch các nhiệm vụ định kỳ vào dự án của mình, nâng cao năng suất và tổ chức.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tùy chỉnh thời lượng của mỗi lần lặp lại không?

Câu trả lời 1: Có, bạn có thể điều chỉnh thời lượng của mỗi lần lặp lại theo yêu cầu của mình bằng cách sửa đổi các tham số trong mã.

### Câu hỏi 2: Có thể đặt các lịch khác nhau cho các nhiệm vụ khác nhau trong cùng một dự án không?

Câu trả lời 2: Hoàn toàn có thể, Aspose.Tasks cho phép bạn chỉ định lịch cụ thể cho từng nhiệm vụ, mang lại sự linh hoạt trong việc lên lịch.

### Câu hỏi 3: Aspose.Tasks có hỗ trợ các kiểu lặp lại khác ngoài hàng ngày không?

Câu trả lời 3: Có, Aspose.Tasks cung cấp nhiều mô hình lặp lại như hàng tuần, hàng tháng, hàng năm, v.v., phục vụ cho các nhu cầu đa dạng của dự án.

### Câu hỏi 4: Tôi có thể hình dung các tác vụ định kỳ được tạo bằng Aspose.Tasks không?

Câu trả lời 4: Chắc chắn, Aspose.Tasks cung cấp các tùy chọn trực quan hóa để giúp bạn phân tích và theo dõi các tác vụ định kỳ một cách hiệu quả.

### Câu hỏi 5: Có phiên bản dùng thử cho Aspose.Tasks không?

 Câu trả lời 5: Có, bạn có thể tận dụng bản dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/) để khám phá các tính năng của nó trước khi mua hàng.