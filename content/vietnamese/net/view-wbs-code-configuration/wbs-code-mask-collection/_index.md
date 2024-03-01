---
title: Làm chủ mặt nạ mã WBS với Aspose.Tasks cho .NET
linktitle: Bộ sưu tập mặt nạ mã WBS trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tăng cường quản lý dự án với Aspose.Tasks cho .NET. Tìm hiểu cách tạo, quản lý và chuyển Mặt nạ mã WBS một cách dễ dàng trong hướng dẫn toàn diện này.
type: docs
weight: 15
url: /vi/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Giới thiệu
Trong thế giới năng động của quản lý dự án, việc tổ chức các nhiệm vụ một cách hiệu quả là rất quan trọng. Aspose.Tasks for .NET cung cấp một giải pháp mạnh mẽ để quản lý mã cấu trúc phân tích công việc dự án (WBS) một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ đi sâu vào Bộ sưu tập Mặt nạ mã WBS, khám phá cách triển khai và thao tác chúng bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta bắt tay vào hành trình viết mã này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#.
-  Aspose.Tasks cho .NET được cài đặt trong môi trường phát triển của bạn. Nếu không thì tải về[đây](https://releases.aspose.com/tasks/net/).
- Trình chỉnh sửa mã như Visual Studio để mang lại trải nghiệm mã hóa liền mạch.
## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Khởi tạo dự án và định nghĩa mã WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Xác định mặt nạ mã WBS
Xóa mọi mặt nạ mã hiện có và thêm mặt nạ mới:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Hiển thị thông tin mặt nạ mã
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Thêm nhiệm vụ vào dự án
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Truy xuất thông tin nhiệm vụ
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Thao tác với mặt nạ mã
Xóa mặt nạ mã và đảm bảo nó được xóa:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Sao chép mặt nạ mã sang dự án khác
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Hiển thị mặt nạ mã trong dự án khác
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Thêm nhiệm vụ vào dự án khác
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Hiển thị mã WBS trong dự án khác
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Phần kết luận
Với Aspose.Tasks cho .NET, việc quản lý mã WBS trở thành một nhiệm vụ dễ dàng. Hướng dẫn này đề cập đến việc tạo, thao tác và chuyển Mặt nạ mã WBS, cung cấp cho bạn hướng dẫn toàn diện để nâng cao trải nghiệm quản lý dự án của bạn.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với các ngôn ngữ lập trình khác không?
Trả lời: Aspose.Tasks chủ yếu hỗ trợ các ngôn ngữ .NET, nhưng bạn có thể khám phá các tùy chọn khả năng tương tác với các ngôn ngữ khác.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?
 A: Có, bạn có thể tải xuống phiên bản dùng thử[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào để tìm kiếm trợ giúp hoặc báo cáo sự cố với Aspose.Tasks cho .NET?
 Đáp: Hãy ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và thảo luận.
### Hỏi: Mục đích của mã WBS trong quản lý dự án là gì?
Đáp: Mã WBS giúp tổ chức và cấu trúc các nhiệm vụ dự án theo thứ bậc, cung cấp cách tiếp cận có hệ thống để lập kế hoạch dự án.
### Câu hỏi: Tôi có thể tùy chỉnh định dạng của mã WBS trong Aspose.Tasks cho .NET không?
Trả lời: Hoàn toàn có thể, bạn có toàn quyền kiểm soát định dạng và cấu trúc của mã WBS bằng cách sử dụng Aspose.Tasks for .NET.