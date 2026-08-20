---
date: 2026-03-05
description: Tìm hiểu cách lưu hình ảnh, tạo HTML có hình ảnh và tùy chỉnh xuất hình
  ảnh bằng Aspose.Tasks cho .NET. Hướng dẫn từng bước để lưu dự án dưới dạng HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Cách lưu hình ảnh bằng Aspose.Tasks cho .NET
url: /vi/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Lưu Hình Ảnh với Aspose.Tasks cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá **cách lưu hình ảnh** từ các tệp Microsoft Project bằng API Aspose.Tasks cho .NET. Dù bạn cần nhúng biểu đồ vào báo cáo, tạo các trang HTML chứa hình ảnh dự án, hay chỉ đơn giản xuất các tài nguyên dạng sơ đồ, các bước dưới đây sẽ hướng dẫn bạn toàn bộ quy trình — từ việc thiết lập đối tượng dự án đến tùy chỉnh các callback xuất hình ảnh.

## Trả lời nhanh
- **“how to save images” có nghĩa là gì trong Aspose.Tasks?**  
  Nó đề cập đến việc sử dụng giao diện `IImageSavingCallback` để kiểm soát nơi và cách các tài nguyên hình ảnh được ghi ra đĩa.
- **Tôi có thể lưu dự án dưới dạng HTML có nhúng hình ảnh không?**  
  Có, bằng cách sử dụng `HtmlSaveOptions` kết hợp với các callback lưu hình ảnh, bạn có thể **lưu dự án dưới dạng HTML** bao gồm tất cả các hình ảnh được tạo.
- **Có cần giấy phép để xuất hình ảnh không?**  
  Giấy phép đánh giá tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.
- **Các phiên bản .NET nào được hỗ trợ?**  
  Aspose.Tasks cho .NET hỗ trợ .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.
- **Có thể tùy chỉnh xuất hình ảnh (định dạng, thư mục, đặt tên) không?**  
  Hoàn toàn có – callback cho phép bạn kiểm soát toàn bộ tên tệp, định dạng và vị trí lưu.

## “how to save images” trong ngữ cảnh Aspose.Tasks là gì?
Lưu hình ảnh có nghĩa là trích xuất các yếu tố trực quan (biểu đồ, thanh Gantt, đồ họa tài nguyên) từ tệp Project và ghi chúng thành các tệp hình ảnh (PNG, JPEG, …). Aspose.Tasks cung cấp một cơ chế callback linh hoạt, cho phép bạn quyết định vị trí chính xác, quy tắc đặt tên và thậm chí định dạng hình ảnh.

## Tại sao nên dùng Aspose.Tasks để lưu hình ảnh?
- **Kiểm soát hoàn toàn bằng mã** – không cần tương tác UI thủ công.  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS thông qua .NET Core.  
- **Kết xuất chất lượng cao** – hình ảnh giữ nguyên độ nét như trong chế độ xem Project gốc.  
- **Tạo HTML dễ dàng** – kết hợp `HtmlSaveOptions` với các callback hình ảnh để **tự động tạo HTML có hình ảnh**.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn bạn đã có:

1. Visual Studio được cài đặt trên máy phát triển.  
2. Aspose.Tasks cho .NET tải về từ [đây](https://releases.aspose.com/tasks/net/).  
3. Kiến thức cơ bản về C# và cấu trúc dự án .NET.

## Nhập không gian tên

Đầu tiên, đưa các không gian tên cần thiết vào file nguồn của bạn:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Bước 1: Tạo đối tượng Project

Tải tệp Microsoft Project mà bạn muốn làm việc:

```csharp
var project = new Project("Project1.mpp");
```

## Bước 2: Định nghĩa tùy chọn lưu

Tạo các tùy chọn lưu HTML, đồng thời chứa các callback lưu hình ảnh của chúng ta:

```csharp
var options = GetSaveOptions(1);
```

## Bước 3: Lưu dự án dưới dạng HTML (save project as html)

Bây giờ xuất dự án ra tệp HTML. Các hình ảnh được tham chiếu trong HTML sẽ được tạo bởi callback mà chúng ta sẽ định nghĩa tiếp theo:

```csharp
project.Save("document_out.html", options);
```

## Bước 4: Triển khai Callback Lưu Hình Ảnh (customize image export)

Triển khai giao diện `IImageSavingCallback`. Đây là nơi bạn **tùy chỉnh hành vi xuất hình ảnh**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Bước 5: Lưu hình ảnh vào thư mục chỉ định

Trong phương thức `ImageSaving`, quyết định nơi mỗi hình ảnh sẽ được lưu. Ví dụ dưới đây phân biệt tài nguyên PNG với các định dạng khác:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Bước 6: Chỉ định tùy chọn lưu (bao gồm các callback)

Kết nối các callback cho phông chữ, CSS và hình ảnh. Điều này đảm bảo mọi yếu tố trực quan đều được xử lý một cách nhất quán:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Hình ảnh không hiển thị trong HTML được tạo | Callback không gán đường dẫn tệp hợp lệ | Đảm bảo `args.Path` trỏ tới thư mục có quyền ghi và đặt `args.ImageStream` đúng cách. |
| Tệp PNG được lưu với phần mở rộng sai | Logic kiểm tra chỉ dựa vào hậu tố “png” | Sử dụng `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` để phát hiện chính xác. |
| Liên kết HTML bị hỏng sau khi di chuyển tệp | Đường dẫn tương đối thay đổi khi di chuyển thư mục đầu ra | Giữ nguyên cấu trúc thư mục HTML và hình ảnh cùng nhau hoặc cập nhật `options.ImageFolder` cho phù hợp. |

## Kết luận

Sau khi thực hiện các bước trên, bạn đã biết **cách lưu hình ảnh** từ tệp Project, **lưu dự án dưới dạng HTML**, và **tùy chỉnh xuất hình ảnh** để phù hợp với cấu trúc thư mục của ứng dụng. Cách tiếp cận này cho phép bạn **tạo HTML có hình ảnh** có thể nhúng vào báo cáo, cổng tài liệu hoặc bảng điều khiển web một cách liền mạch.

## Câu hỏi thường gặp

**Q1: Tôi có thể dùng Aspose.Tasks để thao tác tệp dự án ở các định dạng khác ngoài HTML không?**  
A1: Có, Aspose.Tasks hỗ trợ nhiều định dạng như PDF, XLSX và MPP.

**Q2: Aspose.Tasks có hỗ trợ tích hợp lưu trữ đám mây không?**  
A2: Có, Aspose.Tasks cung cấp API làm việc với các dịch vụ lưu trữ đám mây phổ biến như Amazon S3 và Google Drive.

**Q3: Aspose.Tasks có tương thích với .NET Core không?**  
A3: Có, Aspose.Tasks tương thích với .NET Core, cho phép bạn phát triển ứng dụng đa nền tảng.

**Q4: Tôi có thể tùy chỉnh giao diện của các hình ảnh đã lưu không?**  
A4: Có, bạn có thể tùy chỉnh giao diện của hình ảnh bằng cách sửa đổi logic lưu hình ảnh trong các phương thức callback.

**Q5: Aspose.Tasks có cung cấp phiên bản dùng thử để đánh giá không?**  
A5: Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks từ [đây](https://releases.aspose.com/).

---

**Cập nhật lần cuối:** 2026-03-05  
**Đã kiểm tra với:** Aspose.Tasks 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}