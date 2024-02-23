---
title: Cột Xem bài tập tùy chỉnh trong Aspose.Tasks
linktitle: Cột Xem bài tập tùy chỉnh trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thêm các cột chế độ xem bài tập tùy chỉnh trong Aspose.Tasks cho .NET để nâng cao khả năng quản lý dự án.
type: docs
weight: 16
url: /vi/net/advanced-features/assignment-view-column/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm các cột tùy chỉnh cho chế độ xem bài tập bằng Aspose.Tasks cho .NET. Các cột tùy chỉnh mang lại sự linh hoạt và cho phép bạn hiển thị thông tin bổ sung có liên quan đến nhu cầu quản lý dự án của bạn.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Kiến thức cơ bản về ngôn ngữ lập trình C#.
2.  Aspose.Tasks cho thư viện .NET đã được cài đặt. Nếu không, bạn có thể tải xuống[đây](https://releases.aspose.com/tasks/net/).
3. Một môi trường phát triển tích hợp (IDE) như Visual Studio.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết để truy cập các lớp và phương thức cần thiết để tạo các cột dạng xem bài tập tùy chỉnh:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Bước 1: Tải dự án

 Để bắt đầu, hãy tải tệp dự án của bạn bằng cách sử dụng`Project` lớp học:

```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Bước 2: Tạo tùy chọn lưu bảng tính

 Tiếp theo, tạo một thể hiện của`Spreadsheet2003SaveOptions` cho phép chúng tôi tùy chỉnh các cột xem bài tập:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Bước 3: Xác định cột tùy chỉnh

 Bây giờ, hãy xác định cột tùy chỉnh của bạn bằng cách tạo một phiên bản của`AssignmentViewColumn`Lớp này yêu cầu tên cột, chiều rộng và hàm đại biểu để chuyển đổi dữ liệu gán thành văn bản cột:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Bước 4: Thêm cột tùy chỉnh vào tùy chọn

Thêm cột tùy chỉnh vào bộ sưu tập cột dạng xem bài tập của các tùy chọn lưu:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Bước 5: Lặp lại các bài tập

Lặp lại từng nhiệm vụ tài nguyên trong dự án và hiển thị văn bản cột tùy chỉnh:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Bước 6: Lưu dự án với các cột tùy chỉnh

Cuối cùng, lưu dự án với các cột xem bài tập tùy chỉnh:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách thêm các cột dạng xem bài tập tùy chỉnh bằng Aspose.Tasks cho .NET. Các cột tùy chỉnh mang đến sự linh hoạt trong việc hiển thị thông tin bổ sung phù hợp với yêu cầu dự án của bạn, nâng cao khả năng quản lý dự án.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể thêm nhiều cột tùy chỉnh vào dạng xem bài tập không?

 Câu trả lời 1: Có, bạn có thể thêm nhiều cột tùy chỉnh bằng cách tạo thêm các phiên bản của`AssignmentViewColumn` và thêm chúng vào`Columns` bộ sưu tập.

### Câu hỏi 2: Có sẵn bộ chuyển đổi được xác định trước cho các trường gán chung không?

Câu trả lời 2: Có, Aspose.Tasks cung cấp các trình chuyển đổi được xác định trước cho các trường gán phổ biến, giúp việc trích xuất dữ liệu cho các cột tùy chỉnh trở nên dễ dàng hơn.

### Câu hỏi 3: Tôi có thể tùy chỉnh hình thức của các cột tùy chỉnh, chẳng hạn như định dạng văn bản hoặc áp dụng kiểu không?

Câu trả lời 3: Có, bạn có thể tùy chỉnh giao diện của các cột tùy chỉnh bằng cách sửa đổi các thuộc tính như chiều rộng, phông chữ và căn chỉnh.

### Câu hỏi 4: Có thể xóa các cột mặc định khỏi chế độ xem bài tập không?

 Đ4: Có, bạn có thể loại bỏ các cột mặc định bằng cách loại trừ chúng khỏi`Columns` bộ sưu tập hoặc đặt chiều rộng của chúng thành 0.

### Câu hỏi 5: Aspose.Tasks có hỗ trợ xuất dự án sang các định dạng khác ngoài bảng tính có cột tùy chỉnh không?

Câu trả lời 5: Có, Aspose.Tasks hỗ trợ xuất dự án sang nhiều định dạng khác nhau như PDF, HTML và XML, cho phép có các tùy chọn báo cáo dự án linh hoạt.