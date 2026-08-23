---
date: 2026-03-21
description: Học cách xuất hình ảnh và xử lý ngoại lệ BitmapInvalidSizeException khi
  lưu dự án dưới dạng hình ảnh trong Aspose.Tasks cho .NET. Bao gồm các bước lưu dự
  án dưới dạng hình ảnh và xuất dự án sang PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cách xuất ảnh và xử lý ngoại lệ kích thước không hợp lệ
url: /vi/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Xuất Hình Ảnh – Xử Lý Ngoại Lệ Kích Thước Không Hợp Lệ cho Bitmap trong Aspose.Tasks

Trong hướng dẫn này bạn sẽ học **cách xuất hình ảnh** từ tệp Microsoft Project bằng Aspose.Tasks cho .NET và, quan trọng hơn, cách bắt `BitmapInvalidSizeException` có thể xảy ra trong quá trình này. Việc xuất dự án dưới dạng hình ảnh là yêu cầu phổ biến cho các bảng điều khiển báo cáo, tài liệu, hoặc chỉ đơn giản là chia sẻ một ảnh chụp nhanh của lịch trình. Khi hoàn thành hướng dẫn này, bạn sẽ có thể **lưu dự án dưới dạng hình ảnh** một cách đáng tin cậy và thậm chí **xuất dự án sang định dạng PNG** mà không gặp sự cố bất ngờ.

## Trả Lời Nhanh
- **Ngoại lệ nào có thể xảy ra khi xuất hình ảnh?** `BitmapInvalidSizeException`  
- **Định dạng nào được sử dụng trong ví dụ?** PNG (`SaveFileFormat.Png`)  
- **Tôi có cần giấy phép đặc biệt không?** Cần một giấy phép Aspose.Tasks hợp lệ cho môi trường sản xuất.  
- **Tôi có thể thay đổi thang thời gian không?** Có – bạn có thể đặt đơn vị thang thời gian (phút, giờ, ngày, v.v.).  
- **Mã có tương thích với .NET Core không?** Hoàn toàn – cùng một API hoạt động trên .NET Framework và .NET Core.

## BitmapInvalidSizeException là gì?
`BitmapInvalidSizeException` được ném ra khi kích thước bitmap được tính cho hình ảnh nằm ngoài phạm vi hỗ trợ (ví dụ: chiều rộng hoặc chiều cao bằng 0 hoặc vượt quá giới hạn nội bộ). Thông thường điều này xảy ra khi cài đặt thang thời gian hoặc chế độ xem tạo ra một hình ảnh quá lớn hoặc quá nhỏ.

## Tại sao phải xuất dự án dưới dạng hình ảnh?
- **Báo cáo trực quan** – nhúng biểu đồ Gantt vào PDF, tài liệu Word hoặc trang web.  
- **Chia sẻ đa nền tảng** – tệp PNG có thể xem trên bất kỳ thiết bị nào mà không cần Microsoft Project.  
- **Hiệu suất** – hình ảnh nhẹ hơn so với tệp dự án đầy đủ, phù hợp cho việc xem trước nhanh.

## Yêu Cầu Trước
1. Kiến thức cơ bản về C# và phát triển .NET.  
2. Aspose.Tasks cho .NET đã được cài đặt (gói NuGet `Aspose.Tasks`).  
3. Một tệp Microsoft Project mẫu (ví dụ: `Blank2010.mpp`).  

## Nhập Các Namespace
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Hướng Dẫn Từng Bước

### Bước 1: Khởi Tạo Project và Chọn View
Đầu tiên, tạo một thể hiện `Project` và chọn view bạn muốn render (ở đây chúng ta dùng view Gantt chart đầu tiên).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Bước 2: Cấu Hình Image Save Options (Xuất Dự Án sang PNG)
Đặt định dạng hình ảnh mong muốn và cho Aspose.Tasks biết sử dụng thang thời gian được định nghĩa trong view.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Bước 3: Điều Chỉnh Đơn Vị Thang Thời Gian (Kiểm Soát Kích Thước Hình Ảnh)
Thay đổi thang thời gian sẽ ảnh hưởng đến kích thước bitmap. Trong ví dụ này chúng ta dùng **phút** để giữ kích thước hình ảnh ở mức vừa phải.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Bước 4: Thực Hiện Lưu Dự Án dưới Dạng Hình Ảnh
Dòng lệnh này thực hiện thao tác **lưu dự án dưới dạng hình ảnh** thực tế.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Bước 5: Bắt và Xử Lý BitmapInvalidSizeException
Bao bọc lời gọi lưu trong khối `try / catch` để ứng dụng của bạn có thể phản hồi một cách mềm dẻo nếu kích thước bitmap không hợp lệ.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Các Vấn Đề Thường Gặp và Giải Pháp
| Issue | Cause | Solution |
|-------|-------|----------|
| Exception still thrown after adjusting timescale | Timescale still results in too large bitmap | Reduce `view.MiddleTimescaleTier.Count` or switch to a coarser `TimescaleUnit` (e.g., Hours). |
| Output file is empty | Incorrect file path or missing write permissions | Verify `DataDir` points to a writable folder and the filename ends with `.png` if you change the format. |
| Image quality is poor | Default DPI may be low | Set `options.DpiX` and `options.DpiY` to higher values (e.g., 300). |

## Câu Hỏi Thường Gặp

**Q: Nguyên nhân gây ra BitmapInvalidSizeException trong Aspose.Tasks là gì?**  
A: Nó xảy ra khi kích thước bitmap được tính toán không hợp lệ — thường là do thang thời gian tạo ra một hình ảnh quá lớn hoặc có chiều rộng/chiều cao bằng 0.

**Q: Tôi có thể tùy chỉnh thang thời gian khi xuất hình ảnh không?**  
A: Có. Bạn có thể sửa đổi `view.MiddleTimescaleTier.Unit` và `Count` để phù hợp với nhu cầu, như đã minh họa trong hướng dẫn.

**Q: Aspose.Tasks có hỗ trợ các định dạng hình ảnh khác ngoài PNG không?**  
A: Chắc chắn. `SaveFileFormat` còn bao gồm JPEG, BMP, GIF và TIFF. Chỉ cần thay đổi giá trị enum trong `ImageSaveOptions`.

**Q: Có cần giấy phép để xuất hình ảnh trong môi trường sản xuất không?**  
A: Có. Mặc dù thư viện hoạt động ở chế độ đánh giá, một giấy phép thương mại sẽ loại bỏ các hạn chế đánh giá và cung cấp hỗ trợ đầy đủ.

**Q: Làm sao tôi có thể cải thiện chất lượng PNG xuất ra?**  
A: Tăng cài đặt DPI (`options.DpiX` và `options.DpiY`) hoặc điều chỉnh thang thời gian của view để tạo bitmap lớn hơn.

## Kết Luận
Sau khi thực hiện các bước trên, bạn đã biết **cách xuất hình ảnh** từ tệp Project, **cách lưu dự án dưới dạng hình ảnh**, và cách xử lý một cách mềm dẻo `BitmapInvalidSizeException`. Những kỹ thuật này giúp quy trình báo cáo của bạn trở nên vững chắc hơn và đảm bảo việc xuất hình ảnh hoạt động ổn định trên các kích thước và thang thời gian dự án khác nhau.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

---