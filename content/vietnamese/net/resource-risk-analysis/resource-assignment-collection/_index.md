---
title: Bộ sưu tập các bài tập tài nguyên trong Aspose.Tasks
linktitle: Bộ sưu tập các bài tập tài nguyên trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý việc gán tài nguyên trong Microsoft Project bằng Aspose.Tasks for .NET. Hướng dẫn từng bước với các ví dụ về mã.
type: docs
weight: 12
url: /vi/net/resource-risk-analysis/resource-assignment-collection/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện này về cách quản lý phân công tài nguyên trong Microsoft Project bằng Aspose.Tasks for .NET. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quy trình từng bước một, đảm bảo bạn hiểu rõ về cách thao tác các nhiệm vụ tài nguyên một cách hiệu quả. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn mọi thứ bạn cần biết.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn đã thiết lập như sau:
1.  Aspose.Tasks for .NET Installed: Đảm bảo bạn đã cài đặt Aspose.Tasks for .NET trong môi trường phát triển của mình. Nếu không, bạn có thể tải nó từ[đây](https://releases.aspose.com/tasks/net/).
2. Kiến thức cơ bản về C#: Hướng dẫn này giả sử bạn có hiểu biết cơ bản về ngôn ngữ lập trình C#.
3. Tệp dự án Microsoft: Chuẩn bị sẵn tệp Microsoft Project cho mục đích thử nghiệm. Nếu chưa có, bạn có thể tạo một tệp mẫu.

## Nhập không gian tên
Đầu tiên, hãy nhập các không gian tên cần thiết:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Bước 1: Tải tệp dự án
Bắt đầu bằng cách tải tệp Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Bước 2: Thêm nhiệm vụ và tài nguyên
Bây giờ, hãy thêm một nhiệm vụ và tài nguyên vào dự án:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Bước 3: Gán tài nguyên cho tác vụ
Tiếp theo, chúng ta sẽ gán tài nguyên cho tác vụ:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Bước 4: Làm việc với các loại bài tập khác nhau
Bạn cũng có thể làm việc với các bài tập liên quan đến đơn vị hoặc chi phí:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Đặt thuộc tính cho các phép gán đơn vị và chi phí tương tự như ở Bước 3
```
## Bước 5: In bài tập
In các bài tập cho dự án:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // In chi tiết nhiệm vụ
}
```
## Bước 6: Truy xuất bài tập bằng UID
Bạn có thể truy xuất bài tập bằng UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Bước 7: Kiểm tra trạng thái chỉ đọc
Xác minh xem bộ sưu tập phân công tài nguyên có ở chế độ chỉ đọc hay không:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Bước 8: Chuyển đổi Bộ sưu tập thành Danh sách và Lặp lại
Chuyển đổi bộ sưu tập thành một danh sách và lặp lại nó:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Phần kết luận
Chúc mừng! Bạn đã học cách quản lý việc gán tài nguyên trong Microsoft Project bằng Aspose.Tasks for .NET. Bằng cách làm theo các bước này, bạn có thể thao tác các tác vụ và tài nguyên một cách hiệu quả, giúp việc quản lý dự án trở nên dễ dàng.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với các phiên bản khác nhau của tệp Microsoft Project không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.
### Câu hỏi: Có phiên bản dùng thử trước khi mua Aspose.Tasks cho .NET không?
 Trả lời: Có, bạn có thể dùng thử miễn phí Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ nếu tôi gặp bất kỳ sự cố nào khi sử dụng Aspose.Tasks cho .NET?
 Trả lời: Bạn có thể tìm kiếm sự hỗ trợ từ diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Tôi có thể sử dụng giấy phép tạm thời cho Aspose.Tasks cho .NET không?
 Đáp: Có, giấy phép tạm thời được cấp cho mục đích đánh giá. Bạn có thể lấy một cái từ[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể mua giấy phép đầy đủ cho Aspose.Tasks cho .NET ở đâu?
 Trả lời: Bạn có thể mua giấy phép đầy đủ từ cửa hàng trực tuyến Aspose[đây](https://purchase.aspose.com/buy).