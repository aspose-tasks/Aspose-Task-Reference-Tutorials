---
title: Lặp lại theo ngày trong tháng trong Aspose.Tasks
linktitle: Lặp lại theo ngày trong tháng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý các tác vụ định kỳ trong các dự án .NET bằng Aspose.Tasks. Hướng dẫn từng bước xử lý sự lặp lại theo ngày trong tháng.
weight: 25
url: /vi/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lặp lại theo ngày trong tháng trong Aspose.Tasks

## Giới thiệu

Trong lĩnh vực phát triển .NET, Aspose.Tasks là một công cụ mạnh mẽ để quản lý các nhiệm vụ và lịch trình của dự án. Nó cung cấp rất nhiều chức năng để hợp lý hóa quy trình quản lý dự án, bao gồm xử lý các tác vụ định kỳ. Sự lặp lại theo ngày trong tháng là một yêu cầu phổ biến trong việc lập kế hoạch dự án và Aspose.Tasks cung cấp sự hỗ trợ mạnh mẽ cho kịch bản này.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1. Hiểu biết cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# để nắm bắt các khái niệm được thảo luận trong hướng dẫn này.
2. Cài đặt Aspose.Tasks cho .NET: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
3. Môi trường phát triển tích hợp (IDE): Cài đặt một IDE như Visual Studio trên hệ thống của bạn để thuận tiện cho việc mã hóa.

## Nhập không gian tên

Trong dự án C# của bạn, hãy nhập các vùng tên cần thiết để truy cập các chức năng của Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Hãy chia nhỏ ví dụ mã được cung cấp thành định dạng hướng dẫn từng bước:

## Bước 1: Tải tệp dự án

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Dòng mã này khởi tạo một phiên bản mới của`Project` class, tải tệp dự án có tên "Project1.mpp".

## Bước 2: Xác định tham số tác vụ định kỳ

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

Phần này xác định các tham số cho tác vụ lặp lại, bao gồm tên, thời lượng, kiểu lặp lại và phạm vi lặp lại.

## Bước 3: Thêm tác vụ vào dự án

```csharp
project.RootTask.Children.Add(parameters);
```

Ở đây, chúng tôi thêm các tham số tác vụ định kỳ vào dự án.

## Bước 4: Lưu tệp dự án

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Cuối cùng, dự án đã sửa đổi sẽ được lưu cùng với nhiệm vụ định kỳ được thêm vào.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách xử lý sự lặp lại theo ngày trong tháng trong Aspose.Tasks cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể quản lý hiệu quả các nhiệm vụ định kỳ trong lịch trình dự án của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks có tương thích với tất cả các phiên bản .NET không?

Câu trả lời 1: Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của .NET framework, đảm bảo khả năng tương thích trên các môi trường khác nhau.

### Câu hỏi 2: Tôi có thể tùy chỉnh thêm mô hình lặp lại không?

Câu trả lời 2: Có, Aspose.Tasks cung cấp các tùy chọn tùy chỉnh mở rộng để xác định các mẫu lặp lại theo yêu cầu cụ thể của dự án.

### Câu hỏi 3: Aspose.Tasks có cung cấp hỗ trợ cho các chức năng quản lý dự án khác không?

Câu trả lời 3: Hoàn toàn có thể, Aspose.Tasks cung cấp nhiều tính năng để quản lý dự án, bao gồm theo dõi nhiệm vụ, phân bổ nguồn lực và tạo biểu đồ Gantt.

### Câu hỏi 4: Có phiên bản dùng thử cho Aspose.Tasks không?

 Đ4: Có, bạn có thể tận dụng bản dùng thử miễn phí từ[đây](https://releases.aspose.com/) để khám phá khả năng của Aspose.Tasks trước khi đưa ra quyết định mua hàng.

### Câu hỏi 5: Tôi có thể tìm kiếm sự trợ giúp ở đâu nếu gặp vấn đề hoặc có thắc mắc?

 A5: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để tìm kiếm sự hỗ trợ từ cộng đồng hoặc nhóm Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
