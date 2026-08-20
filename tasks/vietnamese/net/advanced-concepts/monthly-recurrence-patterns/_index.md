---
date: 2026-03-08
description: Tìm hiểu cách tạo nhiệm vụ lặp lại hàng tháng trong Aspose.Tasks cho
  .NET với hướng dẫn từng bước này.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cách tạo nhiệm vụ định kỳ hàng tháng trong Aspose.Tasks
url: /vi/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Nhiệm vụ Định kỳ Hàng tháng bằng Aspose.Tasks

## Giới thiệu

Aspose.Tasks cho .NET cho phép bạn thao tác các tệp Microsoft Project một cách lập trình, và một trong những nhu cầu thực tế phổ biến nhất là **tạo lịch nhiệm vụ định kỳ hàng tháng**. Cho dù bạn đang xây dựng công cụ theo dõi dự án, tự động phân bổ nguồn lực, hay tạo các mục công việc bảo trì định kỳ, hướng dẫn này sẽ chỉ cho bạn các bước chính xác để thêm mẫu lặp lại hàng tháng vào một nhiệm vụ.

Trong các phần tiếp theo, bạn sẽ thấy cách thiết lập dự án, xác định các tham số lặp lại, và cuối cùng lưu tệp đã cập nhật — tất cả đều kèm theo giải thích rõ ràng và các mẹo thực tiễn.

## Câu trả lời nhanh
- **Nhiệm vụ định kỳ hàng tháng có nghĩa là gì?** Một nhiệm vụ lặp lại theo mẫu ngày‑hoặc‑tuần được xác định mỗi tháng.  
- **Lớp API nào xử lý việc lặp lại?** `RecurringTaskParameters` cùng với `MonthlyRecurrencePattern`.  
- **Tôi có cần giấy phép để chạy mẫu không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi khoảng thời gian không?** Có – đặt `RepetitionInterval` thành số tháng giữa các lần xuất hiện.  
- **Các định dạng tệp nào được hỗ trợ?** Cả tệp Project `.mpp` và `.xml` đều có thể được tải và lưu.

## Mẫu Lặp lại Hàng tháng là gì?

Mẫu lặp lại hàng tháng cho Microsoft Project (và Aspose.Tasks) biết tần suất một nhiệm vụ nên lặp lại mỗi tháng. Bạn có thể chỉ định ngày cố định trong tháng (ví dụ: ngày 1) hoặc vị trí tương đối (ví dụ: thứ Sáu cuối cùng). API chuyển các quy tắc này thành cấu trúc tệp Project nền tảng.

## Tại sao nên sử dụng Aspose.Tasks cho việc này?

- **Kiểm soát đầy đủ** – Không có giới hạn giao diện người dùng; bạn định nghĩa mọi khía cạnh của mẫu trong mã.  
- **Đa nền tảng** – Hoạt động trên .NET Framework, .NET Core và .NET 5/6+.  
- **Không cần Microsoft Project** – Tạo hoặc chỉnh sửa tệp trên máy chủ hoặc trong pipeline CI.  

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- .NET 6 (hoặc .NET 5/Framework 4.7+) đã được cài đặt.  
- Gói NuGet Aspose.Tasks cho .NET đã được thêm vào dự án của bạn.  
- Một tệp Project mẫu (`Project1.mpp`) được đặt trong thư mục đã biết (`DataDir`).  

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cần thiết để làm việc với nhiệm vụ và lưu dự án:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Bước 1: Khởi tạo Project

Tạo một thể hiện `Project` trỏ tới tệp `.mpp` hiện có của bạn. Điều này sẽ tải tệp vào bộ nhớ để bạn có thể chỉnh sửa.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Mẹo chuyên nghiệp:** Nếu tệp không tồn tại, Aspose.Tasks sẽ tự động tạo một dự án trống mới.

## Bước 2: Đặt Tham số Nhiệm vụ Định kỳ

Xác định chi tiết của nhiệm vụ định kỳ, bao gồm tên, thời lượng và mẫu hàng tháng bạn muốn áp dụng.

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

- `DayPosition = 1` có nghĩa là nhiệm vụ xảy ra vào **ngày đầu tiên** của tháng.  
- `RepetitionInterval = 2` làm cho nhiệm vụ lặp lại **mỗi hai tháng**.  
- `Start` và `Finish` xác định khoảng thời gian tổng thể mà trong đó mẫu lặp lại đang hoạt động.

## Bước 3: Thêm Tham số vào Project

