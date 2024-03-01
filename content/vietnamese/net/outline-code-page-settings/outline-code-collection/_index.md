---
title: Bộ sưu tập MS Project về mã phác thảo trong Aspose.Tasks
linktitle: Bộ sưu tập mã phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thu thập mã phác thảo Microsoft Project bằng Aspose.Tasks cho .NET. Hướng dẫn toàn diện này cung cấp hướng dẫn từng bước.
type: docs
weight: 11
url: /vi/net/outline-code-page-settings/outline-code-collection/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách thu thập mã phác thảo Microsoft Project bằng Aspose.Tasks cho .NET. Chúng tôi sẽ chia nhỏ quy trình thành các hướng dẫn từng bước để đảm bảo sự rõ ràng và dễ hiểu.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Visual Studio: Cài đặt Visual Studio trên hệ thống của bạn.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về lập trình C#: Làm quen với C# sẽ có lợi.

## Nhập không gian tên
Đầu tiên, nhập các không gian tên cần thiết để truy cập chức năng Aspose.Tasks trong dự án C# của bạn.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Bước 1: Tải tệp dự án
 Bắt đầu bằng cách tải tệp Microsoft Project bằng cách sử dụng`Project` lớp học.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Bước 2: Thu thập mã phác thảo
Tạo một bộ sưu tập để thu thập mã phác thảo từ các nhiệm vụ của dự án.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Bước 3: Lặp lại các nhiệm vụ và mã phác thảo
Lặp lại các nhiệm vụ đã thu thập và mã phác thảo, in chi tiết của chúng.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Bước 4: Thêm định nghĩa mã phác thảo tùy chỉnh
Thêm định nghĩa mã phác thảo tùy chỉnh vào dự án.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Bước 5: Tạo và chèn mã phác thảo
Tạo mã phác thảo và chèn nó vào một nhiệm vụ.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Bước 6: Thao tác mã phác thảo
Thao tác các mã phác thảo nếu cần, chẳng hạn như chèn, xóa hoặc xóa.
```csharp
// Ví dụ về thao tác
// ...
// Chèn mã số 2 vào đúng vị trí
task.OutlineCodes.Insert(2, code2);
// Kiểm tra xem mã đã được chèn chưa
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách thu thập mã phác thảo Microsoft Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể quản lý hiệu quả các mã phác thảo trong dự án của mình, nâng cao tính tổ chức và sự rõ ràng.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với các ngôn ngữ lập trình khác không?
Đáp: Có, Aspose.Tasks for .NET chủ yếu hướng tới nền tảng .NET, nhưng nó cũng cung cấp hỗ trợ cho các ngôn ngữ lập trình khác thông qua Aspose.Tasks for Cloud.
### Câu hỏi: Có bất kỳ hạn chế nào về kích thước của tệp Dự án mà Aspose.Tasks for .NET có thể xử lý không?
Trả lời: Aspose.Tasks for .NET có thể xử lý các tệp Dự án lớn một cách hiệu quả, nhưng hiệu suất có thể khác nhau tùy thuộc vào độ phức tạp và kích thước của tệp.
### Câu hỏi: Aspose.Tasks dành cho .NET có tương thích với các phiên bản mới nhất của Microsoft Project không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, bao gồm cả phiên bản mới nhất.
### Câu hỏi: Tôi có thể tùy chỉnh định dạng đầu ra khi làm việc với Aspose.Tasks cho .NET không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks for .NET cung cấp các tùy chọn mở rộng để tùy chỉnh định dạng đầu ra theo yêu cầu của bạn.
### Câu hỏi: Tôi có thể tìm nguồn hỗ trợ hoặc tài nguyên bổ sung cho Aspose.Tasks cho .NET ở đâu?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) nếu có bất kỳ trợ giúp hoặc thắc mắc nào liên quan đến Aspose.Tasks for .NET.