---
date: 2026-04-01
description: Tìm hiểu cách thiết lập chu kỳ trong Aspose.Tasks cho .NET, thêm nhiệm
  vụ lặp lại và tự động hoá các nhiệm vụ lặp lại theo tháng, tuần và ngày.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Lặp lại theo Tháng, Tuần, Ngày trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cách thiết lập chu kỳ trong Aspose.Tasks (Tháng, Tuần, Ngày)
url: /vi/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Lặp Lại trong Aspose.Tasks (Tháng, Tuần, Ngày)

## Giới thiệu

Nếu bạn cần **cách thiết lập lặp lại** cho các nhiệm vụ trong một dự án, Aspose.Tasks cho .NET cung cấp cho bạn một cách sạch sẽ, lập trình để thêm các định nghĩa nhiệm vụ lặp lại chạy theo tháng, tuần hoặc ngày. Trong hướng dẫn này, chúng tôi sẽ đi qua một ví dụ thực tế cho thấy cách **thêm nhiệm vụ lặp lại**, **tự động hoá các nhiệm vụ lặp lại**, và quản lý chúng trực tiếp từ mã C#. Khi kết thúc, bạn sẽ sẵn sàng tích hợp khả năng này vào bất kỳ giải pháp lập lịch hoặc quản lý dự án nào.

## Câu trả lời nhanh
- **“recurrence” có nghĩa là gì trong Aspose.Tasks?** Nó định nghĩa một mẫu (hàng ngày, hàng tuần, hàng tháng) tự động tạo các phiên bản nhiệm vụ trong một khoảng thời gian.  
- **Phương thức chính nào tạo ra lặp lại?** `RecurringTaskParameters` kết hợp với một `RecurrencePattern` cụ thể.  
- **Tôi có cần giấy phép để chạy đoạn mã này không?** Bản dùng thử hoạt động cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể lên lịch nhiệm vụ hàng tuần thay vì hàng tháng không?** Có – thay `MonthlyRecurrencePattern` bằng `WeeklyRecurrencePattern`.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 và các phiên bản sau.

## Lặp lại là gì trong Aspose.Tasks?

Lặp lại là một tập hợp các quy tắc cho phép Aspose.Tasks tạo các phiên bản nhiệm vụ ở các khoảng thời gian định kỳ—hàng ngày, hàng tuần, hoặc hàng tháng—mà không cần sao chép thủ công. Tính năng này rất quan trọng cho các dự án có các hoạt động thường xuyên như họp trạng thái, kiểm tra, hoặc công việc bảo trì.

## Tại sao nên sử dụng tính năng Lặp lại?

- **Tiết kiệm thời gian:** Không cần sao chép‑dán nhiệm vụ thủ công.  
- **Giảm lỗi:** Thư viện đảm bảo ngày và thời lượng nhất quán.  
- **Linh hoạt:** Kết hợp các mẫu (ví dụ, “Chủ nhật đầu tiên của mỗi 2 tháng”).  
- **Tự động hoá:** Hoàn hảo để tạo lịch trong các pipeline CI hoặc công cụ báo cáo.

## Yêu cầu trước

1. **Kiến thức cơ bản về C#** – bạn sẽ viết một vài dòng mã C#.  
2. **Aspose.Tasks cho .NET đã được cài đặt** – tải về từ [download page](https://releases.aspose.com/tasks/net/).  
3. **Tệp dự án .mpp** – chúng tôi sẽ sử dụng `Project1.mpp` làm tệp nguồn.

## Nhập không gian tên

Để bắt đầu, nhập các không gian tên Aspose.Tasks cần thiết:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Bước 1: Tải tệp dự án

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Chúng tôi tạo một thể hiện `Project` trỏ tới một tệp Microsoft Project hiện có.

### Bước 2: Định nghĩa tham số nhiệm vụ lặp lại

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

Ở đây chúng tôi **tạo tham số nhiệm vụ lặp lại**:

- **TaskName** – tên của nhiệm vụ được tạo.  
- **Duration** – thời lượng của mỗi lần xuất hiện.  
- **RecurrencePattern** – mẫu hàng tháng lặp lại mỗi 2 tháng vào Chủ nhật đầu tiên.  
- **RecurrenceRange** – ngày bắt đầu và kết thúc giới hạn lịch trình.

### Bước 3: Thêm nhiệm vụ lặp lại vào dự án

```csharp
project.RootTask.Children.Add(parameters);
```

Dòng này **thêm nhiệm vụ lặp lại** vào gốc của cây dự án.

### Bước 4: Lưu dự án đã cập nhật

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Dự án được lưu dưới dạng tệp `.mpp` mới, hiện chứa lịch trình tự động.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| **Nhiệm vụ không hiển thị** | Phạm vi lặp lại nằm ngoài ngày của dự án. | Xác minh giá trị `Start` và `Finish` nằm trong lịch dự án. |
| **Ngày trong tuần sai** | Không khớp enum `WeekDay`. | Sử dụng `DayOfWeek.Monday` … `DayOfWeek.Sunday` theo nhu cầu. |
| **Lỗi giấy phép** | Chạy mà không có giấy phép hợp lệ trong môi trường sản xuất. | Áp dụng giấy phép tạm thời hoặc đầy đủ trước khi lưu. |

## Câu hỏi thường gặp

### Q1: Tôi có thể tùy chỉnh mẫu lặp lại vượt quá các ví dụ được cung cấp không?

A1: Có, Aspose.Tasks cho .NET cung cấp các tùy chọn tùy chỉnh rộng rãi cho các mẫu lặp lại, cho phép bạn điều chỉnh chúng theo yêu cầu cụ thể của mình.

### Q2: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?

A2: Có, bạn có thể nhận phiên bản dùng thử miễn phí của Aspose.Tasks cho .NET từ [releases page](https://releases.aspose.com/).

### Q3: Làm thế nào tôi có thể nhận hỗ trợ cho Aspose.Tasks cho .NET?

A3: Bạn có thể tìm kiếm trợ giúp và tham gia cộng đồng trên [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q4: Có giấy phép tạm thời cho Aspose.Tasks cho .NET không?

A4: Có, bạn có thể mua giấy phép tạm thời từ [purchase page](https://purchase.aspose.com/temporary-license/) để thử nghiệm và đánh giá.

### Q5: Tôi có thể tìm tài liệu toàn diện cho Aspose.Tasks cho .NET ở đâu?

A5: Bạn có thể tham khảo tài liệu chi tiết [documentation](https://reference.aspose.com/tasks/net/) có trên trang web Aspose để nhận hướng dẫn sâu về việc sử dụng thư viện.

---

**Cập nhật lần cuối:** 2026-04-01  
**Đã kiểm tra với:** Aspose.Tasks 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}