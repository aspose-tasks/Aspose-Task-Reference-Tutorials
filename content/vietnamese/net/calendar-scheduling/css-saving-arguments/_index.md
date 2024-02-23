---
title: Đối số lưu CSS trong Aspose.Tasks
linktitle: Đối số lưu CSS trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách lưu đối số CSS trong Aspose.Tasks cho .NET để tùy chỉnh đầu ra HTML. Tăng cường trình bày với các cài đặt CSS phù hợp.
type: docs
weight: 20
url: /vi/net/calendar-scheduling/css-saving-arguments/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ đi sâu vào quy trình lưu các đối số CSS bằng Aspose.Tasks cho .NET. Cascading Style Sheets (CSS) rất quan trọng để xác định cách trình bày các phần tử HTML. Aspose.Tasks cho phép chúng ta thao tác và lưu các thuộc tính CSS này một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Cài đặt: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET. Bạn có thể tải nó xuống từ[trang mạng](https://releases.aspose.com/tasks/net/).

2. Kiến thức cơ bản: Nên làm quen với môi trường phát triển C# và .NET.

## Nhập không gian tên

Để bắt đầu, hãy nhập các không gian tên cần thiết:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Bước 1: Xác định lệnh gọi lại lưu CSS

Đầu tiên, chúng tôi xác định các phương thức gọi lại lưu CSS để xử lý việc lưu tệp CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Triển khai logic lưu CSS của bạn tại đây
    }
}
```

## Bước 2: Triển khai lệnh gọi lại lưu phông chữ và hình ảnh

Tiếp theo, triển khai các phương thức gọi lại lưu phông chữ và hình ảnh tương tự:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Triển khai logic lưu phông chữ của bạn tại đây
}

public void ImageSaving(ImageSavingArgs args)
{
    // Triển khai logic lưu hình ảnh của bạn tại đây
}
```

## Bước 3: Định cấu hình tùy chọn lưu

Bây giờ, hãy định cấu hình các tùy chọn lưu HTML để sử dụng các lệnh gọi lại đã triển khai:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Định cấu hình tùy chọn lưu HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Bước 4: Lưu dự án với CSS tùy chỉnh

Cuối cùng, lưu dự án của bạn với cài đặt CSS tùy chỉnh:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách lưu đối số CSS bằng Aspose.Tasks cho .NET. Bằng cách xác định các lệnh gọi lại lưu CSS và định cấu hình các tùy chọn lưu HTML, chúng tôi có thể thao tác các thuộc tính CSS một cách hiệu quả theo yêu cầu của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks dành cho .NET là gì?

Câu trả lời 1: Aspose.Tasks for .NET là một API .NET mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình.

### Câu hỏi 2: Tôi có thể tùy chỉnh các thuộc tính CSS khi lưu tệp HTML bằng Aspose.Tasks không?

Câu trả lời 2: Có, bạn có thể xác định lệnh gọi lại lưu CSS để tùy chỉnh các thuộc tính CSS theo nhu cầu của mình.

### Câu hỏi 3: Aspose.Tasks dành cho .NET có tương thích với tất cả các phiên bản của tệp Microsoft Project không?

A3: Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.

### Câu hỏi 4: Tôi có thể tìm tài liệu toàn diện về Aspose.Tasks cho .NET ở đâu?

 A4: Bạn có thể tham khảo[tài liệu](https://reference.aspose.com/tasks/net/) để biết thông tin chi tiết và ví dụ.

### Câu hỏi 5: Aspose.Tasks dành cho .NET có cung cấp hỗ trợ cho các nhà phát triển không?

 Câu trả lời 5: Có, bạn có thể nhận được hỗ trợ từ cộng đồng Aspose.Tasks thông qua[diễn đàn](https://forum.aspose.com/c/tasks/15).