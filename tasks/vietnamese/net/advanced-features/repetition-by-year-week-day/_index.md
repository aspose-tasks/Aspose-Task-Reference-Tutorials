---
date: 2026-04-03
description: Học cách sử dụng Aspose.Tasks để thêm dự án công việc định kỳ và lưu
  dự án dưới dạng MPP. Hướng dẫn này trình bày tính năng Lặp lại theo Năm, Tuần, Ngày
  một cách chi tiết.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Lặp lại theo Năm, Tuần, Ngày trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cách sử dụng Aspose.Tasks – Lặp lại theo Năm, Tuần, Ngày
url: /vi/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lặp lại theo Năm Tuần Ngày trong Aspose.Tasks

## Giới thiệu

Khi bạn cần **how to use Aspose.Tasks** để xử lý các lịch trình lặp lại phức tạp, thư viện cung cấp cho bạn khả năng kiểm soát chi tiết các mẫu hàng năm. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn tạo một nhiệm vụ lặp lại vào một ngày trong tuần cụ thể của một tháng nhất định, kéo dài qua nhiều năm. Khi kết thúc, bạn sẽ có thể **add recurring task project** và **save project as MPP** chỉ với vài dòng C#.

## Câu trả lời nhanh
- **What does “Repetition by Year Week Day” mean?** Nó lặp lại một nhiệm vụ vào ngày trong tuần đã chọn (ví dụ: Chủ nhật đầu tiên) của một tháng nhất định mỗi năm.  
- **Which .NET versions are supported?** Tất cả các phiên bản .NET Framework và .NET Core/5/6 hiện đại.  
- **Do I need a license to run the code?** Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Can I change the recurrence range?** Có – bạn có thể đặt ngày bắt đầu, ngày kết thúc, hoặc số lần lặp cố định.  
- **Is the output an MPP file?** Chắc chắn – dự án được lưu dưới dạng tệp MPP sẵn sàng cho Microsoft Project.

## Tính năng “Repetition by Year Week Day” là gì?

Tính năng này cho phép bạn định nghĩa một lịch lặp lại hàng năm nhắm vào một **day of the week** cụ thể (ví dụ: Chủ nhật) và một **position** trong tháng (đầu tiên, thứ hai, cuối cùng, v.v.). Điều này lý tưởng cho các nhiệm vụ như đánh giá hàng quý, kiểm toán hàng năm, hoặc bất kỳ sự kiện nào theo nhịp lịch.

## Tại sao nên sử dụng Aspose.Tasks cho các nhiệm vụ lặp lại?

- **Precision** – Kiểm soát đầy đủ các tháng, ngày trong tuần và vị trí thứ tự.  
- **Compatibility** – Tạo các tệp MPP gốc có thể mở một cách hoàn hảo trong Microsoft Project.  
- **No COM interop** – API .NET thuần, không cần cài đặt Office.  
- **Scalability** – Hoạt động cho các dự án nhỏ và lịch trình cấp doanh nghiệp.

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn có:

