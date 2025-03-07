---
title: Thao tác tiêu chí nhóm dự án MS trong Aspose.Tasks
linktitle: Tiêu chí nhóm trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá cách thao tác các tệp MS Project theo chương trình trong .NET bằng Aspose.Tasks. Lấy ví dụ từng bước về nhóm nhiệm vụ và tiêu chí.
weight: 27
url: /vi/net/tasks-project-management/group-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thao tác tiêu chí nhóm dự án MS trong Aspose.Tasks

## Giới thiệu
Aspose.Tasks for .NET là một API mạnh mẽ hỗ trợ làm việc với các tệp Microsoft Project trong các ứng dụng .NET của bạn. Cho dù bạn đang phát triển phần mềm quản lý dự án hay cần thao tác dữ liệu dự án theo chương trình, Aspose.Tasks đều cung cấp một bộ tính năng toàn diện để đáp ứng nhu cầu của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
### 1. Kiến thức về C# và .NET Framework
Cần phải làm quen với ngôn ngữ lập trình C# và .NET Framework để hiểu và triển khai các ví dụ được cung cấp trong hướng dẫn này.
### 2. Cài đặt Aspose.Tasks cho .NET
 Đảm bảo bạn đã cài đặt Aspose.Tasks for .NET trong môi trường phát triển của mình. Bạn có thể tải thư viện từ[đây](https://releases.aspose.com/tasks/net/) và làm theo hướng dẫn cài đặt được cung cấp.
### 3. Môi trường phát triển tích hợp (IDE)
Hãy cài đặt một IDE như Visual Studio trên hệ thống của bạn để viết và thực thi mã C#.

## Nhập không gian tên
Để bắt đầu, hãy nhập các vùng tên cần thiết trong mã C# của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Bước 1: Tải tệp dự án Microsoft
Đầu tiên, chỉ định đường dẫn đến tệp Microsoft Project của bạn:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Thay thế`"Your Document Directory"` với đường dẫn đến tệp dự án của bạn.
## Bước 2: Truy xuất thông tin nhóm nhiệm vụ
Tiếp theo, lấy thông tin về các nhóm nhiệm vụ trong dự án:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Đoạn mã này in tổng số nhóm nhiệm vụ, truy xuất nhóm nhiệm vụ thứ hai, tên của nhóm và số lượng tiêu chí mà nhóm đó nắm giữ.
## Bước 3: Truy xuất thông tin tiêu chí của nhóm nhiệm vụ
Bây giờ, hãy đi sâu vào chi tiết về một tiêu chí cụ thể trong nhóm nhiệm vụ:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Phân đoạn này hiển thị các thuộc tính khác nhau của tiêu chí như chỉ mục, trường, thông tin nhóm, màu ô, màu phông chữ, khoảng cách nhóm và điểm bắt đầu.
## Bước 4: Truy xuất thông tin phông chữ của tiêu chí
Cuối cùng, lấy thông tin chi tiết liên quan đến phông chữ của tiêu chí:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Bước này in ra tên phông chữ, kích thước, kiểu dáng và liệu tiêu chí được sắp xếp theo thứ tự tăng dần hay giảm dần.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách sử dụng Aspose.Tasks cho .NET để truy xuất thông tin về các nhóm nhiệm vụ và tiêu chí từ tệp Microsoft Project. Bằng cách làm theo hướng dẫn từng bước, bạn có thể làm việc hiệu quả với dữ liệu dự án theo chương trình trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Aspose.Tasks có thể xử lý các tệp Microsoft Project lớn không?
Aspose.Tasks được tối ưu hóa để xử lý các tệp dự án lớn một cách hiệu quả, đảm bảo hiệu suất và độ tin cậy cao.
### Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích trên các định dạng tệp khác nhau.
### Tôi có thể thao tác dữ liệu dự án bằng Aspose.Tasks không?
Hoàn toàn có thể, Aspose.Tasks cung cấp các chức năng mở rộng để thao tác dữ liệu dự án, bao gồm các nhiệm vụ, tài nguyên, lịch, v.v.
### Aspose.Tasks có cung cấp hỗ trợ cho các nền tảng .NET khác nhau không?
Có, Aspose.Tasks hỗ trợ nhiều nền tảng .NET bao gồm .NET Framework, .NET Core và .NET Standard.
### Có diễn đàn cộng đồng nào dành cho Aspose.Tasks để tôi có thể tìm kiếm sự trợ giúp không?
 Có, bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi, chia sẻ kiến thức và cộng tác với những người dùng khác.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
