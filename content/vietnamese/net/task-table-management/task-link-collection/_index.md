---
title: Xử lý các liên kết tác vụ trong Aspose.Tasks
linktitle: Xử lý các liên kết tác vụ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá sức mạnh của Aspose.Tasks cho .NET trong việc quản lý các liên kết nhiệm vụ dự án một cách hiệu quả. Hãy làm theo hướng dẫn từng bước của chúng tôi để nâng cao trải nghiệm quản lý dự án của bạn.
type: docs
weight: 19
url: /vi/net/task-table-management/task-link-collection/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước về cách xử lý các liên kết tác vụ trong Aspose.Tasks cho .NET! Liên kết nhiệm vụ đóng một vai trò quan trọng trong quản lý dự án, cho phép bạn thiết lập mối quan hệ giữa các nhiệm vụ và tạo ra sự phụ thuộc. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình làm việc với các bộ sưu tập liên kết tác vụ bằng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện Aspose.Tasks. Bạn có thể tìm thấy thư viện[đây](https://releases.aspose.com/tasks/net/).
2. Tệp dự án mẫu: Chuẩn bị tệp dự án mẫu (ví dụ: "SampleProject.mpp") để làm theo các ví dụ.
Bây giờ, hãy bắt đâù!
## Nhập không gian tên
Trong dự án .NET của bạn, hãy đảm bảo nhập các không gian tên cần thiết để làm việc với Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Bước 1: Tải dự án và nhiệm vụ truy cập
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
// Tải dự án
var project = new Project(DataDir + "SampleProject.mpp");
// Truy cập nhiệm vụ theo ID
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Bước 2: Tạo liên kết nhiệm vụ
Liên kết các nhiệm vụ với nhau để thiết lập sự phụ thuộc:
```csharp
// Liên kết các tác vụ bằng cách sử dụng phụ thuộc FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Bước 3: In liên kết tác vụ
In các liên kết nhiệm vụ cho dự án:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
// Lặp lại thông qua các liên kết nhiệm vụ
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Bước 4: Chỉnh sửa liên kết tác vụ
Chỉnh sửa liên kết tác vụ bằng cách truy cập chỉ mục:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Bước 5: Xóa liên kết tác vụ
Xóa tất cả các liên kết nhiệm vụ khỏi dự án:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách xử lý các liên kết tác vụ trong Aspose.Tasks cho .NET. Hướng dẫn toàn diện này bao gồm việc tải dự án, tạo liên kết nhiệm vụ, in liên kết, chỉnh sửa liên kết và xóa liên kết nhiệm vụ.
Vui lòng khám phá thêm các tính năng và chức năng do Aspose.Tasks cung cấp để nâng cao trải nghiệm quản lý dự án của bạn.
## Câu hỏi thường gặp
### Aspose.Tasks có tương thích với tất cả các phiên bản .NET không?
Có, Aspose.Tasks được thiết kế để hoạt động liền mạch với tất cả các phiên bản .NET.
### Tôi có thể tạo các loại liên kết nhiệm vụ tùy chỉnh bằng Aspose.Tasks không?
Hiện tại, Aspose.Tasks hỗ trợ các loại liên kết nhiệm vụ tiêu chuẩn và các loại liên kết tùy chỉnh không có sẵn.
### Làm cách nào tôi có thể áp dụng các ràng buộc cho các tác vụ trong Aspose.Tasks?
 Bạn có thể áp dụng các ràng buộc bằng cách sử dụng`ConstraintType` tài sản của`Task` lớp trong Aspose.Tasks.
### Có bất kỳ hạn chế nào về kích thước của tệp dự án mà Aspose.Tasks có thể xử lý không?
Aspose.Tasks có thể xử lý các tệp dự án lớn một cách hiệu quả với tác động hiệu suất tối thiểu.
### Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks không?
 Có, bạn có thể tìm thấy sự hỗ trợ và tương tác với cộng đồng trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).