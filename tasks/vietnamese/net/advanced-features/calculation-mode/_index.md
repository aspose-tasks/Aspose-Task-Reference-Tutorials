---
date: 2026-03-24
description: Tìm hiểu cách thiết lập chế độ tính toán trong Aspose.Tasks cho .NET,
  bao gồm chế độ tính toán tự động, thủ công và không tính toán để quản lý phụ thuộc
  của các nhiệm vụ.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Cách thiết lập chế độ tính toán trong Aspose.Tasks cho .NET
url: /vi/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Chế Độ Tính Toán trong Aspose.Tasks cho .NET

## Giới thiệu

Aspose.Tasks for .NET là một API mạnh mẽ cho phép bạn làm việc với các tệp Microsoft Project một cách lập trình. Một trong những cài đặt quan trọng nhất mà bạn sẽ gặp là **calculation mode**, điều khiển cách ngày của nhiệm vụ và lịch trình dự án được cập nhật. Trong hướng dẫn này, bạn sẽ học **how to set calculation** mode, khám phá **automatic calculation mode**, **manual calculation mode**, và **none calculation mode**, và xem các tùy chọn này ảnh hưởng như thế nào đến **manage task dependencies**, **create project start date**, và **link tasks finish‑start** relationships.

## Câu trả lời nhanh
- **What is calculation mode?** Nó xác định liệu ngày của nhiệm vụ có được tính lại tự động, thủ công, hay không tính lại nào cả.  
- **Why use manual calculation mode?** Để có kiểm soát hoàn toàn thời điểm lịch trình được làm mới, hữu ích khi cập nhật hàng loạt.  
- **Which mode is default?** Automatic calculation mode, cập nhật ngày ngay lập tức sau khi có thay đổi.  
- **Can I change the mode at runtime?** Có — chỉ cần đặt thuộc tính `CalculationMode` trên đối tượng `Project`.  
- **Do I need a license?** Cần một giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.

## “how to set calculation” là gì trong Aspose.Tasks?

Đặt chế độ tính toán đơn giản như việc gán một giá trị enum cho thuộc tính `Project.CalculationMode`. Enum này cung cấp ba tùy chọn: `Automatic`, `Manual`, và `None`. Lựa chọn chế độ phù hợp phụ thuộc vào quy trình làm việc của bạn — bạn muốn cập nhật ngay lập tức, xử lý theo lô, hay kiểm soát hoàn toàn.

## Yêu cầu trước

1. **Visual Studio** — bất kỳ phiên bản mới nào (2019, 2022 hoặc mới hơn).  
2. **Aspose.Tasks for .NET** — tải xuống và cài đặt thư viện từ [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** — bạn nên thoải mái khi tạo ứng dụng console và sử dụng các gói NuGet.

## Import Namespaces

Trước khi bắt đầu làm việc với Aspose.Tasks cho .NET, hãy nhập các namespace cần thiết:

```csharp
using Aspose.Tasks;
using System;
```

## Cách Đặt Chế Độ Tính Toán

Dưới đây bạn sẽ tìm thấy các ví dụ từng bước cho mỗi chế độ tính toán. Các khối mã không thay đổi so với hướng dẫn gốc; phần giải thích xung quanh đã được mở rộng để rõ ràng hơn.

### Áp Dụng Chế Độ Tính Toán Tự Động

Chế độ tự động tính lại ngày ngay lập tức mỗi khi bạn sửa đổi nhiệm vụ hoặc liên kết.

#### Bước 1: Tạo một thể hiện Project mới

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Bước 2: Đặt ngày bắt đầu dự án và thêm nhiệm vụ

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Bước 3: Liên kết nhiệm vụ (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Bước 4: Xác minh các ngày đã được tính lại

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Áp Dụng Chế Độ Tính Toán Thủ Công

Chế độ thủ công vô hiệu hoá cập nhật tự động, cho phép bạn xử lý các thay đổi theo lô trước khi buộc tính lại.

#### Bước 1: Tạo một thể hiện Project mới

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Bước 2: Đặt ngày bắt đầu dự án và thêm nhiệm vụ

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Bước 3: Xác minh thuộc tính nhiệm vụ

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Bước 4: Liên kết nhiệm vụ và xác minh ngày (không có tính toán tự động)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Áp Dụng Chế Độ Không Tính Toán

Chế độ không tắt toàn bộ các phép tính nội bộ. Sử dụng khi bạn chỉ cần đọc hoặc xuất dữ liệu mà không thay đổi lịch trình.

#### Bước 1: Tạo một thể hiện Project mới

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Bước 2: Thêm một nhiệm vụ mới

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Bước 3: Xác minh thuộc tính nhiệm vụ (không có ID tự động)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Các Vấn Đề Thường Gặp và Giải Pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| Ngày không cập nhật sau khi liên kết nhiệm vụ | Dự án đang ở chế độ **Manual** hoặc **None** | Đặt `project.CalculationMode = CalculationMode.Automatic` hoặc gọi `project.Calculate()` thủ công |
| ID nhiệm vụ vẫn là 0 | Sử dụng chế độ **None** ngăn việc tạo ID | Chuyển sang chế độ **Automatic** hoặc **Manual**, sau đó tính lại |
| Liên kết thất bại với `ArgumentException` | Ngày bắt đầu của predecessor muộn hơn successor khi dùng chế độ **Manual** mà không tính lại | Đảm bảo ngày bắt đầu đúng hoặc tính lại sau khi thêm liên kết |

## Câu Hỏi Thường Gặp

**Q1: Tôi có thể thay đổi chế độ tính toán một cách động trong thời gian chạy không?**  
A1: Có, bạn có thể sửa đổi thuộc tính `CalculationMode` bất kỳ lúc nào trong mã và sau đó gọi `project.Calculate()` nếu cần cập nhật ngay lập tức.

**Q2: Aspose.Tasks có hỗ trợ các định dạng tệp quản lý dự án khác ngoài Microsoft Project không?**  
A2: Aspose.Tasks chủ yếu tập trung vào các định dạng Microsoft Project, nhưng cũng hỗ trợ Primavera P6 XML, Primavera DB, và Asta Powerproject XML.

**Q3: Aspose.Tasks có phù hợp cho cả dự án quy mô nhỏ và dự án doanh nghiệp không?**  
A3: Chắc chắn. API có thể mở rộng từ danh sách nhiệm vụ đơn giản đến lịch trình doanh nghiệp phức tạp, đa giai đoạn.

**Q4: Tôi có thể tích hợp Aspose.Tasks với các thư viện và framework .NET khác không?**  
A4: Có, bạn có thể kết hợp Aspose.Tasks với ASP.NET, WPF, Xamarin, hoặc bất kỳ công nghệ .NET nào khác để xây dựng các giải pháp quản lý dự án phong phú.

**Q5: Có diễn đàn cộng đồng hoặc kênh hỗ trợ nào dành cho người dùng Aspose.Tasks không?**  
A5: Có, bạn có thể truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ cộng đồng và thảo luận.

---

**Cập nhật lần cuối:** 2026-03-24  
**Kiểm thử với:** Aspose.Tasks 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}