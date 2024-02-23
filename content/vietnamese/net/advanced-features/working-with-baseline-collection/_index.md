---
title: Làm việc với Bộ sưu tập đường cơ sở trong Aspose.Tasks
linktitle: Làm việc với Bộ sưu tập đường cơ sở trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý đường cơ sở trong Aspose.Tasks cho .NET một cách hiệu quả. Hãy làm theo hướng dẫn toàn diện của chúng tôi để được hướng dẫn từng bước.
type: docs
weight: 20
url: /vi/net/advanced-features/working-with-baseline-collection/
---
## Giới thiệu

Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc liền mạch với các tệp Microsoft Project trong ứng dụng .NET của họ. Trong số nhiều tính năng của nó, nó cung cấp sự hỗ trợ mạnh mẽ để quản lý đường cơ sở trong các dự án. Đường cơ sở rất cần thiết cho việc quản lý dự án vì chúng cho phép bạn so sánh kế hoạch dự án ban đầu với trạng thái hiện tại, cho phép theo dõi và phân tích tiến độ dự án tốt hơn.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào làm việc với các bộ sưu tập cơ sở trong Aspose.Tasks, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:

1. Visual Studio: Cài đặt Visual Studio IDE trên hệ thống của bạn.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[Liên kết tải xuống](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C#.
4. Tệp Microsoft Project: Chuẩn bị sẵn tệp Microsoft Project (.mpp) cho mục đích thử nghiệm.

## Nhập không gian tên

Để bắt đầu làm việc với các bộ sưu tập cơ sở trong Aspose.Tasks, bạn cần nhập các không gian tên sau:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Bây giờ, hãy chia từng ví dụ thành nhiều bước:

## Bước 1: Tải tệp dự án

Đầu tiên, tải tệp Microsoft Project bằng Aspose.Tasks:

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Bước 2: Nhận tài nguyên

Tiếp theo, lấy tài nguyên mong muốn từ dự án:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Bước 3: Hiển thị thông tin cơ bản

Bây giờ, hiển thị thông tin về đường cơ sở được liên kết với tài nguyên:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Bước 4: Lặp lại các đường cơ sở

Lặp lại qua từng đường cơ sở được liên kết với tài nguyên và in thông tin liên quan:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Bước 5: Xóa đường cơ sở

Xóa tất cả các đường cơ sở được liên kết với tài nguyên:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách làm việc với các bộ sưu tập cơ sở trong Aspose.Tasks cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể dễ dàng quản lý đường cơ sở trong các ứng dụng .NET của mình, cho phép theo dõi và phân tích dự án hiệu quả.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Tasks có thể xử lý các tệp dự án lớn không?

Câu trả lời 1: Có, Aspose.Tasks được tối ưu hóa để xử lý các tệp dự án lớn một cách hiệu quả, đảm bảo hiệu suất mượt mà.

### Câu hỏi 2: Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?

Trả lời 2: Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.

### Câu hỏi 3: Tôi có thể tùy chỉnh đường cơ sở trong Aspose.Tasks không?

Câu trả lời 3: Có, bạn có thể tùy chỉnh đường cơ sở theo yêu cầu dự án của mình bằng cách sử dụng Aspose.Tasks for .NET.

### Câu hỏi 4: Aspose.Tasks có cung cấp hỗ trợ cho nền tảng đám mây không?

Câu trả lời 4: Có, Aspose.Tasks cung cấp hỗ trợ tích hợp với các nền tảng đám mây phổ biến, mang lại sự linh hoạt trong việc triển khai.

### Câu hỏi 5: Có diễn đàn cộng đồng nào dành cho người dùng Aspose.Tasks tìm kiếm trợ giúp và chia sẻ kiến thức không?

 A5: Có, bạn có thể truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để tương tác với cộng đồng và nhận được sự hỗ trợ từ các chuyên gia.