---
title: Cấu hình mã WBS từng bước trong Aspose.Tasks .NET
linktitle: Định cấu hình Mặt nạ mã WBS trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá cấu hình Mặt nạ mã WBS từng bước trong các dự án .NET bằng Aspose.Tasks. Nâng cao khả năng quản lý dự án một cách dễ dàng.
weight: 14
url: /vi/net/view-wbs-code-configuration/wbs-code-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cấu hình mã WBS từng bước trong Aspose.Tasks .NET

## Giới thiệu
Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác hiệu quả dữ liệu quản lý dự án trong các ứng dụng .NET. Trong hướng dẫn này, chúng ta sẽ khám phá quy trình định cấu hình Mặt nạ mã cấu trúc phân chia công việc (WBS) bằng cách sử dụng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện từ[Aspose.Tasks cho Tài liệu .NET](https://reference.aspose.com/tasks/net/).
- Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET đang hoạt động.
- Thư mục tài liệu: Chọn một thư mục trên hệ thống của bạn để lưu trữ các tệp dự án.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy bao gồm các vùng tên cần thiết để làm việc với Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Bước 1: Tạo một phiên bản dự án
Bắt đầu bằng cách tạo một phiên bản dự án mới:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Bước 2: Xác định định nghĩa mã WBS
Thiết lập Định nghĩa mã WBS cho dự án của bạn:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Bước 3: Thêm mặt nạ mã WBS
Xác định Mặt nạ mã WBS và thêm chúng vào dự án:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Bước 4: Tạo nhiệm vụ
Thêm nhiệm vụ vào dự án:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Bước 5: Tính toán lại
Tính toán lại dự án để đảm bảo mã WBS được áp dụng chính xác:
```csharp
project.Recalculate();
```
## Bước 6: Hiển thị thông tin mặt nạ WBS
Xuất thông tin về mặt nạ WBS ra bảng điều khiển:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Bước 7: Lưu dự án
Lưu dự án với mã WBS đã thêm:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Chúc mừng! Bạn đã định cấu hình thành công Mặt nạ mã WBS trong dự án Aspose.Tasks của mình.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá quy trình từng bước định cấu hình Mặt nạ mã WBS bằng Aspose.Tasks cho .NET. Thư viện mạnh mẽ này cung cấp cho các nhà phát triển một cách liền mạch để nâng cao khả năng quản lý dự án trong các ứng dụng .NET của họ.

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks miễn phí không?
 Aspose.Tasks cung cấp bản dùng thử miễn phí mà bạn có thể tải xuống[đây](https://releases.aspose.com/).
### Tôi có thể tìm thêm hỗ trợ ở đâu?
 Tham quan[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để hỗ trợ cộng đồng.
### Làm thế nào tôi có thể có được giấy phép tạm thời?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Có tài liệu chi tiết có sẵn?
 Có, tài liệu đầy đủ có sẵn[đây](https://reference.aspose.com/tasks/net/).
### Tôi có thể mua Aspose.Tasks ở đâu?
 Mua Aspose.Tasks[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
