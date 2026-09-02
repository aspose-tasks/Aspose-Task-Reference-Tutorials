---
date: 2026-04-03
description: Học cách lên lịch công việc quản lý dự án và cách thêm công việc lặp
  lại bằng Aspose.Tasks cho .NET, bao gồm lưu dự án dưới dạng MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Lặp lại theo ngày trong năm trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Lập lịch công việc quản lý dự án với lặp lại ngày trong năm trong Aspose.Tasks
url: /vi/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lập lịch công việc quản lý dự án với việc lặp lại ngày trong năm trong Aspose.Tasks

## Giới thiệu

Lập lịch **công việc quản lý dự án** hiệu quả là nền tảng của bất kỳ dự án thành công nào. Khi các công việc lặp lại hàng năm — chẳng hạn như kiểm toán hàng năm, cửa sổ bảo trì, hoặc đánh giá theo mùa — việc xử lý các lần lặp này một cách thủ công có thể gây ra lỗi và tốn thời gian. Aspose.Tasks cho .NET đơn giản hoá quá trình này bằng cách cho phép bạn định nghĩa các mẫu ngày‑năm một cách lập trình, để bạn có thể tập trung vào những gì quan trọng nhất: mang lại giá trị. Trong hướng dẫn này, bạn sẽ học **cách thêm logic công việc lặp lại** dựa trên một ngày cụ thể trong năm và xem chính xác **cách lưu dự án dưới dạng MPP** để tích hợp liền mạch với Microsoft Project.

## Câu trả lời nhanh
- **What does “year day repetition” mean?** Ý nghĩa của “year day repetition” là gì?  
  Nó lên lịch một công việc vào một ngày cụ thể của một tháng cụ thể mỗi năm.  
- **Which API class creates the recurrence?** Lớp API nào tạo ra sự lặp lại?  
  `YearlyRecurrencePattern` kết hợp với `ByYearDayRepetition`.  
- **Can I set a start and end date?** Tôi có thể đặt ngày bắt đầu và kết thúc không?  
  Có, sử dụng `EndByRecurrenceRange`.  
- **What file format is produced?** Định dạng tệp nào được tạo?  
  Dự án được lưu dưới dạng tệp MPP (`SaveFileFormat.Mpp`).  
- **Do I need a license for production?** Tôi có cần giấy phép cho môi trường sản xuất không?  
  Cần giấy phép thương mại cho việc sử dụng không phải đánh giá.

## Yêu cầu trước

Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:

