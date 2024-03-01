---
title: Làm việc với Khoảng thời gian sẵn có trong Aspose.Tasks
linktitle: Làm việc với Khoảng thời gian sẵn có trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý hiệu quả thời gian sẵn có của tài nguyên bằng Aspose.Tasks cho .NET. Hướng dẫn này cung cấp hướng dẫn từng bước để làm việc với các khoảng thời gian sẵn có trong dự án .NET của bạn.
type: docs
weight: 17
url: /vi/net/advanced-features/working-with-availability-periods/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các khoảng thời gian khả dụng trong Aspose.Tasks dành cho .NET. Khoảng thời gian sẵn sàng là rất quan trọng để quản lý tài nguyên hiệu quả trong các tình huống quản lý dự án. Chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1. Visual Studio: Cài đặt Visual Studio hoặc bất kỳ IDE ưa thích nào khác để phát triển .NET.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về lập trình C#: Làm quen với những điều cơ bản về ngôn ngữ lập trình C# sẽ rất hữu ích.

## Nhập không gian tên

Trước khi đi sâu vào mã, hãy đảm bảo nhập các không gian tên cần thiết:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Hãy chia mã ví dụ thành nhiều bước:

## Bước 1: Tạo một phiên bản Project mới

```csharp
var project = new Project();
```

Dòng này khởi tạo một phiên bản mới của lớp Project, đại diện cho một dự án trong Aspose.Tasks.

## Bước 2: Thêm tài nguyên

```csharp
var resource = project.Resources.Add("Work Resource");
```

Ở đây, chúng tôi thêm một tài nguyên mới vào dự án với tên "Tài nguyên công việc".

## Bước 3: Xác định khoảng thời gian sẵn có

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Chúng tôi gọi`GetPeriods()` phương pháp để truy xuất một tập hợp các khoảng thời gian sẵn có.

## Bước 4: Thêm khoảng thời gian sẵn sàng vào tài nguyên

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Chúng tôi lặp lại việc tập hợp các khoảng thời gian sẵn có có được ở bước trước và thêm chúng vào tài nguyên.

## Bước 5: Hiển thị chi tiết thời gian có hàng

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Cuối cùng, chúng tôi lặp lại các khoảng thời gian sẵn có liên quan đến tài nguyên và in thông tin chi tiết của chúng, bao gồm ngày bắt đầu, ngày kết thúc và các đơn vị có sẵn.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách làm việc với các khoảng thời gian khả dụng trong Aspose.Tasks cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể quản lý hiệu quả tính khả dụng của tài nguyên trong các ứng dụng quản lý dự án của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks cho .NET trong các dự án thương mại không?

 Câu trả lời 1: Có, Aspose.Tasks cho .NET có thể được sử dụng trong các dự án thương mại. Bạn có thể mua giấy phép[đây](https://purchase.aspose.com/buy).

### Câu hỏi 2: Có bản dùng thử miễn phí dành cho Aspose.Tasks dành cho .NET không?

Câu trả lời 2: Có, bạn có thể nhận bản dùng thử miễn phí Aspose.Tasks cho .NET[đây](https://releases.aspose.com/).

### Câu hỏi 3: Tôi có thể tìm tài liệu về Aspose.Tasks cho .NET ở đâu?

 A3: Bạn có thể tìm thấy tài liệu[đây](https://reference.aspose.com/tasks/net/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?

 A4: Bạn có thể nhận được hỗ trợ từ diễn đàn cộng đồng[đây](https://forum.aspose.com/c/tasks/15).

### Câu hỏi 5: Bạn có cung cấp giấy phép tạm thời cho Aspose.Tasks cho .NET không?

 Câu trả lời 5: Có, giấy phép tạm thời có sẵn[đây](https://purchase.aspose.com/temporary-license/).