---
title: Lặp lại theo tháng Ngày trong tuần trong Aspose.Tasks
linktitle: Lặp lại theo tháng Ngày trong tuần trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thiết lập các lần lặp lại theo tháng, tuần và ngày trong Aspose.Tasks dành cho .NET để tự động hóa các tác vụ định kỳ một cách hiệu quả.
type: docs
weight: 26
url: /vi/net/advanced-features/repetition-by-month-week-day/
---
## Giới thiệu

Trong lĩnh vực phát triển phần mềm, đặc biệt là trong các ứng dụng quản lý dự án, khả năng xử lý các tác vụ định kỳ một cách hiệu quả là điều tối quan trọng. Aspose.Tasks for .NET là một thư viện mạnh mẽ được thiết kế để hợp lý hóa việc tạo và quản lý các tác vụ dự án, bao gồm cả các tác vụ định kỳ. Một chức năng như vậy được Aspose.Tasks cung cấp là khả năng thiết lập các lần lặp lại theo tháng, tuần và ngày, đảm bảo rằng các nhiệm vụ được thực hiện đúng tiến độ mà không cần can thiệp thủ công.

## Điều kiện tiên quyết

Trước khi đi sâu vào sự phức tạp của việc thiết lập các lần lặp lại theo tháng, tuần và ngày bằng Aspose.Tasks cho .NET, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# là điều cần thiết để hiểu và triển khai các ví dụ mã được cung cấp.
   
2.  Cài đặt Aspose.Tasks cho .NET: Đảm bảo rằng bạn đã tải xuống và cài đặt thư viện Aspose.Tasks cho .NET. Bạn có thể lấy thư viện từ[trang tải xuống](https://releases.aspose.com/tasks/net/).

3. Quyền truy cập vào Tệp dự án .mpp: Chuẩn bị sẵn tệp Microsoft Project (.mpp), vì chúng tôi sẽ sử dụng tệp đó để chứng minh việc triển khai lặp lại theo tháng, tuần và ngày.

## Nhập không gian tên

Để bắt đầu sử dụng Aspose.Tasks cho .NET trong ứng dụng C# của bạn, bạn cần nhập các vùng tên cần thiết. Đây là cách bạn có thể làm điều đó:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Hãy chia đoạn mã được cung cấp thành nhiều bước để hiểu kỹ từng phần.

## Bước 1: Tải tệp dự án

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Bước này liên quan đến việc tạo một phiên bản mới của`Project` class và tải tệp Microsoft Project hiện có (`Project1.mpp`) từ thư mục được chỉ định.

## Bước 2: Xác định tham số tác vụ định kỳ

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Trong bước này, chúng tôi xác định các tham số cho một tác vụ định kỳ. Chúng tôi chỉ định tên nhiệm vụ, thời lượng, kiểu lặp lại (hàng tháng) và phạm vi lặp lại (kết thúc trước một ngày cụ thể).

## Bước 3: Thêm tác vụ định kỳ vào dự án

```csharp
project.RootTask.Children.Add(parameters);
```

Ở đây, chúng tôi thêm các tham số tác vụ định kỳ đã xác định vào tác vụ gốc của dự án.

## Bước 4: Lưu tệp dự án

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Cuối cùng, chúng tôi lưu tệp dự án đã sửa đổi với tác vụ định kỳ được thêm vào.

## Phần kết luận

Tóm lại, thiết lập các lần lặp lại theo tháng, tuần và ngày trong Aspose.Tasks cho .NET là một quy trình đơn giản giúp các nhà phát triển tự động hóa việc quản lý các tác vụ định kỳ trong dự án của họ một cách hiệu quả. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch chức năng này vào các ứng dụng C# của mình, tiết kiệm thời gian và công sức trong quản lý dự án.

## Câu hỏi thường gặp

###Q1: Tôi có thể tùy chỉnh mẫu lặp lại ngoài các ví dụ được cung cấp không?

Câu trả lời 1: Có, Aspose.Tasks dành cho .NET cung cấp các tùy chọn tùy chỉnh mở rộng cho các mẫu lặp lại, cho phép bạn điều chỉnh chúng theo yêu cầu cụ thể của mình.

###Q2: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?

 Câu trả lời 2: Có, bạn có thể nhận bản dùng thử miễn phí Aspose.Tasks cho .NET từ[trang phát hành](https://releases.aspose.com/).

###Q3: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?

 Câu trả lời 3: Bạn có thể tìm kiếm sự trợ giúp và tương tác với cộng đồng trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

###Q4: Có giấy phép tạm thời cho Aspose.Tasks cho .NET không?

 Câu trả lời 4: Có, bạn có thể lấy giấy phép tạm thời từ[trang mua hàng](https://purchase.aspose.com/temporary-license/) nhằm mục đích kiểm tra và đánh giá.

###Q5: Tôi có thể tìm tài liệu toàn diện về Aspose.Tasks cho .NET ở đâu?

 A5: Bạn có thể tham khảo chi tiết[tài liệu](https://reference.aspose.com/tasks/net/) có sẵn trên trang web Aspose để được hướng dẫn chuyên sâu về cách sử dụng thư viện.