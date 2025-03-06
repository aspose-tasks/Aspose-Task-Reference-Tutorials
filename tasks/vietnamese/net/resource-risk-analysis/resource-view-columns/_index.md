---
title: Tùy chỉnh các cột xem tài nguyên dự án MS trong Aspose.Tasks
linktitle: Tùy chỉnh các cột xem tài nguyên trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách tùy chỉnh các cột xem tài nguyên MS Project một cách hiệu quả bằng cách sử dụng Aspose.Tasks cho .NET. Tạo chế độ xem phù hợp để quản lý dự án tốt hơn.
weight: 17
url: /vi/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tùy chỉnh các cột xem tài nguyên dự án MS trong Aspose.Tasks

## Giới thiệu
Aspose.Tasks for .NET là một API mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình. Một nhiệm vụ phổ biến trong quản lý dự án là tùy chỉnh các dạng xem để hiển thị thông tin cụ thể. Trong hướng dẫn này, chúng ta sẽ khám phá cách tùy chỉnh các cột xem tài nguyên MS Project bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Aspose.Tasks cho Thư viện .NET: Bạn có thể tải xuống từ[đây](https://releases.aspose.com/tasks/net/).
2. Tệp dự án Microsoft: Có sẵn tệp MS Project mẫu để thử nghiệm.
3. Môi trường phát triển: Môi trường phát triển được thiết lập với .NET framework.
## Nhập không gian tên
Đầu tiên, hãy nhập các không gian tên cần thiết vào dự án của chúng ta:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Bước 1: Tải tệp dự án
Tải tệp MS Project bằng API Aspose.Tasks:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Bước 2: Nhận tài nguyên và xác định các tùy chọn
Tiếp theo, lấy tài nguyên có cột xem mà bạn muốn tùy chỉnh và xác định các tùy chọn lưu PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Bước 3: Xác định cột tùy chỉnh
Bây giờ, hãy xác định các cột tùy chỉnh cho chế độ xem tài nguyên. Bạn có thể chỉ định các trường khác nhau và thậm chí sử dụng đại biểu để tính toán tùy chỉnh:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Bước 4: Lặp lại các cột
Lặp lại các cột đã xác định và hiển thị thuộc tính của chúng:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Bước 5: Lưu Chế độ xem tùy chỉnh
Cuối cùng, đặt chế độ xem tùy chỉnh và lưu nó dưới dạng tệp PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Bằng cách làm theo các bước này, bạn có thể tùy chỉnh các cột chế độ xem tài nguyên MS Project một cách hiệu quả bằng cách sử dụng Aspose.Tasks for .NET.
## Phần kết luận
Việc tùy chỉnh các cột chế độ xem tài nguyên MS Project là điều cần thiết để hiển thị thông tin liên quan phù hợp với nhu cầu dự án của bạn. Với Aspose.Tasks cho .NET, tác vụ này trở nên đơn giản và hiệu quả, cho phép bạn tạo các chế độ xem tùy chỉnh một cách dễ dàng.
## Câu hỏi thường gặp
### Tôi có thể tùy chỉnh chế độ xem cho các thành phần khác ngoài tài nguyên không?
Có, Aspose.Tasks cũng cho phép tùy chỉnh các nhiệm vụ, bài tập và các thành phần khác của dự án.
### Aspose.Tasks có hỗ trợ lưu chế độ xem ở các định dạng khác ngoài PDF không?
Có, bạn có thể lưu chế độ xem ở nhiều định dạng khác nhau như XLSX, HTML và hình ảnh.
### Có thể áp dụng định dạng cho chế độ xem tùy chỉnh không?
Hoàn toàn có thể, Aspose.Tasks cung cấp các tùy chọn định dạng mở rộng để nâng cao giao diện của các chế độ xem tùy chỉnh của bạn.
### Tôi có thể cập nhật động chế độ xem tùy chỉnh dựa trên việc thay đổi dữ liệu dự án không?
Có, bạn có thể cập nhật và tạo lại chế độ xem tùy chỉnh bất cứ khi nào dữ liệu dự án cơ bản thay đổi.
### Aspose.Tasks có hỗ trợ phát triển đa nền tảng không?
Aspose.Tasks for .NET chủ yếu nhắm đến các nền tảng .NET, nhưng cũng có các phiên bản dành cho Java và các nền tảng khác.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
