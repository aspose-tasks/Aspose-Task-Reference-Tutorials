---
title: Xử lý các phần phân chia dự án MS trong Aspose.Tasks
linktitle: Xử lý các phần phân chia trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý các phần phân chia MS Project một cách hiệu quả với Aspose.Tasks for .NET. Tăng cường quy trình quản lý dự án của bạn.
weight: 18
url: /vi/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xử lý các phần phân chia dự án MS trong Aspose.Tasks


## Giới thiệu
Quản lý các phần phân chia MS Project có thể là một khía cạnh quan trọng trong quản lý dự án khi sử dụng Aspose.Tasks cho .NET. Trong hướng dẫn này, chúng ta sẽ khám phá cách xử lý hiệu quả các phần bị tách bằng cách sử dụng hướng dẫn từng bước.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Cài đặt Aspose.Tasks cho .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[trang mạng](https://releases.aspose.com/tasks/net/).
   
2. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.

## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Bước 1: Tạo một phiên bản dự án
```csharp
var project = new Project();
```
 Tạo một phiên bản mới của`Project` lớp học.
## Bước 2: Đặt ngày bắt đầu và kết thúc dự án
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Đặt ngày bắt đầu và kết thúc cho dự án.
## Bước 3: Thêm tác vụ
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Thêm một nhiệm vụ mới vào dự án.
## Bước 4: Đặt thuộc tính tác vụ
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Đặt các thuộc tính như trạng thái thủ công, ngày bắt đầu và thời lượng cho tác vụ.
## Bước 5: Thêm phân công tài nguyên
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Thêm các bài tập tài nguyên vào nhiệm vụ.
## Bước 6: Đặt thuộc tính bài tập
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Đặt các thuộc tính như ngày bắt đầu, ngày làm việc và ngày kết thúc cho nhiệm vụ.
## Bước 7: Tạo dữ liệu theo pha thời gian
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Tạo dữ liệu theo pha thời gian cho nhiệm vụ dựa trên lịch dự án.
## Bước 8: Chia nhiệm vụ
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Chia nhiệm vụ thành nhiều phần trong khung thời gian quy định.
## Bước 9: Lặp lại các phần được chia nhỏ
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Lặp lại các phần được phân chia của nhiệm vụ và in ngày bắt đầu và kết thúc của chúng.

## Phần kết luận
Việc xử lý hiệu quả các phần phân chia MS Project trong Aspose.Tasks cho .NET là rất quan trọng đối với hiệu quả quản lý dự án. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể quản lý liền mạch các nhiệm vụ được phân chia và nâng cao quy trình quản lý dự án của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với các khung .NET khác không?
Trả lời: Có, Aspose.Tasks cho .NET tương thích với nhiều khung .NET khác nhau bao gồm .NET Core và .NET Standard.
### Câu hỏi: Có bản dùng thử miễn phí Aspose.Tasks cho .NET không?
 Đ: Có, bạn có thể nhận bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Aspose.Tasks dành cho .NET có hỗ trợ quản lý tài nguyên không?
Trả lời: Có, Aspose.Tasks for .NET cho phép bạn quản lý tài nguyên dự án một cách hiệu quả.
### Câu hỏi: Tôi có thể tùy chỉnh lịch dự án bằng Aspose.Tasks cho .NET không?
Trả lời: Hoàn toàn có thể, bạn có thể tùy chỉnh lịch dự án theo yêu cầu dự án của mình.
### Câu hỏi: Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho .NET ở đâu?
 Đáp: Bạn có thể tìm thấy sự hỗ trợ và trợ giúp trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
