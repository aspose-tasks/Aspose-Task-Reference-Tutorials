---
title: Định cấu hình tùy chọn MS Project XLSX trong Aspose.Tasks cho .NET
linktitle: Định cấu hình tùy chọn XLSX trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách định cấu hình các tùy chọn MS Project XLSX trong Aspose.Tasks cho .NET. Tùy chỉnh cột, mã hóa và dễ dàng hơn.
type: docs
weight: 11
url: /vi/net/file-format-options/configuring-xlsx-options/
---
## Giới thiệu
Microsoft Project (MS Project) là một công cụ mạnh mẽ để quản lý dự án và Aspose.Tasks for .NET cung cấp khả năng tích hợp liền mạch để làm việc với các tệp MS Project theo chương trình. Trong hướng dẫn này, chúng ta sẽ hướng dẫn quy trình định cấu hình các tùy chọn MS Project XLSX bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
### 1. Aspose.Tasks cho .NET đã được cài đặt
 Đảm bảo bạn đã cài đặt Aspose.Tasks for .NET trong môi trường phát triển của mình. Nếu không, bạn có thể tải xuống từ[Trang tải xuống Aspose.Tasks cho .NET](https://releases.aspose.com/tasks/net/).
### 2. Hiểu biết cơ bản về C# và .NET Framework
Cần phải làm quen với ngôn ngữ lập trình C# và .NET framework để tuân theo hướng dẫn này.
### 3. Tệp dự án Microsoft
Chuẩn bị sẵn tệp Microsoft Project (MPP) mà bạn muốn đặt cấu hình và lưu dưới dạng tệp XLSX.

## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Bước 1: Tải dự án
```csharp
var project = new Project("YourProjectFile.mpp");
```
Tải tệp Microsoft Project mà bạn muốn cấu hình.
## Bước 2: Xác định XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Tạo một thể hiện của`XlsxOptions` để định cấu hình cài đặt để lưu dưới dạng XLSX.
## Bước 3: Thêm cột biểu đồ Gantt
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Thêm các cột Biểu đồ Gantt mong muốn vào các tùy chọn.
## Bước 4: Thêm cột xem tài nguyên
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Bao gồm các cột mong muốn cho chế độ xem tài nguyên trong các tùy chọn.
## Bước 5: Thêm cột xem bài tập
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Thêm các cột mong muốn cho chế độ xem bài tập trong các tùy chọn.
## Bước 6: Đặt mã hóa
```csharp
options.Encoding = Encoding.Unicode;
```
Đặt mã hóa cho tệp đầu ra.
## Bước 7: Lưu dự án dưới dạng XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Lưu dự án với các tùy chọn đã định cấu hình dưới dạng tệp XLSX.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách định cấu hình các tùy chọn MS Project XLSX bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể tùy chỉnh định dạng đầu ra theo yêu cầu của mình, nâng cao tính linh hoạt và khả năng sử dụng của quy trình quản lý dự án của bạn.
## Câu hỏi thường gặp

### Câu hỏi: Tôi có thể đặt cấu hình riêng các cột khác nhau cho Biểu đồ Gantt, Chế độ xem tài nguyên và Chế độ xem bài tập không?

Trả lời: Có, bạn có thể tùy chỉnh các cột độc lập cho từng chế độ xem bằng Aspose.Tasks for .NET.

### Câu hỏi: Có phiên bản dùng thử trước khi mua Aspose.Tasks cho .NET không?

 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[Trang phát hành Aspose.Tasks cho .NET](https://releases.aspose.com/).

### Hỏi: Làm cách nào tôi có thể nhận được hỗ trợ nếu gặp bất kỳ vấn đề nào hoặc có thắc mắc trong quá trình triển khai?

 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ từ cộng đồng và nhóm hỗ trợ Aspose.

### Câu hỏi: Tôi có thể tạo tệp XLSX bằng Aspose.Tasks cho .NET trên nền tảng không phải Windows không?

Trả lời: Aspose.Tasks cho .NET được thiết kế chủ yếu cho nền tảng Windows, nhưng bạn có thể khám phá các tùy chọn tương thích cho các nền tảng khác.

### Câu hỏi: Có bất kỳ tùy chọn giấy phép tạm thời nào dành cho mục đích thử nghiệm không?

 Đáp: Có, bạn có thể xin giấy phép tạm thời từ[Trang giấy phép tạm thời Aspose.Tasks](https://purchase.aspose.com/temporary-license/).