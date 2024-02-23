---
title: Bộ sưu tập các định nghĩa mã phác thảo trong Aspose.Tasks .NET
linktitle: Bộ sưu tập các định nghĩa mã phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thao tác các định nghĩa mã phác thảo trong tài liệu Microsoft Project bằng Aspose.Tasks cho .NET. Phân loại dữ liệu dự án của bạn một cách dễ dàng.
type: docs
weight: 13
url: /vi/net/outline-code-page-settings/outline-code-definition-collection/
---
## Giới thiệu
Aspose.Tasks là một thư viện .NET mạnh mẽ được thiết kế để thao tác các tài liệu Microsoft Project một cách dễ dàng và hiệu quả. Một trong những tính năng chính của nó là khả năng làm việc với các định nghĩa mã phác thảo, cho phép người dùng sắp xếp và phân loại dữ liệu dự án một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các định nghĩa mã phác thảo bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
1. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.
2. Visual Studio: Cài đặt Visual Studio hoặc bất kỳ môi trường phát triển C# ưa thích nào khác.
3.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).

## Nhập không gian tên
Để bắt đầu, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Bước 1: Tải tài liệu Microsoft Project
Trước tiên, hãy tải tài liệu Microsoft Project để bắt đầu làm việc với các định nghĩa mã phác thảo:
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Bước 2: Truy cập định nghĩa mã phác thảo
Bây giờ, hãy truy cập các định nghĩa mã phác thảo trong dự án:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Bước 3: Thêm định nghĩa mã phác thảo tùy chỉnh
Bạn có thể thêm định nghĩa mã phác thảo tùy chỉnh như sau:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Bước 4: Sửa đổi định nghĩa mã phác thảo
Dễ dàng sửa đổi các định nghĩa mã phác thảo hiện có:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Bước 5: Xóa định nghĩa mã phác thảo
Xóa định nghĩa mã phác thảo khi không còn cần thiết:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Bước 6: Lưu thay đổi
Cuối cùng, lưu các thay đổi của bạn vào tài liệu dự án:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Phần kết luận
Tóm lại, Aspose.Tasks cho .NET cung cấp chức năng toàn diện để quản lý các định nghĩa mã phác thảo trong tài liệu Microsoft Project. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể thao tác hiệu quả các định nghĩa mã phác thảo để sắp xếp và phân loại dữ liệu dự án của mình một cách hiệu quả.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể thêm nhiều định nghĩa mã phác thảo vào một dự án không?
 Đáp: Có, bạn có thể thêm nhiều định nghĩa mã phác thảo vào một dự án dựa trên yêu cầu của mình. Đơn giản chỉ cần sử dụng`Add` phương pháp cho mỗi định nghĩa bạn muốn đưa vào.
### Câu hỏi: Có thể xóa tất cả định nghĩa mã phác thảo khỏi dự án cùng một lúc không?
 Đáp: Có, bạn có thể xóa tất cả các định nghĩa mã phác thảo khỏi một dự án bằng cách sử dụng`Clear` phương pháp.
### Câu hỏi: Điều gì xảy ra nếu tôi cố gắng sửa đổi định nghĩa mã phác thảo chỉ đọc?
Trả lời: Nếu định nghĩa mã phác thảo ở chế độ chỉ đọc, bạn sẽ không thể sửa đổi nó trực tiếp. Bạn sẽ cần kiểm tra trạng thái chỉ đọc của nó trước khi thử bất kỳ sửa đổi nào.
### Câu hỏi: Có bất kỳ hạn chế nào về số lượng định nghĩa mã phác thảo mà tôi có thể thêm vào một dự án không?
Trả lời: Aspose.Tasks cho .NET không áp đặt bất kỳ giới hạn cụ thể nào về số lượng định nghĩa mã phác thảo mà bạn có thể thêm vào dự án. Tuy nhiên, hãy xem xét những tác động về hiệu suất khi làm việc với một số lượng lớn các định nghĩa.
### Câu hỏi: Tôi có thể sử dụng định nghĩa mã phác thảo để nhóm các nhiệm vụ dựa trên tiêu chí tùy chỉnh không?
Đáp: Có, định nghĩa mã phác thảo cho phép bạn phân loại các nhiệm vụ dựa trên tiêu chí tùy chỉnh, mang lại sự linh hoạt trong việc tổ chức dữ liệu dự án.## Mã nguồn hoàn chỉnh