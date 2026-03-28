---
date: 2026-03-24
description: Học cách xử lý bộ nhớ ngoài và cách lưu hình ảnh dự án bằng Aspose.Tasks
  Layout Builder trong .NET. Hướng dẫn chi tiết từng bước kèm ví dụ mã.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Xử lý hết bộ nhớ với Aspose.Tasks Layout Builder (C#)
url: /vi/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xử lý Tràn Bộ nhớ với Aspose.Tasks Layout Builder

## Giới thiệu

Xử lý tràn bộ nhớ là một phần quan trọng trong việc xây dựng các ứng dụng .NET đáng tin cậy làm việc với các tệp dự án lớn. Khi bạn tạo các hình ảnh trực quan bằng Aspose.Tasks Layout Builder, bạn có thể nhanh chóng gặp phải các ngoại lệ liên quan đến bộ nhớ, đặc biệt trên các biểu đồ Gantt phức tạp. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách **xử lý các ngoại lệ bộ nhớ**, **tùy chỉnh giao diện Gantt**, và **lưu ảnh dự án** một cách an toàn, để ứng dụng của bạn vẫn phản hồi nhanh ngay cả khi lịch trình rất lớn.

## Câu trả lời nhanh
- **Quản lý tràn bộ nhớ là gì?** Quản lý việc sử dụng bộ nhớ và bắt các lỗi kiểu `OutOfMemoryException` khi xử lý dữ liệu lớn.  
- **API nào hỗ trợ?** Aspose.Tasks Layout Builder cho .NET.  
- **Kịch bản điển hình?** Kết xuất một biểu đồ Gantt độ phân giải cao sang PNG.  
- **Điều kiện tiên quyết chính?** .NET (Framework 4.5+ hoặc .NET 6) với Aspose.Tasks đã được cài đặt.  
- **Cách bắt lỗi?** Sử dụng các khối `try…catch` cho `ApsLayoutBuilderOutOfMemoryException` và các ngoại lệ liên quan.  

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

1. **C# cơ bản** – bạn nên quen thuộc với cú pháp C# tiêu chuẩn.  
2. **Aspose.Tasks cho .NET** đã được cài đặt. Nếu bạn chưa thêm, tải xuống từ [here](https://releases.aspose.com/tasks/net/).  
3. **Một IDE** như Visual Studio (hoặc VS Code với phần mở rộng C#) để biên dịch và chạy mẫu.  

## Nhập không gian tên

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Hướng dẫn từng bước

### Bước 1: Tải dự án

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Dòng này tải **Blank2010.mpp** vào một thể hiện `Project`, chuẩn bị cho việc trực quan hoá.

### Bước 2: Tùy chỉnh giao diện biểu đồ Gantt

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Ở đây chúng ta **tùy chỉnh giao diện Gantt** bằng cách điều chỉnh các tầng timescale ở giữa và dưới cùng. Thay đổi các tầng này giảm lượng dữ liệu được kết xuất cùng lúc, giúp giảm áp lực bộ nhớ.

### Bước 3: Cấu hình tùy chọn lưu ảnh

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` cho Aspose.Tasks biết cách kết xuất biểu đồ. Chúng ta chọn PNG làm định dạng đầu ra và gắn timescale vào giao diện vừa tùy chỉnh.

### Bước 4: Lưu dự án dưới dạng ảnh

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

Lệnh `Save` **lưu ảnh dự án** bằng các tùy chọn đã định nghĩa ở trên. Nếu dự án rất lớn, đây là thời điểm mà lỗi tràn bộ nhớ có khả năng xuất hiện nhất.

### Bước 5: Xử lý ngoại lệ

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Bằng cách bắt `ApsLayoutBuilderOutOfMemoryException` bạn **xử lý ngoại lệ bộ nhớ** một cách nhẹ nhàng, cung cấp thông báo rõ ràng thay vì làm ứng dụng bị sập. Khối catch thứ hai xử lý các vấn đề về kích thước bitmap có thể phát sinh khi kết xuất các biểu đồ khổng lồ.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **OutOfMemoryException** | Kết xuất một hình ảnh độ phân giải rất cao tiêu tốn RAM nhiều hơn khả năng cấp phát của tiến trình. | Giảm kích thước ảnh, đơn giản hoá các tầng timescale, hoặc chia biểu đồ thành nhiều ảnh. |
| **BitmapInvalidSizeException** | Kích thước bitmap yêu cầu vượt quá giới hạn tối đa của nền tảng. | Giới hạn chiều rộng/chiều cao trong `ImageSaveOptions` hoặc kết xuất theo các đoạn. |
| **Slow performance** | Các tệp dự án lớn yêu cầu nhiều xử lý. | Bật `project.Set(Prj.SaveToCache, true)` trước khi kết xuất, hoặc sử dụng luồng nền. |

## Câu hỏi thường gặp

### Q1: Aspose.Tasks cho .NET là gì?

A1: Aspose.Tasks cho .NET là một API mạnh mẽ cho phép các nhà phát triển thao tác các tệp Microsoft Project một cách lập trình trong các ứng dụng .NET.

### Q2: Làm sao tôi có thể lấy giấy phép tạm thời cho Aspose.Tasks?

A2: Bạn có thể lấy giấy phép tạm thời cho Aspose.Tasks bằng cách truy cập [this link](https://purchase.aspose.com/temporary-license/).

### Q3: Aspose.Tasks có phù hợp để xử lý các tệp dự án lớn không?

A3: Có, Aspose.Tasks cung cấp các tính năng và tối ưu hoá để xử lý các tệp dự án lớn một cách hiệu quả, nhưng các nhà phát triển vẫn cần cân nhắc các chiến lược quản lý bộ nhớ.

### Q4: Tôi có thể tùy chỉnh giao diện biểu đồ Gantt bằng Aspose.Tasks không?

A4: Chắc chắn! Aspose.Tasks cung cấp khả năng tùy chỉnh rộng rãi giao diện và bố cục của biểu đồ Gantt theo yêu cầu của bạn.

### Q5: Tôi có thể tìm thêm trợ giúp và hỗ trợ cho Aspose.Tasks ở đâu?

A5: Bạn có thể tìm thêm trợ giúp và hỗ trợ, cũng như tham gia cộng đồng, trên [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Câu hỏi thường gặp

**Câu hỏi: Làm sao tôi có thể giảm việc sử dụng bộ nhớ khi lưu ảnh dự án?**  
**Trả lời:** Giảm độ phân giải ảnh, giới hạn phạm vi timescale, hoặc lưu biểu đồ thành nhiều đoạn nhỏ hơn.

**Câu hỏi: Có thể truyền luồng ảnh trực tiếp tới phản hồi web không?**  
**Trả lời:** Có, bạn có thể dùng `project.Save(stream, options)` và ghi luồng này vào phản hồi HTTP.

**Câu hỏi: Aspose.Tasks có hỗ trợ .NET Core và .NET 5/6 không?**  
**Trả lời:** Thư viện hoàn toàn tương thích với .NET Core, .NET 5 và .NET 6.

**Câu hỏi: Tôi nên làm gì nếu vẫn gặp lỗi tràn bộ nhớ sau khi tối ưu?**  
**Trả lời:** Xem xét xử lý dự án trên máy có RAM lớn hơn hoặc chuyển việc kết xuất sang dịch vụ nền.

**Câu hỏi: Tôi có thể xuất biểu đồ Gantt sang các định dạng khác ngoài PNG không?**  
**Trả lời:** Có, `ImageSaveOptions` hỗ trợ JPEG, BMP và TIFF bên cạnh PNG.

---

**Cập nhật lần cuối:** 2026-03-24  
**Kiểm tra với:** Aspose.Tasks 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}