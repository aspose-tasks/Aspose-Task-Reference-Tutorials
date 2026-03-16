---
date: 2026-03-16
description: Tìm hiểu cách triển khai callback lưu trang trong Aspose.Tasks cho .NET,
  cho phép xử lý tùy chỉnh luồng đầu ra của tài liệu đa trang.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Thực hiện callback lưu trang trong Aspose.Tasks
url: /vi/net/advanced-concepts/page-saving-callback/
weight: 12
---

-16  
**Đã kiểm tra với:** Aspose.Tasks 24.12 cho .NET  
**Tác giả:** Aspose  

Now the closing shortcodes.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Triển khai callback lưu trang trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học cách **triển khai callback lưu trang** trong Aspose.Tasks cho .NET. Tính năng mạnh mẽ này cho phép bạn chỉ định mỗi trang của tài liệu đa trang tới một stream mà bạn chọn, cung cấp cho bạn toàn quyền kiểm soát cách lưu trữ hoặc xử lý đầu ra.

## Câu trả lời nhanh
- **Callback lưu trang làm gì?** Nó ghi lại mỗi trang đã render vào một stream riêng biệt để bạn có thể xử lý chúng từng cái một.  
- **Tôi có thể xuất sang định dạng nào?** Bất kỳ định dạng nào được `ImageSaveOptions` hỗ trợ, ví dụ: PNG, JPEG, PDF.  
- **Tôi có cần giấy phép không?** Cần có giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.  
- **Có thể sử dụng với .NET Core không?** Có, Aspose.Tasks hoàn toàn hỗ trợ .NET Core và .NET 5/6+.  
- **Callback có an toàn đa luồng không?** Callback chạy trên cùng một luồng thực hiện việc render, vì vậy các quy tắc an toàn luồng thông thường áp dụng.

## **Triển khai callback lưu trang** là gì?
Mẫu **triển khai callback lưu trang** cho phép bạn chèn logic tùy chỉnh vào quy trình lưu của Aspose.Tasks. Thay vì ghi trực tiếp vào tệp, bạn nhận được một đối tượng `Stream` cho mỗi trang, cho phép lưu trữ trong bộ nhớ, tải lên lưu trữ đám mây, hoặc thực hiện xử lý bổ sung.

## Tại sao xuất dự án dưới dạng PNG với callback?
Xuất dự án dưới dạng PNG cung cấp cho bạn hình ảnh raster của mỗi trang biểu đồ Gantt, rất phù hợp cho báo cáo, email, hoặc nhúng vào trang web. Sử dụng callback có nghĩa là bạn có thể giữ mỗi trang trong một `MemoryStream` riêng biệt mà không cần tạo các tệp tạm trên đĩa.

## Yêu cầu trước

1. **Kiến thức C#** – hiểu biết cơ bản về lớp, giao diện và stream.  
2. **Aspose.Tasks cho .NET** – tải xuống và cài đặt từ [here](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider, hoặc bất kỳ trình soạn thảo nào tương thích với .NET.

## Nhập không gian tên

Để bắt đầu, nhập các không gian tên cần thiết:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Bước 1: Tạo đối tượng Project

Tải một tệp MPP hiện có vào một thể hiện `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Bước 2: Cấu hình Image Save Options

Thiết lập `ImageSaveOptions` cho đầu ra PNG và gắn callback tùy chỉnh:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Mẹo chuyên nghiệp:** Đặt `RenderToSinglePage = false` đảm bảo mỗi trang biểu đồ Gantt được render riêng biệt, điều này rất cần thiết để callback nhận được các stream riêng.

## Bước 3: Lưu Project với Callback

Gọi phương thức `Save`, truyền `Stream.Null` vì các stream thực tế được cung cấp bởi callback:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Bước 4: Xử lý các Stream trang đã lưu

Sau khi thao tác lưu hoàn tất, callback giữ một bộ sưu tập các đối tượng `MemoryStream` — một cho mỗi trang. Bạn có thể duyệt qua chúng ngay bây giờ:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Bước 5: Triển khai Custom Page Saving Callback

Tạo một lớp sealed triển khai `IPageSavingCallback`. Lớp này ghi lại stream của mỗi trang và lưu vào danh sách để sử dụng sau.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Các lỗi thường gặp & Khắc phục

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|-----------|
| **Không có trang nào được trả về** | `RenderToSinglePage` để là `true`. | Đặt `RenderToSinglePage = false` để tạo các trang riêng biệt. |
| **Streams rỗng** | `KeepStreamOpen` được đặt thành `true` mà không giải phóng sau này. | Giữ nó là `false` (mặc định) và để callback tự động đóng các stream. |
| **Lỗi hết bộ nhớ** | Các dự án rất lớn tạo ra nhiều PNG độ phân giải cao. | Xử lý các stream từng cái một hoặc tăng giới hạn bộ nhớ VM. |

## Câu hỏi thường gặp

**Q1: Callback lưu trang là gì trong Aspose.Tasks?**  
A: Callback lưu trang cho phép bạn chặn quá trình lưu cho mỗi trang của tài liệu đa trang, cung cấp một `Stream` tùy chỉnh cho trang đó.

**Q2: Tôi có thể sử dụng các định dạng khác nhau để lưu các trang bằng callback này không?**  
A: Có. Bằng cách thay đổi `SaveFileFormat` bạn có thể xuất sang PNG, JPEG, PDF, SVG, v.v.

**Q3: Aspose.Tasks có tương thích với .NET Core không?**  
A: Hoàn toàn. Aspose.Tasks hỗ trợ .NET Core, .NET 5 và .NET 6.

**Q4: Làm sao để xử lý lỗi trong quá trình lưu trang?**  
A: Bao bọc logic callback trong khối try/catch và ghi log ngoại lệ. Phương thức `OnFinish` là nơi tốt để thực hiện dọn dẹp cuối cùng.

**Q5: Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Tasks ở đâu?**  
A: Bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ, xem tài liệu [tại đây](https://reference.aspose.com/tasks/net/), hoặc khám phá các tính năng và tùy chọn giấy phép bổ sung trên [trang web Aspose.Tasks](https://purchase.aspose.com/buy).

**Cập nhật lần cuối:** 2026-03-16  
**Đã kiểm tra với:** Aspose.Tasks 24.12 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}