---
title: Nắm vững các giá trị phác thảo của dự án MS với Aspose.Tasks
linktitle: Quản lý giá trị phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý các giá trị phác thảo MS Project một cách hiệu quả bằng cách sử dụng Aspose.Tasks cho .NET. Tùy chỉnh phác thảo dự án một cách dễ dàng.
type: docs
weight: 16
url: /vi/net/outline-code-page-settings/outline-values/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý các giá trị phác thảo Microsoft Project bằng thư viện Aspose.Tasks cho .NET. Với Aspose.Tasks, bạn có thể dễ dàng thao tác mã phác thảo, tạo giá trị phác thảo mới và tùy chỉnh phác thảo dự án theo yêu cầu của mình.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Cài đặt Aspose.Tasks cho .NET: Tải xuống và cài đặt thư viện Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển, chẳng hạn như Visual Studio, có khả năng tương thích với .NET framework.
3. Hiểu biết cơ bản về lập trình C#: Làm quen với những điều cơ bản về ngôn ngữ lập trình C#, vì chúng ta sẽ sử dụng C# để làm việc với thư viện Aspose.Tasks.

## Nhập không gian tên
Bắt đầu bằng cách nhập các vùng tên cần thiết vào mã C# của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Bước 1: Tải tệp dự án
```csharp
// Đường dẫn đến thư mục tài liệu.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Bước này khởi tạo một đối tượng Project mới và tải tệp Microsoft Project từ thư mục đã chỉ định.
## Bước 2: Xác định định nghĩa mã phác thảo
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Ở đây, chúng tôi xác định hai đối tượng OutlineCodeDefinition và thêm chúng vào bộ sưu tập OutlineCodes của dự án.
## Bước 3: Xác định mặt nạ phác thảo
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Bước này thiết lập OutlineMask cho định nghĩa mã phác thảo.
## Bước 4: Tạo giá trị phác thảo
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
Trong bước này, chúng ta tạo hai đối tượng OutlineValue và đặt các thuộc tính của chúng như giá trị, ID giá trị, loại, mô tả và trạng thái thu gọn.

## Phần kết luận
Việc quản lý các giá trị phác thảo của MS Project bằng Aspose.Tasks cho .NET rất đơn giản với các chức năng được cung cấp. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể thao tác hiệu quả các mã và giá trị phác thảo để tùy chỉnh phác thảo dự án theo nhu cầu của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các khung .NET khác không?
Trả lời: Có, Aspose.Tasks tương thích với nhiều khung .NET khác nhau, đảm bảo tính linh hoạt trong môi trường phát triển của bạn.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks không?
 Trả lời: Có, bạn có thể truy cập phiên bản dùng thử miễn phí của Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?
 Trả lời: Để được hỗ trợ và trợ giúp, bạn có thể truy cập diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks không?
Đáp: Có, bạn có thể mua giấy phép tạm thời cho Aspose.Tasks từ[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể tìm tài liệu chi tiết về Aspose.Tasks ở đâu?
 A: Bạn có thể tham khảo tài liệu đầy đủ có sẵn[đây](https://reference.aspose.com/tasks/net/).