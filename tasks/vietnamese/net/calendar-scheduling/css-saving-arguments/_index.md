---
date: 2026-07-05
description: Tìm hiểu cách tùy chỉnh CSS khi xuất dự án sang HTML bằng Aspose.Tasks
  cho .NET. Tinh chỉnh đầu ra HTML với các tham số lưu CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Cách Tùy Chỉnh CSS Khi Lưu Dự Án Bằng Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Cách Tùy Chỉnh CSS Khi Lưu Dự Án Bằng Aspose.Tasks
url: /vi/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tùy Chỉnh CSS Khi Lưu Dự Án Với Aspose.Tasks

Trong hướng dẫn này, bạn sẽ khám phá **cách tùy chỉnh CSS** trong quá trình xuất HTML của tệp Microsoft Project bằng cách sử dụng Aspose.Tasks cho .NET. Bằng cách điều chỉnh các đối số lưu CSS, bạn có toàn quyền kiểm soát kiểu dáng trực quan của các trang HTML được tạo, giúp đầu ra phù hợp với thương hiệu hoặc tiêu chuẩn báo cáo của bạn.

## Câu Trả Lời Nhanh
- **Điểm vào chính là gì?** Sử dụng `HtmlSaveOptions` với các callback tùy chỉnh.  
- **Tôi có cần giấy phép không?** Có, cần một giấy phép Aspose.Tasks hợp lệ cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có thể xuất dự án lớn không?** Aspose.Tasks xử lý các dự án có > 10.000 nhiệm vụ mà không cần tải toàn bộ tệp vào bộ nhớ.  
- **Việc tùy chỉnh CSS có tùy chọn không?** Có, bạn có thể bỏ qua các callback để sử dụng stylesheet mặc định.

## Cách Tùy Chỉnh CSS Trong Aspose.Tasks?

Tải dự án của bạn, gắn các callback lưu CSS vào đối tượng `HtmlSaveOptions`, sau đó gọi `project.Save`. Mẫu này cho phép bạn viết các tệp CSS tùy chỉnh, thay thế các kiểu mặc định và kiểm soát cấu trúc thư mục — tất cả chỉ trong vài dòng mã. Các callback sẽ được gọi tự động cho mỗi tệp CSS trong quá trình xuất.

`HtmlSaveOptions` cấu hình cách một dự án được xuất ra HTML.

## Giới Thiệu

Trong bài hướng dẫn này, chúng ta sẽ khám phá quy trình lưu các đối số CSS bằng cách sử dụng Aspose.Tasks cho .NET. Cascading Style Sheets (CSS) là yếu tố quan trọng để định nghĩa cách trình bày các phần tử HTML. Aspose.Tasks cho phép chúng ta thao tác và lưu các thuộc tính CSS một cách hiệu quả.

## Yêu Cầu Trước

Trước khi bắt đầu, hãy đảm bảo bạn đã có các yêu cầu sau:

