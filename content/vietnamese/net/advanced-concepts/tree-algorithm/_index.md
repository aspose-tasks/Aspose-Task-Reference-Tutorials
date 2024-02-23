---
title: Sử dụng thuật toán cây trong Aspose.Tasks
linktitle: Sử dụng thuật toán cây trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thao tác hiệu quả hệ thống phân cấp nhiệm vụ trong các dự án .NET của bạn bằng Thuật toán cây của Aspose.Tasks.
type: docs
weight: 13
url: /vi/net/advanced-concepts/tree-algorithm/
---
## Giới thiệu

Aspose.Tasks for .NET cung cấp các chức năng mạnh mẽ để làm việc với các nhiệm vụ, tài nguyên và lịch trình quản lý dự án. Một tính năng như vậy là Thuật toán cây, cho phép người dùng thao tác phân cấp nhiệm vụ một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Thuật toán cây trong Aspose.Tasks cho .NET để thu thập công việc chung và cập nhật các giá trị công việc trong một dự án.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# theo các ví dụ.

## Nhập không gian tên

Trong dự án C# của bạn, hãy nhập các vùng tên cần thiết để hoạt động với các chức năng của Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Bây giờ, hãy chia từng ví dụ thành nhiều bước:

## Bước 1: Tải tệp dự án

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Tải tệp dự án vào bộ nhớ bằng cách sử dụng`Project` lớp học.

## Bước 2: Xác định hệ thống phân cấp nhiệm vụ

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Xác định hệ thống phân cấp nhiệm vụ bằng cách thêm nhiệm vụ cha và con.

## Bước 3: Đặt thuộc tính tác vụ

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Đặt các thuộc tính như ngày bắt đầu, thời lượng và ngày kết thúc cho nhiệm vụ.

## Bước 4: Thêm tài nguyên

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Thêm tài nguyên vào dự án và phân công chúng cho các nhiệm vụ nếu cần.

## Bước 5: Áp dụng thuật toán cây

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Khởi tạo`WorkAccumulator` lớp và áp dụng Thuật toán cây để tập hợp công việc chung.

## Bước 6: Cập nhật công việc nhiệm vụ

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Cập nhật giá trị công việc cho các nhiệm vụ dựa trên thông tin đã thu thập được.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách sử dụng Thuật toán cây trong Aspose.Tasks dành cho .NET để thao tác phân cấp nhiệm vụ một cách hiệu quả. Bằng cách làm theo hướng dẫn từng bước, bạn có thể quản lý hiệu quả các nhiệm vụ và tài nguyên trong dự án của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks dành cho .NET là gì?

Câu trả lời 1: Aspose.Tasks dành cho .NET là một API mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình bằng cách sử dụng C#.

### Câu hỏi 2: Tôi có thể tải xuống bản dùng thử miễn phí Aspose.Tasks cho .NET không?

 Câu trả lời 2: Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/).

### Câu hỏi 3: Tôi có thể tìm tài liệu về Aspose.Tasks cho .NET ở đâu?

 Câu trả lời 3: Bạn có thể tìm tài liệu về Aspose.Tasks for .NET[đây](https://reference.aspose.com/tasks/net/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?

 Câu trả lời 4: Để được hỗ trợ liên quan đến Aspose.Tasks cho .NET, bạn có thể truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Câu hỏi 5: Có giấy phép tạm thời dành cho mục đích thử nghiệm không?

 Câu trả lời 5: Có, bạn có thể xin giấy phép tạm thời cho mục đích thử nghiệm từ[đây](https://purchase.aspose.com/temporary-license/).