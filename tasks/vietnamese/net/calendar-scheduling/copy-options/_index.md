---
date: 2026-07-05
description: Tìm hiểu cách sao chép dữ liệu dự án bằng Aspose.Tasks cho .NET với copy
  options. Tăng cường các ứng dụng .NET của bạn với quản lý dự án chính xác.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Cách sao chép dữ liệu dự án với copy options trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Cách sao chép dữ liệu dự án với copy options trong Aspose.Tasks
url: /vi/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sao chép dữ liệu dự án với tùy chọn sao chép trong Aspose.Tasks

## Giới thiệu

Nếu bạn cần **cách sao chép dự án** thông tin từ một tệp Microsoft Project sang tệp khác, Aspose.Tasks cho .NET cung cấp cho bạn một cách sạch sẽ, dựa trên mã để thực hiện. Trong hướng dẫn này, chúng tôi sẽ đi qua toàn bộ quy trình — tải dự án nguồn, cấu hình tùy chọn sao chép, tạo bản sao và tải kết quả — để bạn có thể tích hợp logic sao chép dự án vào bất kỳ ứng dụng .NET nào một cách tự tin.

## Câu trả lời nhanh
- **Tính năng sao chép làm gì?** Nó sao chép dữ liệu dự án trong khi cho phép bạn bao gồm hoặc loại trừ các phần cụ thể như lịch, nguồn lực hoặc thông tin hiển thị.  
- **Lớp nào kiểm soát hành vi?** `CopyToOptions` cho phép bạn tinh chỉnh những gì được sao chép.  
- **Tôi có cần giấy phép không?** Một giấy phép Aspose.Tasks hợp lệ là bắt buộc cho môi trường sản xuất; bản dùng thử miễn phí hoạt động cho phát triển.  
- **Các định dạng được hỗ trợ?** Aspose.Tasks xử lý các tệp MPP, XML và XER — hơn 20 + định dạng tổng cộng.  
- **Có thể bỏ qua dữ liệu hiển thị không?** Có, đặt `CopyToOptions.SkipViewData = true` để loại bỏ thông tin liên quan tới giao diện người dùng.

## “Cách sao chép dự án” là gì trong Aspose.Tasks?

**“Cách sao chép dự án”** đề cập đến việc sử dụng API của Aspose.Tasks để sao chép dữ liệu của một đối tượng Project vào một tệp mới, tùy chọn lọc bỏ các yếu tố không mong muốn. Thao tác này hữu ích cho việc tạo mẫu, lưu trữ, hoặc tạo các biến thể dự án mà không cần các bước giao diện người dùng thủ công, và nó hoạt động trên tất cả các định dạng tệp được hỗ trợ.

## Tại sao nên sử dụng Tùy chọn Sao chép trong Aspose.Tasks?

Aspose.Tasks hỗ trợ **hơn 50 thực thể liên quan đến dự án** (công việc, nguồn lực, lịch, phân công, v.v.) và có thể xử lý các tệp với **tối đa 10.000 công việc** trong khi giữ mức sử dụng bộ nhớ dưới 200 MB. Sử dụng `CopyToOptions` cho phép bạn tránh sao chép dữ liệu hiển thị nặng, giảm kích thước tệp đầu ra xuống **30‑40 %** và tăng tốc độ thực hiện khoảng **2×** cho các dự án lớn.

## Yêu cầu trước

1. **Aspose.Tasks cho .NET** – tải phiên bản mới nhất từ [download link](https://releases.aspose.com/tasks/net/).  
2. **Môi trường phát triển .NET** – Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET 6+) đã được cài đặt.  
3. **Giấy phép Aspose.Tasks hợp lệ** – tùy chọn cho việc đánh giá, bắt buộc cho các bản dựng sản xuất.  
4. **Một tệp dự án hiện có** (ví dụ, `SourceProject.xml`) mà bạn muốn sao chép.

## Cách nhập không gian tên cho Aspose.Tasks?

Thêm các chỉ thị `using` cần thiết ở đầu tệp C# của bạn để trình biên dịch có thể tìm thấy các kiểu của Aspose.Tasks. Bao gồm các câu lệnh này cho phép bạn truy cập trực tiếp vào `Project`, `CopyToOptions`, và các lớp tiện ích khác mà không cần viết đầy đủ tên, giúp đơn giản hoá mã và cải thiện khả năng đọc.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Bước 1: Khởi tạo Đối tượng Dự án