1. **Basic .NET knowledge** – Quen thuộc với C# và các khái niệm hướng đối tượng.  
2. **Aspose.Tasks for .NET** – Tải xuống từ [download link](https://releases.aspose.com/tasks/net/) và thêm DLL vào dự án của bạn.  
3. **Access to the official docs** – Tài liệu [documentation](https://reference.aspose.com/tasks/net/) chứa chi tiết đầy đủ về tất cả các lớp.  
4. **A development IDE** – Visual Studio, Rider, hoặc bất kỳ trình chỉnh sửa .NET nào tương thích.  

Bây giờ bạn đã sẵn sàng, hãy xem phần triển khai.

## Cách sử dụng Aspose.Tasks cho các nhiệm vụ lặp lại

### Nhập các namespace cần thiết

Đầu tiên, đưa các namespace cần thiết vào phạm vi để bạn có thể làm việc với dự án, nhiệm vụ và các tùy chọn lưu.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Bước 1: Khởi tạo Dự án và Tham số Nhiệm vụ

Tạo một thể hiện `Project` mới, sau đó định nghĩa một đối tượng `RecurringTaskParameters` mô tả mẫu lặp lại.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Điều chỉnh `Month`, `WeekDay`, và `Position` để phù hợp với lịch trình thực tế của bạn.

### Bước 2: Thêm Tham số vào Dự án

Chèn định nghĩa nhiệm vụ lặp lại vào gốc của dự án.

```csharp
project.RootTask.Children.Add(parameters);
```

### Bước 3: Lưu Dự án dưới dạng MPP

Cuối cùng, lưu dự án vào tệp MPP để có thể mở trong Microsoft Project hoặc bất kỳ trình xem nào tương thích.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> This demonstrates **save project as mpp** trong một dòng mã duy nhất.

## Các vấn đề thường gặp và giải pháp

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| Không có nhiệm vụ nào xuất hiện sau khi mở tệp MPP | Ngày phạm vi lặp lại nằm ngoài lịch dự án | Xác minh ngày `Start` và `Finish` nằm trong thời gian làm việc của dự án |
| Ngoại lệ `ArgumentNullException` khi `Add` | `parameters` là null hoặc chưa được khởi tạo đầy đủ | Đảm bảo tất cả các thuộc tính bắt buộc (TaskName, Duration, RecurrencePattern) được đặt |
| Ngày trong tuần được chọn sai | Giá trị enum `WeekDay` không khớp | Sử dụng `DayOfWeek.Monday` … `DayOfWeek.Sunday` theo nhu cầu |

## Câu hỏi thường gặp

**Q: Tôi có thể tùy chỉnh mẫu lặp lại ngoài ví dụ đã cung cấp không?**  
A: Có, Aspose.Tasks cho phép bạn kết hợp `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern`, hoặc thậm chí các đối tượng `RecurrenceRange` tùy chỉnh để phù hợp với bất kỳ lịch trình nào.

**Q: Aspose.Tasks cho .NET có tương thích với phần mềm quản lý dự án khác không?**  
A: Chắc chắn – thư viện đọc và ghi các định dạng MPP, XML và Primavera, cho phép trao đổi dữ liệu mượt mà.

**Q: Làm thế nào tôi có thể xử lý ngoại lệ hoặc sửa đổi các nhiệm vụ lặp lại?**  
A: Sử dụng lớp `ExceptionTask` để tạo ghi đè cho các lần xuất hiện cụ thể, hoặc chỉnh sửa `RecurringTaskParameters` và lưu lại dự án.

**Q: Aspose.Tasks có hỗ trợ các giải pháp dựa trên đám mây không?**  
A: Có, bạn có thể chạy API trong Azure Functions, AWS Lambda, hoặc bất kỳ dịch vụ đám mây nào tương thích với .NET.

**Q: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Tasks cho .NET từ [website](https://releases.aspose.com/), cho phép bạn khám phá các tính năng trước khi quyết định mua.

**Q: Làm thế nào để thêm một nhiệm vụ lặp lại vào dự án hiện có mà không ghi đè dữ liệu khác?**  
A: Tải dự án hiện có bằng `new Project("Existing.mpp")`, thêm `RecurringTaskParameters` vào `RootTask.Children`, và sau đó `Save` tệp.

## Kết luận

Bằng cách nắm vững **how to use Aspose.Tasks** cho kịch bản **Repetition by Year Week Day**, bạn có khả năng **add recurring task project** các mục nhập phù hợp hoàn hảo với lịch thực tế và **save project as MPP** để hợp tác liền mạch. Hãy tích hợp các đoạn mã này vào giải pháp của bạn để nâng cao độ chính xác lập lịch và giảm công sức thủ công.

---

**Cập nhật lần cuối:** 2026-04-03  
**Đã kiểm tra với:** Aspose.Tasks 24.12 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}