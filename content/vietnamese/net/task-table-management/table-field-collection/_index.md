---
title: Làm chủ các bộ sưu tập trường bảng trong Aspose.Tasks cho .NET
linktitle: Bộ sưu tập các trường bảng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá thế giới năng động của quản lý dự án với Aspose.Tasks for .NET. Tìm hiểu cách thao tác các bộ sưu tập trường bảng để có trải nghiệm dự án tùy chỉnh.
type: docs
weight: 13
url: /vi/net/task-table-management/table-field-collection/
---
## Giới thiệu
Aspose.Tasks for .NET là một thư viện mạnh mẽ hỗ trợ quản lý dự án bằng cách cung cấp chức năng mở rộng để làm việc với các tệp Microsoft Project. Trong hướng dẫn này, chúng ta sẽ đi sâu vào bộ sưu tập các trường bảng trong Aspose.Tasks, khám phá cách thao tác và quản lý chúng một cách hiệu quả bằng C#.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã thiết lập sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#.
- Aspose.Tasks cho thư viện .NET đã được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/net/).
- Môi trường phát triển tích hợp (IDE) như Visual Studio.
## Nhập không gian tên
Trước tiên, hãy đảm bảo rằng bạn đã nhập các không gian tên cần thiết ở đầu tệp C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Bây giờ, hãy chia mỗi ví dụ thành nhiều bước theo định dạng hướng dẫn từng bước.
## Bước 1: Đặt thư mục tài liệu
Đặt đường dẫn đến thư mục tài liệu nơi chứa tệp Dự án của bạn.
```csharp
String DataDir = "Your Document Directory";
```
## Bước 2: Tải tệp dự án
Tải tệp dự án bằng thư viện Aspose.Tasks.
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## Bước 3: Lặp lại các trường của bảng
Lặp lại các trường bảng trong dự án.
```csharp
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Table name: " + tbl.Name);
    Console.WriteLine("Is collection of table fields read-only?: " + tbl.TableFields.IsReadOnly);
    // lặp qua các trường bảng
    Console.WriteLine("Print table fields of " + project.Get(Prj.Name) + " project.");
    Console.WriteLine("Table count: " + tbl.TableFields.Count);
    foreach (var fld in tbl.TableFields)
    {
        Console.WriteLine("Field Title: " + fld.Title);
        Console.WriteLine("Field Field: " + fld.Field);
        Console.WriteLine();
    }
}
```
## Bước 4: Thêm trường bảng mới
Thêm trường bảng mới vào bảng hiện có.
```csharp
var table = project.Tables.ToList()[0];
var field = new TableField();
field.Title = "New Table Field";
table.TableFields.Add(field);
```
## Bước 5: Chèn trường mới
Chèn một trường mới vào một vị trí cụ thể trong bảng.
```csharp
var field2 = new TableField();
field2.Title = "New Table Field 2";
var idx = table.TableFields.IndexOf(field);
table.TableFields.Insert(idx, field2);
```
## Bước 6: Chỉnh sửa trường bảng mới
Chỉnh sửa trường bảng mới được thêm bằng cách sử dụng quyền truy cập chỉ mục.
```csharp
table.TableFields[idx].WrapHeader = true;
```
## Bước 7: Xóa trường
Xóa từng trường trong bảng hoặc xóa toàn bộ bộ sưu tập.
```csharp
Console.WriteLine("The collection contains the new table field?: " + table.TableFields.Contains(field));
// Xóa trường
table.TableFields.RemoveAt(idx);
```
## Bước 8: Xóa bộ sưu tập
Xóa bộ sưu tập trường bảng từng cái một hoặc hoàn toàn.
```csharp
if (deleteOneByOne)
{
    // Loại bỏ từng cái một
    var tableFields = new TableField[table.TableFields.Count];
    table.TableFields.CopyTo(tableFields, 0);
    foreach (var fld in tableFields)
    {
        table.TableFields.Remove(fld);
    }
}
else
{
    // Xóa bộ sưu tập hoàn toàn
    table.TableFields.Clear();
}
```
Bây giờ bạn đã khám phá thành công bộ sưu tập các trường bảng trong Aspose.Tasks cho .NET, cho phép bạn quản lý và thao tác chúng theo yêu cầu dự án của mình.
## Phần kết luận
Tóm lại, việc hiểu cách làm việc với các bộ sưu tập trường bảng trong Aspose.Tasks cho .NET sẽ mở ra khả năng tùy chỉnh và quản lý dự án hiệu quả. Với tính linh hoạt do Aspose.Tasks cung cấp, các nhà phát triển có thể điều chỉnh ứng dụng của mình để đáp ứng các nhu cầu dự án cụ thể một cách liền mạch.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho .NET với bất kỳ phiên bản nào của tệp Microsoft Project không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, đảm bảo tính tương thích và tính linh hoạt.
### Có thể tạo và sửa đổi các trường bảng một cách linh hoạt trong thời gian chạy không?
Tuyệt đối! Như được hiển thị trong hướng dẫn, bạn có thể thêm, chèn, chỉnh sửa và xóa các trường bảng một cách linh hoạt nếu cần.
### Có bất kỳ cân nhắc cấp phép nào khi sử dụng Aspose.Tasks cho .NET trong một dự án thương mại không?
 Có, bạn cần có giấy phép hợp lệ để sử dụng Aspose.Tasks cho .NET trong một dự án thương mại. Bạn có thể có được giấy phép[đây](https://purchase.aspose.com/buy).
### Làm cách nào tôi có thể nhận được hỗ trợ hoặc tìm kiếm trợ giúp với Aspose.Tasks cho .NET?
 tham quan[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ, đặt câu hỏi và cộng tác với cộng đồng.
### Có bản dùng thử miễn phí dành cho Aspose.Tasks cho .NET không?
 Có, bạn có thể khám phá các tính năng của Aspose.Tasks for .NET bằng bản dùng thử miễn phí. Tải xuống[đây](https://releases.aspose.com/).