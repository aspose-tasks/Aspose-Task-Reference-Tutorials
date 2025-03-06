---
title: Quản lý bộ sưu tập dự án trong Aspose.Tasks
linktitle: Quản lý bộ sưu tập nhóm trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý bộ sưu tập MS Project một cách hiệu quả bằng Aspose.Tasks cho .NET. Thực hiện theo hướng dẫn từng bước của chúng tôi.
weight: 26
url: /vi/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý bộ sưu tập dự án trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý các bộ sưu tập MS Project nhóm bằng Aspose.Tasks cho .NET. Quản lý bộ sưu tập nhóm là rất quan trọng để tổ chức và thao tác các nhiệm vụ và tài nguyên một cách hiệu quả trong dự án của bạn.
## Điều kiện tiên quyết
Trước khi tiếp tục với hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[Liên kết tải xuống](https://releases.aspose.com/tasks/net/).
2. Kiến thức cơ bản về C#: Làm quen với những điều cơ bản về ngôn ngữ lập trình C# vì hướng dẫn này liên quan đến việc viết mã bằng C#.
3. Môi trường phát triển: Thiết lập môi trường phát triển như Visual Studio hoặc bất kỳ IDE nào khác hỗ trợ phát triển .NET.

## Nhập không gian tên
Trước tiên, hãy nhập các không gian tên cần thiết để làm việc với các chức năng Aspose.Tasks trong mã C# của chúng tôi.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Bước 1: Tải dự án
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Bước này liên quan đến việc tải tệp MS Project vào đối tượng dự án Aspose.Tasks, cho phép chúng tôi thực hiện các thao tác trên đó.
## Bước 2: Lặp lại các nhóm nhiệm vụ
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Ở đây, chúng tôi lặp lại các nhóm nhiệm vụ trong dự án, in các chi tiết như chỉ mục, tên và khả năng hiển thị trong menu cho từng nhóm.
## Bước 3: Lặp lại các nhóm tài nguyên
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Tương tự, bước này lặp lại các nhóm tài nguyên, hiển thị chỉ mục, tên và khả năng hiển thị của chúng trong menu.
## Bước 4: Xóa và sao chép nhóm sang dự án khác
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Xóa các nhóm dự án khác
otherProject.TaskGroups.Clear();
// Sao chép nhóm sang dự án khác
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Ở đây, chúng ta xóa các nhóm của dự án khác và sau đó sao chép các nhóm từ dự án ban đầu sang dự án đó.
## Bước 5: Thêm nhóm tác vụ tùy chỉnh
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
Trong bước này, chúng tôi tạo một nhóm nhiệm vụ tùy chỉnh và thêm nó vào dự án khác nếu nó chưa có.
## Bước 6: Xóa tất cả các nhóm
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Cuối cùng, chúng tôi xóa tất cả các nhóm khỏi dự án khác.

## Phần kết luận
Quản lý các bộ sưu tập MS Project của nhóm trong Aspose.Tasks for .NET là điều cần thiết để tổ chức và thao tác dữ liệu dự án một cách hiệu quả. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể xử lý hiệu quả các nhóm nhiệm vụ và nguồn lực trong dự án của mình, cải thiện việc quản lý dự án tổng thể.
## Câu hỏi thường gặp
### Aspose.Tasks for .NET có tương thích với tất cả các phiên bản MS Project không?
Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, bao gồm 2003, 2007, 2010, 2013, 2016 và 2019.
### Tôi có thể tùy chỉnh thuộc tính nhóm bằng Aspose.Tasks cho .NET không?
Có, bạn có thể tùy chỉnh các thuộc tính nhóm như tên và mức độ hiển thị bằng Aspose.Tasks for .NET.
### Aspose.Tasks cho .NET có cung cấp khả năng tương thích đa nền tảng không?
Aspose.Tasks for .NET chủ yếu nhắm vào .NET framework, nhưng nó có thể được sử dụng trong các tình huống đa nền tảng với .NET Core và .NET Standard.
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?
 Bạn có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET thông qua[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.Tasks cho .NET từ[trang mạng](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
