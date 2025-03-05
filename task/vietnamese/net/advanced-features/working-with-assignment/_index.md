---
title: Làm việc với Bài tập trong Aspose.Tasks
linktitle: Làm việc với Bài tập trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý các nhiệm vụ dự án trong .NET bằng Aspose.Tasks. Khám phá các đường nét khác nhau để lập kế hoạch nguồn lực.
type: docs
weight: 13
url: /vi/net/advanced-features/working-with-assignment/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các bài tập trong Aspose.Tasks cho .NET. Nhiệm vụ rất quan trọng trong quản lý dự án vì chúng phân bổ nguồn lực cho các nhiệm vụ, giúp lập kế hoạch và theo dõi tiến độ. Chúng tôi sẽ tập trung vào việc tạo dữ liệu theo pha thời gian phân công tài nguyên với nhiều đường nét khác nhau bằng cách sử dụng Aspose.Tasks.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1.  Cài đặt Aspose.Tasks cho .NET: Tải xuống và cài đặt thư viện Aspose.Tasks cho .NET từ[Liên kết tải xuống](https://releases.aspose.com/tasks/net/).
2. Hiểu biết cơ bản về C# và .NET Framework: Cần phải làm quen với ngôn ngữ lập trình C# và các khái niệm .NET framework.

## Nhập không gian tên

Đảm bảo nhập các không gian tên cần thiết vào dự án C# của bạn:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Bước 1: Tạo dự án và nhiệm vụ

Hãy bắt đầu bằng cách tạo một dự án mới và thêm một nhiệm vụ vào đó. Đặt ngày bắt đầu, thời lượng và ngày kết thúc cho nhiệm vụ:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Bước 2: Thêm tài nguyên và phân công nhiệm vụ

Tiếp theo, thêm tài nguyên vào dự án và gán nó cho tác vụ đã tạo trước đó:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Bước 3: Tạo dữ liệu theo pha thời gian với các đường viền khác nhau

Bây giờ, hãy tạo dữ liệu theo pha thời gian với các đường nét khác nhau để phân công tài nguyên:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Bước 4: Thay đổi đường viền và tạo dữ liệu

Chúng ta có thể thay đổi loại đường viền và tạo dữ liệu theo pha thời gian tương ứng. Dưới đây là một số ví dụ:

```csharp
// Thay đổi đường viền
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Tạo dữ liệu theo pha thời gian và in
// Lặp lại bước này cho các loại đường viền khác
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách làm việc với các bài tập trong Aspose.Tasks cho .NET. Chúng tôi đã khám phá việc tạo dữ liệu theo pha thời gian phân công tài nguyên với nhiều đường nét khác nhau. Kiến thức này có thể vô cùng hữu ích trong các tình huống quản lý dự án.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks để lên lịch tác vụ trong ứng dụng .NET của mình không?

Câu trả lời 1: Có, Aspose.Tasks cung cấp các API toàn diện để lập lịch và quản lý tác vụ trong các ứng dụng .NET.

### Câu hỏi 2: Aspose.Tasks có bản dùng thử miễn phí không?

 Câu trả lời 2: Có, bạn có thể tận dụng bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).

### Câu hỏi 3: Có bất kỳ hạn chế nào về số lượng nhiệm vụ hoặc tài nguyên trong Aspose.Tasks không?

Câu trả lời 3: Aspose.Tasks không áp đặt bất kỳ giới hạn nào về số lượng nhiệm vụ hoặc tài nguyên bạn có thể quản lý trong dự án của mình.

### Câu hỏi 4: Tôi có thể tùy chỉnh đường viền cho các nhiệm vụ tài nguyên trong Aspose.Tasks không?

Câu trả lời 4: Có, như được minh họa trong hướng dẫn này, bạn có thể đặt nhiều đường viền khác nhau như con rùa, cái chuông, đỉnh, v.v., tùy theo yêu cầu dự án của bạn.

### Câu hỏi 5: Tôi có thể tìm hỗ trợ cho các truy vấn liên quan đến Aspose.Tasks ở đâu?

Câu trả lời 5: Bạn có thể tìm thấy sự hỗ trợ trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) nơi các chuyên gia và thành viên cộng đồng tích cực tham gia thảo luận.