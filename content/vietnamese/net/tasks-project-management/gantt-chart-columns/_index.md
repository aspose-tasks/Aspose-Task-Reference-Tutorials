---
title: Tùy chỉnh các cột biểu đồ Gantt bằng Aspose.Tasks
linktitle: Cột biểu đồ Gantt trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách điều chỉnh các cột biểu đồ Gantt trong Aspose.Tasks cho .NET để hiển thị thông tin nhiệm vụ cụ thể một cách hiệu quả.
type: docs
weight: 21
url: /vi/net/tasks-project-management/gantt-chart-columns/
---
## Giới thiệu
Biểu đồ Gantt là một công cụ cơ bản trong quản lý dự án, cung cấp sự trình bày trực quan về các nhiệm vụ, tiến trình và nguồn lực. Aspose.Tasks for .NET cung cấp các khả năng mạnh mẽ để thao tác biểu đồ Gantt, bao gồm tùy chỉnh các cột để hiển thị thông tin nhiệm vụ cụ thể. Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các cột biểu đồ Gantt bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Cài đặt: Aspose.Tasks for .NET được cài đặt trên hệ thống của bạn. Nếu không, hãy tải xuống và cài đặt nó từ[đây](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển .NET: Kiến thức làm việc về C# và .NET framework.
3. Tệp dự án mẫu: Có tệp Microsoft Project mẫu (`.mpp`) thuận tiện để thử nghiệm. Nếu chưa có, bạn có thể tạo một dự án đơn giản trong MS Project và lưu nó.

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết để làm việc với Aspose.Tasks cho .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Bước 1: Tải tệp dự án
 Tải tệp dự án bằng cách sử dụng`Project` lớp được cung cấp bởi Aspose.Tasks:
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Bước 2: Xác định các cột trong biểu đồ Gantt
Xác định các cột bạn muốn hiển thị trong biểu đồ Gantt. Bạn có thể chỉ định các trường tích hợp hoặc tạo các trường tùy chỉnh:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Bước 3: Lặp lại các cột
Lặp lại các cột đã xác định để truy cập thuộc tính của chúng và hiển thị thông tin:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Bước 4: Lưu biểu đồ Gantt vào CSV
Lưu biểu đồ Gantt với các cột được xác định vào tệp CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Bằng cách làm theo các bước này, bạn có thể làm việc hiệu quả với các cột biểu đồ Gantt trong Aspose.Tasks for .NET, cho phép bạn tùy chỉnh và hiển thị thông tin nhiệm vụ khi cần.

## Phần kết luận
Việc thành thạo thao tác với các cột biểu đồ Gantt trong Aspose.Tasks dành cho .NET mở ra khả năng vô tận để điều chỉnh hình ảnh quản lý dự án theo nhu cầu cụ thể của bạn. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể xử lý thông tin nhiệm vụ một cách hiệu quả và nâng cao tính rõ ràng cũng như tổ chức của dự án.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tạo các cột tùy chỉnh trong Aspose.Tasks cho .NET không?
Trả lời: Có, bạn có thể xác định các cột tùy chỉnh để hiển thị các thuộc tính nhiệm vụ cụ thể theo yêu cầu dự án của mình.
### Câu hỏi: Aspose.Tasks dành cho .NET có tương thích với tất cả các phiên bản của tệp Microsoft Project không?
Trả lời: Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, đảm bảo khả năng tương thích trên các môi trường dự án khác nhau.
### Câu hỏi: Làm cách nào tôi có thể xử lý các cấu trúc dự án phức tạp bằng Aspose.Tasks cho .NET?
Trả lời: Aspose.Tasks cho .NET cung cấp các API và tính năng toàn diện để quản lý các cấu trúc dự án phức tạp, mang lại tính linh hoạt và khả năng mở rộng.
### Câu hỏi: Có bất kỳ hạn chế nào về số lượng cột mà tôi có thể thêm vào biểu đồ Gantt không?
Đáp: Aspose.Tasks dành cho .NET cung cấp các tùy chọn tùy chỉnh mở rộng, cho phép bạn thêm một số lượng cột đáng kể vào biểu đồ Gantt mà không bị giới hạn.
### Câu hỏi: Tôi có thể tìm nguồn hỗ trợ và tài nguyên bổ sung cho Aspose.Tasks cho .NET ở đâu?
Trả lời: Bạn có thể khám phá tài liệu, diễn đàn cộng đồng và các kênh hỗ trợ do Aspose.Tasks cung cấp cho .NET để truy cập các tài nguyên và hỗ trợ toàn diện.