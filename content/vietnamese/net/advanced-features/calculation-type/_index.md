---
title: Loại tính toán trong Aspose.Tasks
linktitle: Loại tính toán trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách tùy chỉnh các phép tính giá trị trong các dự án .NET với Loại tính toán trong thư viện Aspose.Tasks.
type: docs
weight: 30
url: /vi/net/advanced-features/calculation-type/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá tính năng Loại tính toán trong Aspose.Tasks cho .NET. Aspose.Tasks là một thư viện mạnh mẽ cho phép các nhà phát triển .NET làm việc với các tệp Microsoft Project mà không cần cài đặt Microsoft Project trên hệ thống của họ. Loại tính toán cho phép chúng ta xác định cách tính các giá trị cho các nhiệm vụ và nhiệm vụ tóm tắt trong một dự án.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:

1. Kiến thức cơ bản về C# và .NET framework.
2. Visual Studio được cài đặt trên hệ thống của bạn.
3.  Aspose.Tasks cho thư viện .NET đã được cài đặt. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
4.  Truy cập vào Aspose.Tasks cho tài liệu .NET để tham khảo, có sẵn[đây](https://reference.aspose.com/tasks/net/).

## Nhập không gian tên

Trước khi đi sâu vào ví dụ, hãy đảm bảo nhập các không gian tên cần thiết:

```csharp
using Aspose.Tasks;
using System;


```

## Bước 1: Tạo một dự án mới

Đầu tiên, hãy tạo một đối tượng dự án mới:

```csharp
var project = new Project();
```

## Bước 2: Thêm nhiệm vụ

Bây giờ, hãy thêm một nhiệm vụ vào dự án của chúng tôi:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Bước 3: Xác định loại tính toán cho thuộc tính mở rộng

Chúng tôi sẽ tạo một định nghĩa thuộc tính mở rộng với Loại tính toán được đặt thành Công thức:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Bước 4: Xác định kiểu tính toán cho hàng tóm tắt

Tiếp theo, chúng ta sẽ tạo một định nghĩa thuộc tính mở rộng khác trong đó các giá trị cho nhiệm vụ tóm tắt được tính toán bằng loại tổng số Trung bình:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách làm việc với Loại tính toán trong Aspose.Tasks cho .NET. Bằng cách xác định Loại tính toán cho các thuộc tính mở rộng, chúng tôi có thể tùy chỉnh cách tính giá trị cho các nhiệm vụ và nhiệm vụ tóm tắt trong dự án, mang lại sự linh hoạt và khả năng kiểm soát cao hơn.

## Câu hỏi thường gặp

### Câu hỏi 1: Loại tính toán trong Aspose.Tasks là gì?

Câu trả lời 1: Loại tính toán trong Aspose.Tasks xác định cách tính giá trị cho các tác vụ và nhiệm vụ tóm tắt trong dự án, cung cấp các tùy chọn như Công thức và Tổng hợp.

### Câu hỏi 2: Làm cách nào để đặt Loại tính toán cho Thuộc tính mở rộng?

Câu trả lời 2: Bạn có thể đặt Loại tính toán cho Thuộc tính mở rộng bằng cách xác định thuộc tính Loại tính toán tương ứng.

### Câu hỏi 3: Tôi có thể tùy chỉnh Loại tính toán cho các hàng tóm tắt trong dự án không?

Câu trả lời 3: Có, Aspose.Tasks cho phép bạn chỉ định Loại tính toán cho các hàng tóm tắt, cho phép bạn điều chỉnh các phép tính giá trị dựa trên yêu cầu của mình.

### Câu hỏi 4: Có sẵn các Loại Tổng hợp khác nhau để tính toán nhiệm vụ tóm tắt không?

Câu trả lời 4: Có, Aspose.Tasks cung cấp nhiều Loại tổng hợp khác nhau như Trung bình, Tổng và Đếm để tính toán giá trị của các tác vụ tóm tắt.

### Câu hỏi 5: Tôi có thể tìm thêm tài nguyên về Aspose.Tasks cho .NET ở đâu?

 Câu trả lời 5: Bạn có thể khám phá các tài liệu và diễn đàn hỗ trợ cộng đồng có sẵn trên[Aspose.Tasks cho .NET](https://reference.aspose.com/tasks/net/) để được hướng dẫn và hỗ trợ toàn diện.