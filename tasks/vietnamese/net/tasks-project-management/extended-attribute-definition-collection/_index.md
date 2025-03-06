---
title: Định nghĩa thuộc tính mở rộng chính của MS Project trong Aspose.Tasks
linktitle: Bộ sưu tập các định nghĩa thuộc tính mở rộng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý các định nghĩa thuộc tính mở rộng trong Microsoft Project bằng Aspose.Tasks for .NET. Tùy chỉnh và nâng cao dữ liệu dự án của bạn một cách dễ dàng.
weight: 14
url: /vi/net/tasks-project-management/extended-attribute-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Định nghĩa thuộc tính mở rộng chính của MS Project trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các định nghĩa thuộc tính mở rộng trong Microsoft Project bằng Aspose.Tasks for .NET. Các thuộc tính mở rộng cung cấp một cách linh hoạt để tùy chỉnh và nâng cao dữ liệu dự án, cho phép người dùng thêm các trường bổ sung ngoài các trường tiêu chuẩn được cung cấp theo mặc định. Với Aspose.Tasks, bạn có thể dễ dàng quản lý các thuộc tính mở rộng này để điều chỉnh nhu cầu quản lý dự án của mình.
## Điều kiện tiên quyết
Trước khi tiếp tục, hãy đảm bảo bạn đã cài đặt các điều kiện tiên quyết sau:
- [.Nền tảng NET](https://dotnet.microsoft.com/download)
-  Aspose.Tasks cho thư viện .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết để truy cập các lớp và phương thức Aspose.Tasks trong dự án .NET của bạn. Thực hiện theo các bước sau:
## Bước 1: Mở dự án .NET của bạn
Mở dự án .NET của bạn trong IDE ưa thích của bạn, chẳng hạn như Visual Studio.
## Bước 2: Thêm không gian tên Aspose.Tasks
Thêm dòng sau vào đầu tệp mã của bạn để nhập vùng tên Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Bây giờ, hãy chia các ví dụ mã được cung cấp thành nhiều bước để hiểu toàn diện:
## Bước 1: Tải file dự án
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Bước 2: Xóa định nghĩa thuộc tính mở rộng hiện có (tùy chọn)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Bước 3: Tạo và thêm định nghĩa thuộc tính mở rộng cho một tác vụ
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Bước 4: Lặp lại các thuộc tính mở rộng của nhiệm vụ
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Bước 5: Tạo và thêm định nghĩa thuộc tính mở rộng cho tài nguyên
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Bước 6: Chèn định nghĩa thuộc tính mở rộng tài nguyên
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Bước 7: Xóa thuộc tính mở rộng theo chỉ mục
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày những kiến thức cơ bản về cách làm việc với các định nghĩa thuộc tính mở rộng trong Microsoft Project bằng cách sử dụng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể quản lý và tùy chỉnh các thuộc tính mở rộng một cách hiệu quả để phù hợp với yêu cầu quản lý dự án của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sửa đổi các định nghĩa thuộc tính mở rộng hiện có không?
Đáp: Có, bạn có thể sửa đổi các định nghĩa thuộc tính mở rộng hiện có hoặc tạo các định nghĩa thuộc tính mới theo nhu cầu của mình.
### Câu hỏi: Các thuộc tính mở rộng có được hỗ trợ trong tất cả các phiên bản của Microsoft Project không?
Trả lời: Có, các thuộc tính mở rộng được hỗ trợ trong hầu hết các phiên bản Microsoft Project, bao gồm cả các phiên bản gần đây.
### Câu hỏi: Tôi có thể sử dụng các thuộc tính mở rộng để tính toán các trường tùy chỉnh không?
Đáp: Hoàn toàn có thể, các thuộc tính mở rộng có thể được sử dụng để tính toán các trường tùy chỉnh dựa trên tiêu chí cụ thể mà bạn xác định.
### Câu hỏi: Aspose.Tasks có tương thích với các khung .NET khác không?
Trả lời: Aspose.Tasks tương thích với nhiều khung .NET khác nhau, đảm bảo tính linh hoạt và dễ tích hợp.
### Câu hỏi: Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Tasks ở đâu?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và khám phá tài liệu[đây](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
