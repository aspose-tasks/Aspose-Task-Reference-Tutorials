---
title: Làm chủ các tùy chọn lưu dự án MS cho Aspose.Tasks
linktitle: Tùy chọn lưu chung cho Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách lưu tệp MS Project một cách hiệu quả bằng Aspose.Tasks cho .NET. Tùy chỉnh các tùy chọn đầu ra dễ dàng cho các dự án của bạn.
type: docs
weight: 17
url: /vi/net/saving-options/general-save-options/
---
## Giới thiệu
Aspose.Tasks for .NET cung cấp các tính năng mạnh mẽ để thao tác các tệp Microsoft Project theo chương trình. Trong hướng dẫn này, chúng ta sẽ đi sâu vào sự phức tạp của việc lưu tệp MS Project bằng nhiều tùy chọn khác nhau do Aspose.Tasks cung cấp. Cụ thể, chúng tôi sẽ tập trung vào các tùy chọn lưu chung có sẵn cho Aspose.Tasks, cho phép bạn điều chỉnh đầu ra theo yêu cầu cụ thể của mình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Cài đặt Aspose.Tasks cho .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[Liên kết tải xuống](https://releases.aspose.com/tasks/net/).
2. Hiểu biết cơ bản về .NET Framework: Làm quen với các khái niệm lập trình .NET là có lợi.

## Nhập không gian tên
Trước khi đi sâu vào mã, hãy đảm bảo nhập các không gian tên cần thiết:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Bước 1: Tải tệp dự án
Trước tiên, bạn cần tải tệp MS Project bằng Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Bước 2: Xác định tùy chọn lưu
 Xác định các tùy chọn lưu theo yêu cầu của bạn. Trong ví dụ này, chúng tôi đang sử dụng`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Bước 3: Tùy chỉnh cột xem
Bạn có thể tùy chỉnh các cột dạng xem như biểu đồ Gantt, dạng xem tài nguyên và dạng xem bài tập. Dưới đây là cách thêm cột vào mỗi cột:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Bước 4: Lưu dự án với các tùy chọn
Cuối cùng, lưu dự án với các tùy chọn đã chỉ định:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Phần kết luận
Nắm vững các tùy chọn lưu chung của MS Project với Aspose.Tasks for .NET cho phép bạn tùy chỉnh hiệu quả định dạng đầu ra theo nhu cầu của dự án.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp MS Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp MS Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?
 Trả lời: Có, bạn có thể khám phá Aspose.Tasks với bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm tài liệu về Aspose.Tasks ở đâu?
 A: Tài liệu chi tiết có thể được tìm thấy[đây](https://reference.aspose.com/tasks/net/), cung cấp hướng dẫn toàn diện về cách sử dụng các tính năng của Aspose.Tasks.
### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks?
 Đáp: Giấy phép tạm thời có sẵn cho mục đích đánh giá[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể tìm kiếm hỗ trợ cho các truy vấn liên quan đến Aspose.Tasks ở đâu?
 Trả lời: Bạn có thể tham gia diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15)để nhận được sự hỗ trợ từ các chuyên gia và các nhà phát triển đồng nghiệp.