1. Aspose.Tasks for .NET Library: Thư viện Aspose.Tasks cho .NET: Tải xuống và cài đặt thư viện Aspose.Tasks cho .NET từ [website](https://releases.aspose.com/tasks/net/).  
2. Development Environment: Môi trường phát triển: Thiết lập môi trường phát triển phù hợp với Visual Studio hoặc bất kỳ IDE nào bạn ưa thích cho phát triển .NET.  
3. Basic Knowledge of C#: Kiến thức cơ bản về C#: Làm quen với các khái niệm cơ bản của ngôn ngữ lập trình C# để theo dõi các ví dụ mã.  
4. Project Management Concepts: Các khái niệm quản lý dự án: Hiểu biết về các khái niệm quản lý dự án và lập lịch công việc sẽ giúp nắm bắt các nội dung trong hướng dẫn một cách hiệu quả.

## Nhập không gian tên

Trước khi bắt đầu viết mã, hãy nhập các không gian tên cần thiết để hỗ trợ việc thao tác công việc của chúng ta bằng Aspose.Tasks cho .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Bây giờ, chúng ta sẽ phân tích ví dụ đã cung cấp thành nhiều bước và giải thích chi tiết từng bước.

## Cách thêm công việc lặp lại với mẫu ngày trong năm

### Bước 1: Tải tệp dự án

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Ở đây, chúng ta khởi tạo một đối tượng `Project` mới và tải một tệp dự án hiện có có tên **Project1.mpp**.

### Bước 2: Định nghĩa tham số công việc lặp lại

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

Trong bước này, chúng ta định nghĩa các tham số cho công việc lặp lại của mình. Chúng ta chỉ định tên công việc, thời lượng và mẫu lặp lại. Đối với lặp lại hàng năm, chúng ta sử dụng `YearlyRecurrencePattern` và đặt việc lặp lại xảy ra vào **ngày 1 tháng 7** bằng cách dùng `ByYearDayRepetition`. Ngoài ra, chúng ta xác định phạm vi lặp lại từ ngày 1 Tháng 7 2018 đến ngày 1 Tháng 7 2019.

### Bước 3: Thêm công việc vào dự án

```csharp
project.RootTask.Children.Add(parameters);
```

Ở đây, chúng ta thêm các tham số công việc lặp lại đã định nghĩa vào công việc gốc của dự án.

### Bước 4: Lưu dự án dưới dạng MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Cuối cùng, chúng ta **lưu dự án dưới dạng tệp MPP**, để sẵn sàng mở trong Microsoft Project hoặc bất kỳ trình xem tương thích nào.

## Tại sao điều này quan trọng

- **Automation** – Loại bỏ việc nhập thủ công các công việc hàng năm, giảm lỗi con người.  
- **Consistency** – Đảm bảo mẫu ngày‑tháng giống nhau được áp dụng qua nhiều năm.  
- **Integration** – Tệp MPP kết quả có thể được chia sẻ với các bên liên quan phụ thuộc vào Microsoft Project.  

## Những lỗi thường gặp & Mẹo

- **DateTime precision** – Đảm bảo thời gian bắt đầu phù hợp với lịch dự án của bạn; nếu không, công việc có thể hiển thị lệch.  
- **Time zones** – API làm việc với các đối tượng `DateTime`; cân nhắc chuyển đổi sang UTC nếu ứng dụng của bạn hoạt động trên nhiều khu vực.  
- **License enforcement** – Trong chế độ đánh giá, tệp MPP đã lưu có thể chứa watermark; sử dụng giấy phép hợp lệ cho môi trường sản xuất.

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể xử lý các mẫu lặp lại phức tạp không?**  
A: Có, Aspose.Tasks cung cấp hỗ trợ toàn diện cho nhiều mẫu lặp lại, bao gồm lặp lại hàng năm, hàng tháng, hàng tuần và hàng ngày.

**Q: Aspose.Tasks có tương thích với các định dạng tệp dự án khác nhau không?**  
A: Chắc chắn, Aspose.Tasks hỗ trợ các định dạng tệp dự án phổ biến như MPP, XML và CSV, đảm bảo tính tương thích với các công cụ quản lý dự án khác nhau.

**Q: Aspose.Tasks có cung cấp tài liệu và hỗ trợ cho nhà phát triển không?**  
A: Có, các nhà phát triển có thể truy cập tài liệu chi tiết và tìm kiếm trợ giúp từ diễn đàn cộng đồng Aspose.Tasks cho bất kỳ câu hỏi hoặc vấn đề nào họ gặp phải.

**Q: Tôi có thể tùy chỉnh các thuộc tính công việc như thời lượng và ngày bắt đầu bằng Aspose.Tasks không?**  
A: Chắc chắn, Aspose.Tasks cung cấp các API mạnh mẽ để thao tác các thuộc tính công việc một cách động, cho phép nhà phát triển tùy chỉnh thời lượng, ngày bắt đầu, phụ thuộc và hơn thế nữa.

**Q: Aspose.Tasks có phù hợp cho cả dự án quy mô nhỏ và dự án cấp doanh nghiệp không?**  
A: Thực tế, Aspose.Tasks được thiết kế để đáp ứng nhu cầu của các nhà phát triển làm việc trên các dự án ở mọi quy mô, từ các công việc cá nhân đến các dự án doanh nghiệp quy mô lớn.

---

**Cập nhật lần cuối:** 2026-04-03  
**Kiểm thử với:** Aspose.Tasks 24.12 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}