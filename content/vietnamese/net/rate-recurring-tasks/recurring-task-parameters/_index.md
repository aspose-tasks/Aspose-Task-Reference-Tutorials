---
title: Đặt tham số tác vụ định kỳ trong Aspose.Tasks
linktitle: Đặt tham số tác vụ định kỳ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách đặt tham số tác vụ định kỳ trong Microsoft Project bằng Aspose.Tasks for .NET. Hướng dẫn toàn diện với hướng dẫn từng bước.
type: docs
weight: 14
url: /vi/net/rate-recurring-tasks/recurring-task-parameters/
---
## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập các tham số tác vụ định kỳ của Microsoft Project bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Hiểu biết cơ bản về ngôn ngữ lập trình C#.
2. Đã cài đặt Visual Studio hoặc bất kỳ IDE C# nào khác.
3. Thư viện Aspose.Tasks cho .NET được cài đặt và tham chiếu trong dự án của bạn.

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết trong mã C# của mình:
```csharp
using Aspose.Tasks;
using System;

```
## Bước 1: Xác định thư mục tài liệu
```csharp
String DataDir = "Your Document Directory";
```
 Thay thế`"Your Document Directory"` với đường dẫn đến thư mục tài liệu của bạn.
## Bước 2: Tải tệp dự án
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Dòng mã này tải tệp Microsoft Project vào`project` Biến đổi.
## Bước 3: Xác định tham số tác vụ định kỳ
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Tại đây, bạn xác định các tham số cho tác vụ định kỳ như tên tác vụ, thời lượng, kiểu lặp lại, phạm vi lặp lại và liệu có bỏ qua lịch tài nguyên hay không.
## Bước 4: Đặt lịch cho tác vụ định kỳ
```csharp
parameters.SetCalendar(project, "Standard");
```
Bước này đặt lịch cho nhiệm vụ định kỳ. Trong ví dụ này, nó đặt lịch thành "Tiêu chuẩn".
## Bước 5: Thêm tham số vào dự án
```csharp
project.RootTask.Children.Add(parameters);
```
Cuối cùng, thêm các tham số vào tác vụ gốc của dự án.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày cách đặt tham số tác vụ định kỳ của Microsoft Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể quản lý hiệu quả các tác vụ định kỳ trong dự án của mình.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh thêm mô hình lặp lại không?
Có, Aspose.Tasks cung cấp nhiều mẫu và tùy chọn lặp lại khác nhau để tùy chỉnh theo yêu cầu dự án của bạn.
### Có bản dùng thử trước khi mua không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ Aspose.Tasks[trang mạng](https://purchase.aspose.com/buy) để đánh giá các tính năng của thư viện.
### Aspose.Tasks có hỗ trợ các định dạng tệp dự án khác không?
Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án khác nhau bao gồm MPP, XML, XLSX, v.v.
### Tôi có được hỗ trợ nếu gặp bất kỳ vấn đề gì trong quá trình thực hiện không?
Có, bạn có thể truy cập diễn đàn Aspose.Tasks để được cộng đồng hỗ trợ hoặc liên hệ với bộ phận hỗ trợ để được trợ giúp trực tiếp.
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks?
 Bạn có thể xin giấy phép tạm thời từ[trang mạng](https://purchase.aspose.com/temporary-license/) cho mục đích thử nghiệm.