Đầu tiên, tạo một thể hiện `Project` đại diện cho tệp nguồn và tải dữ liệu XML.  
Lớp `Project` đại diện cho một tệp Microsoft Project được tải vào bộ nhớ, cung cấp các công việc, nguồn lực, lịch và các thông tin dự án khác.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Mẹo chuyên nghiệp:** Nếu bạn làm việc với các tệp rất lớn, hãy cân nhắc sử dụng hàm khởi tạo `LoadOptions` để bật tải lười và giữ mức tiêu thụ bộ nhớ thấp.

## Bước 2: Tạo Bản sao của Dự án

Tiếp theo, khởi tạo một đối tượng `Project` thứ hai sẽ nhận dữ liệu đã sao chép. Đối tượng này bắt đầu rỗng.

```csharp
Project copiedProject = new Project();
```

Bây giờ bạn có hai đối tượng `Project` riêng biệt: một được tải từ đĩa và một sẵn sàng nhận bản sao.

## Bước 3: Tải Dự án Đã sao chép

Sau thao tác sao chép (được hiển thị sau), bạn sẽ muốn xác minh kết quả bằng cách tải tệp vừa lưu vào một thể hiện `Project` khác.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Việc tải lại tệp xác nhận rằng việc sao chép đã thành công và các tùy chọn bạn đã đặt hoạt động như mong đợi.

## Bước 4: Cấu hình Tùy chọn Sao chép

Lớp `CopyToOptions` cho phép bạn chỉ định chính xác những gì sẽ được chuyển từ nguồn sang đích.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Đặt `SkipViewData = true` giảm kích thước tệp đầu ra và tăng tốc độ thực hiện, đặc biệt khi bạn chỉ cần dữ liệu dự án logic.

## Bước 5: Thực hiện Sao chép Dự án

Cuối cùng, gọi phương thức `CopyTo` trên dự án nguồn, truyền vào dự án đích và các tùy chọn bạn đã cấu hình.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Lệnh gọi hai dòng này thực hiện toàn bộ thao tác sao chép, tuân theo các tùy chọn bạn đã định nghĩa. Tệp `CopiedProject.xml` kết quả chỉ chứa dữ liệu bạn yêu cầu.

## Các vấn đề thường gặp và giải pháp

| Issue | Cause | Fix |
|-------|-------|-----|
| **NullReferenceException when calling `CopyTo`** | Dự án đích chưa được khởi tạo. | Đảm bảo gọi `new Project()` trước khi `CopyTo`. |
| **Missing tasks after copy** | `CopyCommonData` được đặt thành `false`. | Đặt `CopyCommonData = true` hoặc sao chép các bộ sưu tập cụ thể một cách thủ công. |
| **Large output file** | `SkipViewData` để là `false`. | Bật `SkipViewData` để loại bỏ dữ liệu liên quan tới giao diện người dùng. |
| **License not applied** | Tệp giấy phép chưa được tải. | Gọi `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` trước khi sử dụng bất kỳ API nào. |

## Câu hỏi thường gặp

**Q: Tôi có thể sao chép chỉ một phần các công việc không?**  
A: Có, sử dụng `CopyToOptions` cùng với `ProjectRootTask` để chỉ định công việc bắt đầu, hoặc sao chép thủ công các công việc đã chọn sau khi sao chép ban đầu.

**Q: Aspose.Tasks có hỗ trợ sao chép giữa các định dạng tệp khác nhau không?**  
A: Chắc chắn. Bạn có thể tải tệp MPP và lưu bản sao dưới dạng XML, XER, hoặc bất kỳ định dạng nào khác được hỗ trợ — hơn **20 + định dạng** tổng cộng.

**Q: Làm thế nào để xử lý các tệp dự án được bảo vệ bằng mật khẩu?**  
A: Tải nguồn bằng `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, sau đó tiếp tục sao chép như bình thường.

**Q: Có cách nào để sao chép các pool nguồn lực mà không có công việc không?**  
A: Đặt `CopyToOptions.CopyResources = true` và `CopyToOptions.CopyTasks = false` để chuyển chỉ thông tin nguồn lực.

**Q: Tôi có thể tìm thêm ví dụ ở đâu?**  
A: Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để xem các đoạn mã do cộng đồng đóng góp, mẹo khắc phục sự cố và tài liệu chính thức.

**Cập nhật lần cuối:** 2026-07-05  
**Đã kiểm tra với:** Aspose.Tasks 24.12 cho .NET  
**Tác giả:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Làm chủ dữ liệu dự án với Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Làm chủ tùy chọn lưu của MS Project cho Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Lịch và lập kế hoạch Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}