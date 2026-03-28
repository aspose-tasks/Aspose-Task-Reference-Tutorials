---
date: 2026-03-24
description: Tìm hiểu cách thiết lập tính toán trong Aspose.Tasks cho .NET, kèm các
  ví dụ về việc tính các giá trị tổng hợp, định nghĩa công thức tính toán và cấu hình
  tổng hợp rollup.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cách thiết lập loại tính toán trong Aspose.Tasks
url: /vi/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Loại Tính Toán trong Aspose.Tasks

## Giới thiệu

## Câu trả lời nhanh
- **Mục đích chính là gì?** Để kiểm soát cách các giá trị nhiệm vụ và tổng hợp được tính trong tệp Project.  
- **Lớp API nào được sử dụng?** `ExtendedAttributeDefinition` cùng với `CalculationType` và `SummaryRowsCalculationType`.  
- **Tôi có thể sử dụng công thức không?** Có – đặt `CalculationType = CalculationType.Formula` và cung cấp một chuỗi công thức.  
- **Làm thế nào để tổng hợp các giá trị tổng hợp?** Sử dụng `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` và chỉ định một `RollupType` như `Average`.  
- **Tôi có cần giấy phép không?** Cần có giấy phép Aspose.Tasks hợp lệ cho việc sử dụng trong môi trường sản xuất.

## Loại Tính Toán là gì và cách đặt tính toán?

`CalculationType` cho Aspose.Tasks biết cách tính giá trị của một thuộc tính mở rộng. Bạn có thể chọn một giá trị tĩnh, một công thức, hoặc để thư viện tổng hợp giá trị từ các nhiệm vụ con. Đặt tính toán đúng là rất quan trọng khi bạn muốn dự án phản ánh các quy tắc kinh doanh tùy chỉnh mà không cần cập nhật thủ công.

## Tại sao sử dụng loại tính toán để tính các giá trị tổng hợp?

Khi một dự án chứa các nhiệm vụ tổng hợp, bạn thường cần các hàng tổng hợp hiển thị dữ liệu tổng hợp (ví dụ: tổng chi phí, thời lượng trung bình). Bằng cách cấu hình **calculate summary values** thông qua `SummaryRowsCalculationType` và `RollupType`, Aspose.Tasks có thể tự động giữ các tổng hợp này đồng bộ khi bạn chỉnh sửa các nhiệm vụ riêng lẻ.

## Yêu cầu trước

1. Kiến thức cơ bản về C# và .NET framework.  
2. Visual Studio (bất kỳ phiên bản mới nào) đã được cài đặt trên máy của bạn.  
3. Thư viện Aspose.Tasks cho .NET đã được cài đặt – bạn có thể tải xuống từ [here](https://releases.aspose.com/tasks/net/).  
4. Truy cập tài liệu chính thức của Aspose.Tasks cho .NET để tham khảo, có sẵn [here](https://reference.aspose.com/tasks/net/).

## Nhập các Namespace

Before diving into the example, make sure to import the necessary namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Bước 1: Tạo một Project mới

Đầu tiên, chúng ta tạo một đối tượng `Project` trống sẽ chứa các nhiệm vụ và thuộc tính tùy chỉnh của chúng ta.

```csharp
var project = new Project();
```

## Bước 2: Thêm một Nhiệm vụ vào Project

Bây giờ chúng ta **thêm dữ liệu nhiệm vụ** bằng cách tạo một nhiệm vụ đơn giản, đặt ngày bắt đầu và cho nó thời lượng một ngày.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Bước 3: Định nghĩa Loại Tính Toán cho một Thuộc tính Mở rộng (Ví dụ Công thức)

Ở đây chúng ta tạo một định nghĩa thuộc tính mở rộng mà giá trị của nó được tính từ một công thức. Điều này minh họa một **calculation type example** và cho thấy cách **define calculation formula**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Bước 4: Định nghĩa Loại Tính Toán cho Các Hàng Tổng hợp (Cấu hình Rollup Summary)

Tiếp theo, chúng ta tạo một định nghĩa thuộc tính mở rộng khác cho phép Aspose.Tasks **configure rollup summary** bằng cách sử dụng kiểu roll‑up *Average*. Đây là cách điển hình để **calculate summary values** cho chi phí, công việc hoặc các trường tùy chỉnh.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Các Vấn đề Thường gặp & Khắc phục

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| Công thức trả về `null` | Tham chiếu trường không đúng trong công thức | Xác minh tên trường bên trong dấu ngoặc vuông (ví dụ: `[Start]` chứ không phải `[stARt]`). |
| Các hàng tổng hợp hiển thị 0 | `SummaryRowsCalculationType` chưa được đặt hoặc `RollupType` sai | Đảm bảo `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` và chọn một `RollupType` phù hợp. |
| Dự án không tải được sau khi thêm thuộc tính | Không khớp giữa định nghĩa thuộc tính và việc sử dụng trong nhiệm vụ | Thêm định nghĩa thuộc tính **trước** khi bạn gán nó cho bất kỳ nhiệm vụ nào. |

## Kết luận

Trong hướng dẫn này, chúng tôi đã đề cập đến **cách đặt tính toán** các quy tắc trong Aspose.Tasks cho .NET, từ việc tạo một nhiệm vụ đơn giản đến việc định nghĩa cả hai loại tính toán dựa trên công thức và dựa trên roll‑up. Bằng cách nắm vững các cài đặt này, bạn sẽ có khả năng kiểm soát chi tiết **calculate summary values**, cho phép phân tích dự án phong phú hơn mà không cần công việc bảng tính thủ công.

## Câu hỏi thường gặp

### Q1: Loại Tính Toán trong Aspose.Tasks là gì?

A1: Loại Tính Toán trong Aspose.Tasks xác định cách các giá trị được tính cho nhiệm vụ và nhiệm vụ tổng hợp trong một dự án, cung cấp các tùy chọn như Formula và Rollup.

### Q2: Làm thế nào để đặt Loại Tính Toán cho một Thuộc tính Mở rộng?

A2: Bạn có thể đặt Loại Tính Toán cho một Thuộc tính Mở rộng bằng cách định nghĩa thuộc tính CalculationType của nó một cách phù hợp.

### Q3: Tôi có thể tùy chỉnh Loại Tính Toán cho các hàng tổng hợp trong dự án không?

A3: Có, Aspose.Tasks cho phép bạn chỉ định Loại Tính Toán cho các hàng tổng hợp, cho phép bạn tùy chỉnh cách tính giá trị dựa trên yêu cầu của mình.

### Q4: Có các loại Rollup khác nhau cho việc tính toán nhiệm vụ tổng hợp không?

A4: Có, Aspose.Tasks cung cấp các loại Rollup khác nhau như Average, Sum và Count để tính giá trị của các nhiệm vụ tổng hợp.

### Q5: Tôi có thể tìm thêm tài nguyên về Aspose.Tasks cho .NET ở đâu?

A5: Bạn có thể khám phá tài liệu và diễn đàn hỗ trợ cộng đồng có sẵn trên [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) để nhận hướng dẫn và hỗ trợ toàn diện.

---

**Cập nhật lần cuối:** 2026-03-24  
**Kiểm tra với:** Aspose.Tasks for .NET (latest release)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}