Gắn đối tượng `RecurringTaskParameters` vào bộ sưu tập con của task gốc. Điều này thực tế tạo ra nhiệm vụ định kỳ trong cấu trúc dự án.

```csharp
project.RootTask.Children.Add(parameters);
```

## Bước 4: Lưu Project

Lưu các thay đổi bằng cách lưu dự án vào một tệp mới. Bạn có thể chọn bất kỳ định dạng nào được hỗ trợ; ở đây chúng tôi sử dụng định dạng gốc `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Sau khi chạy mã, mở tệp kết quả trong Microsoft Project để xem nhiệm vụ định kỳ hàng tháng mà bạn vừa tạo.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Nhiệm vụ không hiển thị sau khi lưu | Dự án không được làm mới trong giao diện người dùng | Mở lại tệp hoặc gọi `project.UpdateTaskLinks()` trước khi lưu. |
| Ngày bắt đầu sai | `Start` được đặt vào cuối tuần | Sử dụng `DateTime` rơi vào ngày làm việc hoặc điều chỉnh lịch. |
| Khoảng thời gian lặp lại bị bỏ qua | Sử dụng `ByMonthDayRepetition` với `DayPosition` = 0 | Đảm bảo `DayPosition` nằm trong khoảng 1‑31. |

## Kết luận

Bằng cách thực hiện các bước này, bạn đã biết cách **tạo lịch nhiệm vụ định kỳ hàng tháng** với Aspose.Tasks cho .NET. API cung cấp cho bạn khả năng kiểm soát chi tiết các khoảng thời gian lặp lại, phạm vi bắt đầu/kết thúc và mẫu ngày cụ thể, cho phép tự động hoá các kịch bản lập kế hoạch dự án phức tạp.

## Câu hỏi thường gặp

### Q1: Aspose.Tasks có tương thích với mọi phiên bản tệp Microsoft Project không?

A1: Aspose.Tasks hỗ trợ nhiều phiên bản tệp Microsoft Project, bao gồm MPP, MPT, XML và MPX.

### Q2: Tôi có thể tùy chỉnh mẫu lặp lại thêm không?

A2: Có, Aspose.Tasks cung cấp nhiều tùy chọn để tùy chỉnh mẫu lặp lại, bao gồm hàng ngày, hàng tuần, hàng tháng và hàng năm.

### Q3: Có bản dùng thử miễn phí cho Aspose.Tasks không?

A3: Có, bạn có thể nhận bản dùng thử miễn phí của Aspose.Tasks từ trang web [here](https://releases.aspose.com/).

### Q4: Làm thế nào để tôi nhận được hỗ trợ cho Aspose.Tasks?

A4: Bạn có thể tìm kiếm trợ giúp và tham gia thảo luận trên [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Tôi có thể mua giấy phép cho Aspose.Tasks ở đâu?

A5: Bạn có thể mua giấy phép cho Aspose.Tasks từ trang web [here](https://purchase.aspose.com/buy)

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng đoạn mã này trong ứng dụng .NET Core không?**  
A: Chắc chắn. Aspose.Tasks cho .NET hoàn toàn hỗ trợ .NET Core 3.1 và các phiên bản sau.

**Q: Làm thế nào để thay đổi lặp lại thành “ngày làm việc cuối cùng của tháng”?**  
A: Sử dụng `ByMonthDayRepetition` với `DayPosition = -1` (giá trị âm đếm từ cuối tháng) và đặt `WeekDay` cho phù hợp.

**Q: Điều gì sẽ xảy ra nếu phạm vi lặp lại vượt quá lịch của dự án?**  
A: API tuân theo lịch dự án; các lần xuất hiện rơi vào ngày không làm việc sẽ bị bỏ qua hoặc được di chuyển tùy theo cài đặt của lịch.

**Q: Có thể xóa một lần xuất hiện cụ thể của nhiệm vụ định kỳ không?**  
A: Có. Sau khi thêm nhiệm vụ định kỳ, bạn có thể lấy các lần xuất hiện riêng lẻ bằng `Task.GetOccurrences()` và xóa những lần không cần thiết.

**Q: Aspose.Tasks có tự động xử lý sự khác biệt múi giờ không?**  
A: Thư viện lưu ngày giờ ở dạng UTC; bạn có thể chuyển sang giờ địa phương bằng các phương thức chuẩn của .NET `DateTime` nếu cần.

---

**Cập nhật lần cuối:** 2026-03-08  
**Đã kiểm tra với:** Aspose.Tasks 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}