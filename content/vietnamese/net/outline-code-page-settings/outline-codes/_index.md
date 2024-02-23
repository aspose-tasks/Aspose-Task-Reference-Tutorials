---
title: Quản lý mã phác thảo dự án trong Aspose.Tasks cho .NET
linktitle: Quản lý mã phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý mã phác thảo MS Project bằng Aspose.Tasks cho .NET. Đơn giản hóa việc tổ chức dự án một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/outline-code-page-settings/outline-codes/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý mã phác thảo Microsoft Project bằng Aspose.Tasks cho .NET. Mã phác thảo là các trường tùy chỉnh trong Microsoft Project cho phép người dùng phân loại và sắp xếp các nhiệm vụ theo tiêu chí cụ thể. Aspose.Tasks đơn giản hóa quá trình đọc và thao tác các mã phác thảo này theo chương trình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[trang mạng](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển phù hợp cho lập trình .NET, chẳng hạn như Visual Studio.
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có ích cho việc hiểu các ví dụ về mã.

## Nhập không gian tên
Để bắt đầu, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Điều này cho phép bạn truy cập các lớp và phương thức được cung cấp bởi thư viện Aspose.Tasks.
1. Mở Visual Studio: Khởi chạy Visual Studio IDE của bạn.
2. Tạo một dự án mới: Bắt đầu một dự án C# mới hoặc mở một dự án hiện có mà bạn định sử dụng Aspose.Tasks.
3. Thêm tài liệu tham khảo Aspose.Tasks: Nhấp chuột phải vào dự án của bạn trong Solution Explorer, chọn "Quản lý gói NuGet", tìm kiếm "Aspose.Tasks" và cài đặt phiên bản mới nhất.
4. Nhập không gian tên Aspose.Tasks: Ở đầu tệp C# của bạn, thêm lệnh sử dụng sau:
```csharp
using Aspose.Tasks;
using System;

```
## Bước 1: Xác định thư mục tài liệu
Đầu tiên, đặt đường dẫn đến thư mục chứa tệp MS Project của bạn.
```csharp
String DataDir = "Your Document Directory";
```
 thay thế`"Your Document Directory"` với đường dẫn thực tế đến tệp dự án của bạn.
## Bước 2: Tải tệp dự án
 Khởi tạo một cái mới`Project` đối tượng bằng cách tải tệp MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Điều này khởi tạo đối tượng dự án với tệp được chỉ định.
## Bước 3: Đọc mã phác thảo
Lặp lại tất cả các nhiệm vụ trong dự án và lấy mã phác thảo của chúng.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Đoạn mã này lặp qua từng tác vụ, kiểm tra xem nó có mã phác thảo hay không và in ra các chi tiết như Id trường, Hướng dẫn giá trị và Id giá trị cho từng mã phác thảo được liên kết với tác vụ.

## Phần kết luận
Tóm lại, Aspose.Tasks for .NET cung cấp các khả năng mạnh mẽ để quản lý mã phác thảo Microsoft Project theo chương trình. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể đọc và thao tác các mã phác thảo trong tệp MS Project một cách hiệu quả bằng C#.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sửa đổi mã phác thảo bằng Aspose.Tasks không?
Trả lời: Có, bạn có thể sửa đổi mã phác thảo theo chương trình bằng cách sử dụng Aspose.Tasks cho .NET. Chỉ cần truy cập mã phác thảo của nhiệm vụ và cập nhật giá trị của chúng nếu cần.
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?
Trả lời: Aspose.Tasks hỗ trợ nhiều phiên bản Microsoft Project, bao gồm 2003, 2007, 2010, 2013, 2016 và 2019.
### Câu hỏi: Aspose.Tasks có yêu cầu giấy phép sử dụng thương mại không?
Trả lời: Có, cần có giấy phép hợp lệ để sử dụng Aspose.Tasks vì mục đích thương mại. Bạn có thể lấy giấy phép từ trang web Aspose.
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?
Trả lời: Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks từ trang web để đánh giá các tính năng và khả năng của nó.
### Câu hỏi: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?
 Trả lời: Bạn có thể nhận hỗ trợ cho Aspose.Tasks bằng cách truy cập diễn đàn tại[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Mã nguồn hoàn chỉnh