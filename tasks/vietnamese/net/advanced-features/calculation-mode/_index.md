---
title: Chế độ tính toán trong Aspose.Tasks
linktitle: Chế độ tính toán trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý các chế độ tính toán hiệu quả trong Aspose.Tasks dành cho .NET để hợp lý hóa việc lập kế hoạch dự án và các phần phụ thuộc của nhiệm vụ.
weight: 29
url: /vi/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chế độ tính toán trong Aspose.Tasks

## Giới thiệu

Aspose.Tasks for .NET là một API mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình trong các ứng dụng .NET của họ. Một khía cạnh quan trọng khi làm việc với các tệp dự án là quản lý các chế độ tính toán, trong đó chỉ ra cách tính toán và cập nhật các nhiệm vụ và lịch trình dự án. Trong hướng dẫn này, chúng ta sẽ đi sâu vào các chế độ tính toán khác nhau được Aspose.Tasks hỗ trợ cho .NET và trình bày cách sử dụng chúng một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên hệ thống của mình.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Hiểu biết cơ bản về lập trình C#: Làm quen với các khái niệm lập trình C#.

## Nhập không gian tên

Trước khi chúng ta bắt đầu làm việc với Aspose.Tasks cho .NET, hãy nhập các vùng tên cần thiết:

```csharp
using Aspose.Tasks;
using System;


```

## Áp dụng chế độ tính toán tự động

### Bước 1: Tạo một phiên bản Project mới

 Khởi tạo một cái mới`Project` đối tượng và thiết lập nó`CalculationMode` tài sản để`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Bước 2: Đặt ngày bắt đầu dự án và thêm nhiệm vụ

Xác định ngày bắt đầu của dự án và thêm nhiệm vụ vào đó.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Bước 3: Liên kết nhiệm vụ

Thiết lập sự phụ thuộc giữa các nhiệm vụ.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Bước 4: Xác minh ngày tính toán lại

Kiểm tra xem ngày có được tính toán lại tự động hay không.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Thêm nhiều xác minh hơn nếu cần
```

## Áp dụng chế độ tính toán thủ công

### Bước 1: Tạo một phiên bản Project mới

 Khởi tạo một cái mới`Project` đối tượng và thiết lập nó`CalculationMode` tài sản để`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Bước 2: Đặt ngày bắt đầu dự án và thêm nhiệm vụ

Xác định ngày bắt đầu của dự án và thêm nhiệm vụ vào đó.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Bước 3: Xác minh thuộc tính nhiệm vụ

Kiểm tra xem thuộc tính tác vụ có được đặt chính xác trong chế độ thủ công hay không.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Thêm nhiều xác minh hơn nếu cần
```

### Bước 4: Liên kết nhiệm vụ và xác minh ngày tháng

Liên kết các nhiệm vụ với nhau và kiểm tra xem ngày của chúng có bị tính toán lại hay không.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Áp dụng chế độ tính toán Không có

### Bước 1: Tạo một phiên bản Project mới

 Khởi tạo một cái mới`Project` đối tượng và thiết lập nó`CalculationMode` tài sản để`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Bước 2: Thêm nhiệm vụ mới

Thêm một nhiệm vụ mới vào dự án.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Bước 3: Xác minh thuộc tính nhiệm vụ

Kiểm tra xem thuộc tính nhiệm vụ có được tính toán tự động hay không.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Thêm nhiều xác minh hơn nếu cần
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá các chế độ tính toán có sẵn trong Aspose.Tasks dành cho .NET và tìm hiểu cách áp dụng chúng trong các tình huống thực tế. Cho dù bạn cần chế độ tự động, thủ công hay không tính toán, Aspose.Tasks đều cung cấp tính linh hoạt để phù hợp với yêu cầu dự án của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể thay đổi chế độ tính toán một cách linh hoạt trong thời gian chạy không?

Trả lời 1: Có, bạn có thể thay đổi chế độ tính toán của dự án tại bất kỳ thời điểm nào trong thời gian chạy bằng cách sửa đổi`CalculationMode` tài sản.

### Câu hỏi 2: Aspose.Tasks có hỗ trợ các định dạng tệp quản lý dự án khác ngoài Microsoft Project không?

Câu trả lời 2: Aspose.Tasks chủ yếu tập trung vào các định dạng tệp Microsoft Project, nhưng nó cũng hỗ trợ các định dạng khác như Primavera P6 XML, Primavera DB và Asta Powerproject XML.

### Câu hỏi 3: Aspose.Tasks có phù hợp cho cả dự án quy mô nhỏ và cấp doanh nghiệp không?

A3: Chắc chắn rồi! Aspose.Tasks được thiết kế để đáp ứng nhu cầu của cả dự án quy mô nhỏ và cấp doanh nghiệp với các tính năng toàn diện và API mạnh mẽ.

### Câu hỏi 4: Tôi có thể tích hợp Aspose.Tasks với các thư viện và khung .NET khác không?

Câu trả lời 4: Có, bạn có thể tích hợp liền mạch Aspose.Tasks với các thư viện và khung .NET khác để nâng cao chức năng của ứng dụng của mình.

### Câu hỏi 5: Có diễn đàn cộng đồng hoặc kênh hỗ trợ nào dành cho người dùng Aspose.Tasks không?

 A5: Có, bạn có thể truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được cộng đồng hỗ trợ và thảo luận.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
