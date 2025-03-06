---
title: Bộ sưu tập các khoảng thời gian khả dụng trong Aspose.Tasks
linktitle: Bộ sưu tập các khoảng thời gian khả dụng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý khoảng thời gian sẵn có của tài nguyên trong Aspose.Tasks for .NET. Hướng dẫn từng bước này hướng dẫn bạn cách thêm, cập nhật và xóa các khoảng thời gian sẵn có, đảm bảo lập kế hoạch nguồn lực dự án hiệu quả.
weight: 18
url: /vi/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bộ sưu tập các khoảng thời gian khả dụng trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với bộ sưu tập tài nguyên trong khoảng thời gian khả dụng trong Aspose.Tasks cho .NET. Quản lý thời gian sẵn sàng là rất quan trọng đối với việc quản lý dự án, cho phép chúng tôi xác định thời điểm có sẵn nguồn lực cho các nhiệm vụ trong dự án.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản: Làm quen với C# và .NET framework.

## Nhập không gian tên

Đầu tiên, chúng ta cần nhập các không gian tên cần thiết vào dự án của mình:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Hãy chia mã ví dụ thành nhiều bước và hiểu từng phần:

## Bước 1: Khởi tạo dự án và tài nguyên

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Ở đây, chúng tôi đang tải một tệp dự án và lấy tài nguyên cụ thể theo ID của nó.

## Bước 2: Xóa khoảng thời gian sẵn có hiện tại

```csharp
resource.AvailabilityPeriods.Clear();
```

Chúng tôi xóa mọi khoảng thời gian sẵn có hiện có liên quan đến tài nguyên.

## Bước 3: Thêm khoảng thời gian sẵn có

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Chúng tôi lặp lại qua một tập hợp các khoảng thời gian sẵn có và thêm chúng vào tài nguyên.

## Bước 4: Chèn Khoảng thời gian sẵn sàng mới

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Chúng tôi tạo khoảng thời gian có sẵn mới cho năm 2013 và chèn nó vào bộ sưu tập.

## Bước 5: Hiển thị thời gian có hàng

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Chúng tôi in ra số lượng và chi tiết của từng khoảng thời gian sẵn có liên quan đến tài nguyên.

## Bước 6: Sao chép khoảng thời gian sẵn sàng sang tài nguyên khác

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Chúng tôi sao chép khoảng thời gian sẵn có từ tài nguyên này sang tài nguyên khác.

## Bước 7: Cập nhật và xóa khoảng thời gian sẵn sàng

```csharp
// Cập nhật các đơn vị có sẵn trong một khoảng thời gian cụ thể
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Xóa một khoảng thời gian cụ thể
otherResource.AvailabilityPeriods.Remove(period2013);
```

Chúng tôi cập nhật các đơn vị có sẵn trong một khoảng thời gian và xóa các khoảng thời gian cụ thể khỏi bộ sưu tập.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách làm việc với các bộ sưu tập khoảng thời gian khả dụng trong Aspose.Tasks dành cho .NET. Quản lý nguồn lực sẵn có là điều cần thiết để lập kế hoạch và thực hiện dự án hiệu quả.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể thêm trường tùy chỉnh vào khoảng thời gian sẵn có không?

Trả lời 1: Không, khoảng thời gian khả dụng trong Aspose.Tasks dành cho .NET không hỗ trợ các trường tùy chỉnh.

### Câu hỏi 2: Khoảng thời gian sẵn sàng có liên quan đến các nhiệm vụ cụ thể không?

Câu trả lời 2: Không, khoảng thời gian sẵn sàng được liên kết với các nguồn lực và xác định thời điểm chúng sẵn sàng cho các nhiệm vụ nói chung.

### Câu hỏi 3: Tôi có thể nhập khoảng thời gian sẵn có từ các nguồn bên ngoài không?

Câu trả lời 3: Có, bạn có thể nhập khoảng thời gian sẵn sàng từ nhiều nguồn dữ liệu khác nhau bằng Aspose.Tasks cho API .NET.

### Câu hỏi 4: Làm cách nào để xử lý các khoảng thời gian sẵn có chồng chéo?

Câu trả lời 4: Aspose.Tasks dành cho .NET không cung cấp cơ chế tích hợp sẵn để xử lý các khoảng thời gian chồng chéo. Bạn có thể cần triển khai logic tùy chỉnh để quản lý các tình huống như vậy.

### Câu hỏi 5: Có giới hạn về số lượng thời gian sẵn sàng mà một nguồn lực có thể có không?

Câu trả lời 5: Không có giới hạn được xác định trước đối với số khoảng thời gian khả dụng mà tài nguyên có thể có, nhưng hiệu suất có thể giảm theo số lượng khoảng thời gian lớn.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
