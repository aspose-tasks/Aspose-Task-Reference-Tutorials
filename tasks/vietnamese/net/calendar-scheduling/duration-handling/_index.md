---
title: Xử lý thời lượng trong Aspose.Tasks
linktitle: Xử lý thời lượng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý thời lượng hiệu quả trong Aspose.Tasks for .NET với hướng dẫn từng bước.
weight: 30
url: /vi/net/calendar-scheduling/duration-handling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xử lý thời lượng trong Aspose.Tasks

## Giới thiệu

Xử lý thời lượng một cách hiệu quả là rất quan trọng trong các ứng dụng quản lý dự án. Aspose.Tasks for .NET cung cấp chức năng mạnh mẽ để quản lý thời lượng một cách hiệu quả. Trong hướng dẫn này, chúng ta sẽ khám phá các khía cạnh khác nhau của việc xử lý thời lượng bằng Aspose.Tasks cho .NET.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1. Kiến thức cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C# để hiểu và triển khai các ví dụ.
2. Visual Studio: Cài đặt Visual Studio IDE để tạo và chạy các ứng dụng .NET.
3.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết để sử dụng các chức năng của Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Hãy chia mỗi ví dụ thành nhiều bước theo định dạng hướng dẫn từng bước:

## Cập nhật thời lượng của nhiệm vụ

### Bước 1: Tải tệp dự án

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Bước 2: Nhận nhiệm vụ và thời lượng

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Bước 3: Thời lượng cập nhật

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Bước 4: Hiển thị thời lượng cập nhật

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Trừ đi thời gian của nhiệm vụ

### Bước 1: Tải tệp dự án

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Bước 2: Nhận nhiệm vụ và thời lượng

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Bước 3: Trừ thời lượng

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Bước 4: Hiển thị thời lượng cập nhật

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Chuyển đổi thời lượng thành TimeSpan

### Bước 1: Tải tệp dự án

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Bước 2: Nhận nhiệm vụ và thời lượng

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Bước 3: Chuyển đổi thời lượng thành TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Chuyển đổi thời lượng thành chuỗi

### Bước 1: Tải tệp dự án

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Bước 2: Nhận nhiệm vụ và thời lượng

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Bước 3: Chuyển đổi thời lượng thành chuỗi

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã đề cập đến các khía cạnh khác nhau của việc xử lý thời lượng trong Aspose.Tasks cho .NET. Hiểu và quản lý hiệu quả thời lượng là rất quan trọng để quản lý dự án thành công. Aspose.Tasks cung cấp các chức năng toàn diện để đơn giản hóa các tác vụ quản lý thời lượng trong các ứng dụng .NET của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks dành cho .NET là gì?

Câu trả lời 1: Aspose.Tasks for .NET là một thư viện mạnh mẽ để làm việc với các tệp Microsoft Project trong các ứng dụng .NET.

### Câu hỏi 2: Aspose.Tasks có thể xử lý các cấu trúc dự án phức tạp không?

Câu trả lời 2: Có, Aspose.Tasks có thể xử lý các cấu trúc dự án phức tạp một cách dễ dàng, cung cấp các API mở rộng để thao tác.

### Câu hỏi 3: Aspose.Tasks dành cho .NET có tương thích với .NET Core không?

Câu trả lời 3: Có, Aspose.Tasks for .NET tương thích với .NET Core, cho phép bạn sử dụng nó trong các ứng dụng đa nền tảng.

### Câu hỏi 4: Aspose.Tasks có hỗ trợ đọc và ghi tệp Microsoft Project không?

A4: Có, Aspose.Tasks hỗ trợ đọc và ghi các tệp Microsoft Project ở nhiều định dạng khác nhau, bao gồm MPP, XML và MPX.

### Câu hỏi 5: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?

Câu trả lời 5: Có, bạn có thể dùng thử miễn phí Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
