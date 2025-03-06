---
title: Nhóm nhiệm vụ dự án MS hiệu quả với Aspose.Tasks
linktitle: Nhóm các nhiệm vụ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách nhóm các tác vụ Microsoft Project một cách hiệu quả bằng cách sử dụng Aspose.Tasks cho .NET.
type: docs
weight: 25
url: /vi/net/tasks-project-management/grouping-tasks/
---
## Giới thiệu
Việc quản lý các nhiệm vụ trong Microsoft Project đôi khi có thể gặp khó khăn, đặc biệt là khi sắp xếp chúng một cách hiệu quả. Aspose.Tasks for .NET cung cấp một giải pháp toàn diện cho vấn đề này bằng cách cung cấp các chức năng để nhóm các tác vụ một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ khám phá cách nhóm các tác vụ MS Project bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET.
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết vào dự án C# của mình để sử dụng các chức năng của Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Bước 1: Tải tệp dự án MS
Bắt đầu bằng cách tải tệp MS Project của bạn bằng mã sau:
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Bước 2: Truy cập nhóm tác vụ
Tiếp theo, hãy truy cập các nhóm nhiệm vụ trong dự án:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## Bước 3: Truy xuất thông tin nhóm
Bây giờ, lấy thông tin về nhóm nhiệm vụ:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## Bước 4: Tiêu chí nhóm truy cập
Truy cập các tiêu chí được đặt cho nhóm nhiệm vụ:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## Bước 5: Truy xuất thông tin tiêu chí
Truy xuất thông tin chi tiết về từng tiêu chí:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
Bằng cách làm theo các bước này, bạn có thể nhóm các tác vụ MS Project một cách hiệu quả bằng cách sử dụng Aspose.Tasks cho .NET, nâng cao khả năng tổ chức và quản lý dữ liệu dự án của bạn.

## Phần kết luận
Tóm lại, Aspose.Tasks for .NET cung cấp các khả năng mạnh mẽ để nhóm các nhiệm vụ MS Project, cho phép tổ chức và quản lý dữ liệu dự án tốt hơn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể sử dụng hiệu quả các tính năng này trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Tôi có thể nhóm các nhiệm vụ dựa trên tiêu chí tùy chỉnh không?
Có, bạn có thể xác định tiêu chí tùy chỉnh để nhóm các tác vụ theo yêu cầu cụ thể của mình bằng cách sử dụng Aspose.Tasks for .NET.
### Aspose.Tasks có hỗ trợ các phiên bản khác nhau của tệp MS Project không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp MS Project, đảm bảo khả năng tương thích và tích hợp liền mạch.
### Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?
 Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/).
### Tôi có thể tùy chỉnh giao diện của các nhiệm vụ được nhóm không?
Hoàn toàn có thể, Aspose.Tasks cung cấp các tùy chọn để tùy chỉnh giao diện của các tác vụ được nhóm, bao gồm màu ô, phông chữ và kiểu.
### Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho .NET ở đâu?
 Bạn có thể tìm thấy sự hỗ trợ và trợ giúp cho Aspose.Tasks for .NET trong[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).