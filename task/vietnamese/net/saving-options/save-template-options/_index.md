---
title: Lưu tệp dự án MS dưới dạng mẫu với Aspose.Tasks
linktitle: Lưu tùy chọn mẫu cho Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách lưu tệp Microsoft Project dưới dạng mẫu bằng Aspose.Tasks cho .NET. Tùy chỉnh cài đặt mẫu để quản lý dự án hợp lý.
type: docs
weight: 18
url: /vi/net/saving-options/save-template-options/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ hướng dẫn quy trình lưu mẫu bằng Aspose.Tasks cho .NET. Các mẫu rất hữu ích cho việc chuẩn hóa cấu trúc và cài đặt dự án để sử dụng trong tương lai. Chúng tôi sẽ trình bày cách lưu dự án dưới dạng mẫu, đồng thời điều chỉnh các thuộc tính của dự án trong quá trình thực hiện.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET Library: Đảm bảo bạn đã cài đặt thư viện Aspose.Tasks for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
2. Kiến thức về lập trình C#: Cần có kiến thức cơ bản về lập trình C# để hiểu và triển khai các đoạn mã được cung cấp.
3. Tệp dự án Microsoft: Chuẩn bị sẵn tệp Microsoft Project (định dạng MPP) mà bạn muốn lưu làm mẫu.

## Nhập không gian tên
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Bước 1: Tải dự án
Trước tiên, chúng ta cần tải tệp Microsoft Project (.mpp) mà chúng ta muốn lưu làm mẫu.
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Bước 2: Nhận thông tin tệp dự án
Truy xuất thông tin về tệp dự án đã tải, chẳng hạn như định dạng của nó.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Bước 3: Định cấu hình tùy chọn lưu mẫu
Tạo các tùy chọn lưu mẫu và định cấu hình các thuộc tính của nó theo yêu cầu của bạn. Các tùy chọn này cho phép bạn tùy chỉnh dữ liệu nào sẽ bị xóa khỏi mẫu.
```csharp
var options = new SaveTemplateOptions
{
	// Xóa tất cả chi phí cố định khỏi mẫu dự án
	RemoveFixedCosts = true,
	// Xóa tất cả các giá trị thực tế khỏi mẫu dự án
	RemoveActualValues = true,
	// Xóa tỷ lệ tài nguyên khỏi mẫu dự án
	RemoveResourceRates = true,
	// Xóa tất cả các giá trị cơ sở khỏi mẫu dự án
	RemoveBaselineValues = true
};
```
## Bước 4: Lưu dự án dưới dạng mẫu
Lưu dự án dưới dạng mẫu với các tùy chọn đã chỉ định.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Bước 5: Nhận thông tin tệp mẫu
Truy xuất thông tin về tệp mẫu đã lưu, chẳng hạn như định dạng của nó.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Chúc mừng! Bạn đã lưu thành công mẫu bằng Aspose.Tasks cho .NET, tùy chỉnh các thuộc tính của nó nếu cần.

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá cách lưu tệp Microsoft Project dưới dạng mẫu bằng cách sử dụng Aspose.Tasks cho .NET. Các mẫu có giá trị để chuẩn hóa cấu trúc và cài đặt dự án, hợp lý hóa việc tạo dự án trong tương lai.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tùy chỉnh dữ liệu nào cần xóa khỏi mẫu không?
Trả lời: Có, bạn có thể định cấu hình Tùy chọn Lưu Mẫu để xóa dữ liệu cụ thể như chi phí cố định, giá trị thực tế, tỷ lệ tài nguyên và giá trị cơ sở.
### Câu hỏi: Aspose.Tasks dành cho .NET có tương thích với tất cả các phiên bản Microsoft Project không?
Trả lời: Aspose.Tasks cho .NET cung cấp khả năng tương thích rộng rãi với nhiều phiên bản khác nhau của Microsoft Project, đảm bảo chức năng và tích hợp liền mạch.
### Hỏi: Tôi có thể áp dụng mẫu cho các dự án hiện có không?
Trả lời: Có, bạn có thể áp dụng mẫu cho các dự án hiện có bằng cách tải tệp mẫu và hợp nhất nó với dự án hiện tại của bạn nếu cần.
### Câu hỏi: Aspose.Tasks cho .NET có hỗ trợ phát triển đa nền tảng không?
Trả lời: Aspose.Tasks for .NET được thiết kế chủ yếu cho các ứng dụng .NET framework chạy trên nền tảng Windows.
### Câu hỏi: Aspose.Tasks dành cho .NET có hỗ trợ kỹ thuật không?
 Trả lời: Có, bạn có thể tìm kiếm sự hỗ trợ và hướng dẫn kỹ thuật từ cộng đồng Aspose.Tasks[diễn đàn](https://forum.aspose.com/c/tasks/15)hoặc liên hệ trực tiếp với nhóm hỗ trợ của họ.