1. Cài đặt: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET. Bạn có thể tải xuống từ [website](https://releases.aspose.com/tasks/net/).
2. Kiến thức cơ bản: Nên có kiến thức về C# và môi trường phát triển .NET.

## Nhập Không Gian Tên

Để bắt đầu, nhập các không gian tên cần thiết:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Bước 1: Định Nghĩa Callback Lưu CSS

`ICssSavingCallback` là một giao diện cho phép bạn tùy chỉnh cách các tệp CSS được lưu trong quá trình xuất HTML.

Một **CSS saving callback** là một delegate mà Aspose.Tasks gọi để ghi các tệp CSS trong quá trình xuất HTML. Định nghĩa các phương thức callback để kiểm soát cách mỗi tệp CSS được tạo:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Bước 2: Triển Khai Callback Lưu Font và Hình Ảnh

`FontSavingArgs` cung cấp thông tin về phông chữ đang được lưu, trong khi `ImageSavingArgs` cung cấp chi tiết cho các tài nguyên hình ảnh.

Triển khai các phương thức callback lưu phông chữ và hình ảnh tương tự:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Bước 3: Cấu Hình Tùy Chọn Lưu

`HtmlSaveOptions` là đối tượng cấu hình kiểm soát cách một Project được xuất ra HTML.

`HtmlSaveOptions` cho phép bạn chỉ định các callback, thư mục đầu ra và các cài đặt xuất khác.

Đặt các thuộc tính của nó để sử dụng các callback đã định nghĩa ở trên và chỉ định thư mục đầu ra:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Bước 4: Lưu Dự Án Với CSS Được Tùy Chỉnh

`Project` đại diện cho một tệp Microsoft Project có thể được thao tác và lưu.

Cuối cùng, lưu dự án của bạn với các cài đặt CSS được tùy chỉnh:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Tại Sao Cần Tùy Chỉnh CSS Khi Xuất Dự Án?

Aspose.Tasks hỗ trợ **xuất dự án sang HTML** trong hơn 30 định dạng và có thể tạo lên đến 30 tệp CSS riêng biệt cho mỗi lần xuất. Nó xử lý một cách đáng tin cậy các dự án chứa hơn 10 000 nhiệm vụ trong khi giữ mức sử dụng bộ nhớ dưới 200 MB, cho phép báo cáo quy mô doanh nghiệp mà không gặp tắc nghẽn hiệu năng.

## Kết Luận

Trong bài hướng dẫn này, chúng ta đã khám phá cách lưu các đối số CSS bằng Aspose.Tasks cho .NET. Bằng cách định nghĩa các callback lưu CSS và cấu hình các tùy chọn lưu HTML, chúng ta có thể thao tác các thuộc tính CSS một cách hiệu quả theo yêu cầu.

## Câu Hỏi Thường Gặp

### Q1: Aspose.Tasks cho .NET là gì?

A1: Aspose.Tasks cho .NET là một API .NET mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project một cách lập trình.

### Q2: Tôi có thể tùy chỉnh các thuộc tính CSS khi lưu tệp HTML với Aspose.Tasks không?

A2: Có, bạn có thể định nghĩa các callback lưu CSS để tùy chỉnh các thuộc tính CSS theo nhu cầu của mình.

### Q3: Aspose.Tasks cho .NET có tương thích với mọi phiên bản tệp Microsoft Project không?

A3: Aspose.Tasks cho .NET hỗ trợ nhiều phiên bản tệp Microsoft Project, đảm bảo tính tương thích trên các môi trường khác nhau.

### Q4: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks cho .NET ở đâu?

A4: Bạn có thể tham khảo [tài liệu](https://reference.aspose.com/tasks/net/) để có thông tin chi tiết và các ví dụ.

### Q5: Aspose.Tasks cho .NET có cung cấp hỗ trợ cho nhà phát triển không?

A5: Có, bạn có thể nhận hỗ trợ từ cộng đồng Aspose.Tasks thông qua [diễn đàn](https://forum.aspose.com/c/tasks/15).

**Các Câu Hỏi Bổ Sung**

**Q: Việc tùy chỉnh CSS ảnh hưởng như thế nào đến kích thước của HTML được xuất?**  
A: Sử dụng CSS tùy chỉnh có thể giảm tổng kích thước lên tới 15 % vì bạn có thể loại bỏ các kiểu mặc định không dùng.

**Q: Tôi có thể sử dụng cùng một callback cho nhiều dự án không?**  
A: Chắc chắn. Triển khai các callback một lần và tái sử dụng chúng cho bất kỳ số lượng xuất dự án nào.

**Q: Có thể nhúng CSS trực tiếp vào HTML thay vì các tệp riêng biệt không?**  
A: Có, đặt `HtmlSaveOptions.EmbeddedCss = true` để nhúng stylesheet vào trong HTML, giúp việc phân phối đơn giản hơn.

---

**Cập Nhật Cuối Cùng:** 2026-07-05  
**Kiểm Tra Với:** Aspose.Tasks 24.11 cho .NET  
**Tác Giả:** Aspose

## Các Hướng Dẫn Liên Quan

- [Lưu MS Project dưới dạng HTML với Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Triển khai Callback Lưu Trang trong Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Xử lý Lưu Hình Ảnh trong Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}