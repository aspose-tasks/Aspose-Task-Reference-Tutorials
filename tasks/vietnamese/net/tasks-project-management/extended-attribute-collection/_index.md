---
title: Quản lý bộ sưu tập thuộc tính dự án MS trong Aspose.Tasks
linktitle: Quản lý bộ sưu tập thuộc tính mở rộng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý hiệu quả các thuộc tính mở rộng của MS Project bằng Aspose.Tasks cho .NET. Thao tác liền mạch các thuộc tính nhiệm vụ với hướng dẫn từng bước.
type: docs
weight: 12
url: /vi/net/tasks-project-management/extended-attribute-collection/
---
## Giới thiệu
Bạn đang tìm cách quản lý hiệu quả các thuộc tính mở rộng của MS Project bằng Aspose.Tasks cho .NET? Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình. Hãy đi sâu vào!
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Visual Studio: Cài đặt Visual Studio trên hệ thống của bạn.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Kiến thức cơ bản về C#: Làm quen với những kiến thức cơ bản về ngôn ngữ lập trình C#.

## Nhập không gian tên
Bắt đầu bằng cách nhập các không gian tên cần thiết vào dự án của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Bước 1: Tải tệp dự án
Trước tiên, hãy tải tệp MS Project bằng đoạn mã sau:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Bước 2: Truy cập tác vụ và thuộc tính mở rộng
Truy cập một tác vụ cụ thể và các thuộc tính mở rộng của nó:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Bước 3: Xóa thuộc tính mở rộng
Xóa các thuộc tính mở rộng hiện có nếu cần:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Bước 4: Tạo định nghĩa thuộc tính mở rộng
Tạo định nghĩa cho các thuộc tính mở rộng mới:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Bước 5: Lặp lại các thuộc tính mở rộng của nhiệm vụ
Lặp lại các thuộc tính mở rộng của nhiệm vụ:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Bước 6: Thêm thuộc tính mở rộng
Thêm các thuộc tính mở rộng mới vào nhiệm vụ:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Bước 7: Làm việc với các thuộc tính mở rộng
Thực hiện các thao tác trên các thuộc tính mở rộng theo yêu cầu.
## Bước 8: Xóa thuộc tính mở rộng
Xóa các thuộc tính mở rộng theo chỉ mục hoặc theo điều kiện:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Bước 9: Sao chép thuộc tính sang tác vụ khác
Sao chép các thuộc tính sang một tác vụ khác trong cùng một dự án hoặc dự án khác:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Phần kết luận
Việc quản lý các bộ sưu tập thuộc tính mở rộng của MS Project trở nên liền mạch với Aspose.Tasks for .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể xử lý các thuộc tính mở rộng một cách hiệu quả, nâng cao khả năng quản lý dự án của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể thao tác các thuộc tính mở rộng trên nhiều dự án không?
Trả lời: Có, bạn có thể sao chép các thuộc tính mở rộng giữa các tác vụ trong các dự án khác nhau bằng Aspose.Tasks cho .NET.
### Câu hỏi: Có giới hạn nào về số lượng thuộc tính mở rộng cho mỗi nhiệm vụ không?
Trả lời: Aspose.Tasks dành cho .NET không áp đặt giới hạn cố hữu nào về số lượng thuộc tính mở rộng cho mỗi tác vụ.
### Câu hỏi: Tôi có thể tạo các trường thuộc tính mở rộng tùy chỉnh không?
Đ: Chắc chắn rồi! Aspose.Tasks for .NET cho phép bạn xác định các trường thuộc tính mở rộng tùy chỉnh phù hợp với yêu cầu dự án của bạn.
### Câu hỏi: Aspose.Tasks for .NET có hỗ trợ đọc và ghi vào các tệp MS Project thuộc nhiều phiên bản khác nhau không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ các định dạng tệp MS Project trên các phiên bản khác nhau.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?
 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).