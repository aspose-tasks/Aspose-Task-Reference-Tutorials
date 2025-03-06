---
title: Làm chủ dữ liệu dự án với Aspose.Tasks
linktitle: Làm việc với Dữ liệu dự án trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thao tác dữ liệu Microsoft Project bằng Aspose.Tasks trong .NET. Tạo nhiệm vụ, thêm tài nguyên và lưu dự án một cách dễ dàng.
weight: 16
url: /vi/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Làm chủ dữ liệu dự án với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với dữ liệu Microsoft Project bằng thư viện Aspose.Tasks cho .NET. Aspose.Tasks cung cấp các tính năng mạnh mẽ để thao tác với tệp dự án, bao gồm tạo tác vụ, thêm tài nguyên, đặt thuộc tính và lưu dự án ở nhiều định dạng khác nhau.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Cài đặt Thư viện Aspose.Tasks: Tải xuống và cài đặt thư viện Aspose.Tasks từ[đây](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET.
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.

## Nhập không gian tên
Trước khi làm việc với Aspose.Tasks, hãy nhập các không gian tên cần thiết vào dự án của bạn:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Bước 1: Khởi tạo đối tượng dự án
```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Dòng này khởi tạo một phiên bản mới của`Project` class, đại diện cho tệp Microsoft Project.
## Bước 2: Đặt thuộc tính dự án
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Những dòng này trình bày cách thiết lập các thuộc tính của dự án như định dạng công việc và chế độ tạo tác vụ.
## Bước 3: Thêm nhiệm vụ
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Tại đây, một tác vụ mới có tên "Nhiệm vụ 1" được thêm vào tác vụ gốc của dự án.
## Bước 4: Đặt thuộc tính tác vụ
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Những dòng này đặt ngày bắt đầu, thời lượng và ngày kết thúc cho "Nhiệm vụ 1".
## Bước 5: Thêm tài nguyên
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Phần này trình bày cách thêm tài nguyên công việc vào dự án.
## Bước 6: Gán tài nguyên cho nhiệm vụ
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Những dòng này hiển thị cách gán tài nguyên công việc đã thêm trước đó cho "Nhiệm vụ 1" với ngày bắt đầu, ngày làm việc và ngày kết thúc cụ thể.
## Bước 7: Lưu dự án
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Cuối cùng, dự án được lưu ở định dạng tệp Microsoft Project XML.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách làm việc với dữ liệu Microsoft Project bằng thư viện Aspose.Tasks trong .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể thao tác với các tệp dự án, thêm nhiệm vụ, tài nguyên, gán tài nguyên cho nhiệm vụ và lưu dự án ở nhiều định dạng khác nhau.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có thể xử lý các cấu trúc dự án phức tạp không?
Trả lời: Có, Aspose.Tasks cung cấp hỗ trợ toàn diện cho các cấu trúc dự án phức tạp, cho phép bạn quản lý các nhiệm vụ, tài nguyên và nhiệm vụ một cách hiệu quả.
### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của Microsoft Project không?
Trả lời: Aspose.Tasks hỗ trợ nhiều phiên bản Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Câu hỏi: Tôi có thể tích hợp Aspose.Tasks với các thư viện .NET khác không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks tích hợp liền mạch với các thư viện .NET khác, mang lại sự linh hoạt trong các dự án phát triển của bạn.
### Câu hỏi: Aspose.Tasks có hỗ trợ các thuật toán lập lịch dự án không?
Trả lời: Có, Aspose.Tasks bao gồm các thuật toán lập lịch nâng cao để giúp bạn tối ưu hóa tiến trình dự án và việc sử dụng tài nguyên.
### Câu hỏi: Có diễn đàn cộng đồng nào dành cho người dùng Aspose.Tasks không?
 Trả lời: Có, bạn có thể tìm thấy các tài nguyên hữu ích và tương tác với những người dùng Aspose.Tasks khác trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
