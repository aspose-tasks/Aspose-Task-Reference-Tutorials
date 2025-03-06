---
title: Trích xuất thông tin đầu trang và chân trang bằng Aspose.Tasks
linktitle: Thông tin đầu trang và chân trang trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách trích xuất thông tin đầu trang & chân trang từ các tệp MS Project bằng Aspose.Tasks cho .NET. Giải pháp dễ dàng, hiệu quả và thân thiện với nhà phát triển.
weight: 29
url: /vi/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất thông tin đầu trang và chân trang bằng Aspose.Tasks

## Giới thiệu
Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách truy xuất thông tin đầu trang và chân trang từ các tệp MS Project bằng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Visual Studio: Cài đặt Visual Studio trên hệ thống của bạn.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C#.

## Nhập không gian tên
Trước tiên, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Điều này sẽ cho phép bạn truy cập các lớp và phương thức do thư viện Aspose.Tasks cung cấp.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Bước 1: Khởi tạo đối tượng dự án
 Để bắt đầu, bạn cần khởi tạo một`Project` đối tượng bằng cách tải tệp MS Project hiện có.
```csharp
// Đường dẫn đến thư mục tài liệu.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Bước 2: Truy xuất thông tin Header và Footer
 Khi bạn đã tải tệp dự án, bạn có thể truy xuất thông tin đầu trang và chân trang bằng cách sử dụng`PageInfo` tài sản.
```csharp
var info = project.DefaultView.PageInfo;
// Thông tin tiêu đề
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Thông tin chân trang
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Bằng cách làm theo các bước đơn giản này, bạn có thể dễ dàng truy xuất thông tin đầu trang và chân trang từ các tệp MS Project bằng Aspose.Tasks for .NET.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách trích xuất thông tin đầu trang và chân trang từ các tệp MS Project bằng Aspose.Tasks cho .NET. Thư viện mạnh mẽ này đơn giản hóa tác vụ làm việc với các tệp Project trong ứng dụng C#, cung cấp cho các nhà phát triển các công cụ mạnh mẽ để thao tác.
### Câu hỏi thường gặp
### Tôi có thể sửa đổi thông tin đầu trang và chân trang bằng Aspose.Tasks không?
Có, bạn có thể sửa đổi thông tin đầu trang và chân trang theo chương trình bằng cách sử dụng Aspose.Tasks for .NET.
### Aspose.Tasks có hỗ trợ các định dạng tệp dự án khác ngoài MS Project không?
Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án khác nhau, bao gồm MPP, XML và MPX.
### Có bản dùng thử miễn phí cho Aspose.Tasks không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Tasks ở đâu?
 Bạn có thể tìm tài liệu về Aspose.Tasks[đây](https://reference.aspose.com/tasks/net/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?
 Bạn có thể nhận hỗ trợ cho Aspose.Tasks bằng cách truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
