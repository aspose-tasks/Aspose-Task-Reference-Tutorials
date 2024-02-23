---
title: Xử lý các mẫu lặp lại hàng tháng trong Aspose.Tasks
linktitle: Xử lý các mẫu lặp lại hàng tháng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý các mẫu lặp lại hàng tháng trong Aspose.Tasks cho .NET bằng hướng dẫn từng bước này.
type: docs
weight: 18
url: /vi/net/advanced-concepts/monthly-recurrence-patterns/
---
## Giới thiệu

Aspose.Tasks for .NET là một API mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình. Một trong những chức năng thiết yếu mà nó cung cấp là khả năng xử lý các tác vụ định kỳ một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ đi sâu vào cách làm việc với các mẫu lặp lại hàng tháng bằng Aspose.Tasks, theo từng bước.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã cài đặt các điều kiện tiên quyết sau:

## Nhập không gian tên

Trước tiên, hãy đảm bảo bạn đã nhập các vùng tên cần thiết trong dự án .NET của mình:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Bây giờ, hãy chia nhỏ quy trình xử lý các dạng lặp lại hàng tháng thành nhiều bước:

## Bước 1: Khởi tạo dự án

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Bước 2: Đặt tham số tác vụ định kỳ

Xác định các tham số cho tác vụ định kỳ, bao gồm tên tác vụ, thời lượng và kiểu lặp lại:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Bước 3: Thêm tham số vào dự án

```csharp
project.RootTask.Children.Add(parameters);
```

## Bước 4: Lưu dự án

Lưu dự án đã sửa đổi với tác vụ định kỳ:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Phần kết luận

Việc xử lý các mẫu lặp lại hàng tháng trong Aspose.Tasks cho .NET rất đơn giản và hiệu quả. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng tạo các tác vụ định kỳ với khoảng thời gian và phạm vi lặp lại cụ thể hàng tháng.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks có tương thích với tất cả các phiên bản của tệp Microsoft Project không?

Trả lời 1: Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm MPP, MPT, XML và MPX.

### Câu hỏi 2: Tôi có thể tùy chỉnh thêm mô hình lặp lại không?

Câu trả lời 2: Có, Aspose.Tasks cung cấp các tùy chọn mở rộng để tùy chỉnh các kiểu lặp lại, bao gồm hàng ngày, hàng tuần, hàng tháng và hàng năm.

### Câu hỏi 3: Aspose.Tasks có bản dùng thử miễn phí không?

 Câu trả lời 3: Có, bạn có thể nhận bản dùng thử miễn phí Aspose.Tasks từ trang web[đây](https://releases.aspose.com/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?

 Câu trả lời 4: Bạn có thể tìm kiếm sự trợ giúp và tham gia thảo luận về[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Câu hỏi 5: Tôi có thể mua giấy phép cho Aspose.Tasks ở đâu?

 Câu trả lời 5: Bạn có thể mua giấy phép cho Aspose.Tasks từ trang web[đây](https://purchase.aspose.com/buy)