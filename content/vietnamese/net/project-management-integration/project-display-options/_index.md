---
title: Định cấu hình tùy chọn hiển thị dự án MS trong Aspose.Tasks
linktitle: Định cấu hình tùy chọn hiển thị dự án trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách định cấu hình các tùy chọn hiển thị MS Project theo chương trình bằng cách sử dụng Aspose.Tasks cho .NET. Tùy chỉnh giao diện dự án của bạn một cách dễ dàng.
type: docs
weight: 17
url: /vi/net/project-management-integration/project-display-options/
---
## Giới thiệu
Microsoft Project cung cấp rất nhiều tùy chọn hiển thị để tùy chỉnh giao diện dự án của bạn. Aspose.Tasks for .NET cung cấp một khung mạnh mẽ để thao tác các tùy chọn này theo chương trình. Trong hướng dẫn này, chúng ta sẽ khám phá cách định cấu hình các tùy chọn hiển thị MS Project bằng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
1.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện từ[đây](https://releases.aspose.com/tasks/net/).
2. Tệp dự án Microsoft: Chuẩn bị sẵn tệp MS Project (.mpp) hợp lệ để áp dụng các tùy chọn hiển thị.
3. Kiến thức cơ bản về C#: Cần phải làm quen với ngôn ngữ lập trình C#.

## Nhập không gian tên
Trước tiên, hãy đảm bảo nhập các không gian tên cần thiết vào mã C# của bạn:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Bước 1: Tải tệp dự án
 Tải tệp MS Project bằng cách sử dụng`Project` lớp được cung cấp bởi Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Bước 2: Định cấu hình tùy chọn hiển thị
Bây giờ, hãy định cấu hình các tùy chọn hiển thị khác nhau có sẵn trong MS Project:
### Tắt cảnh báo lịch trình nhiệm vụ
Để tắt cảnh báo về xung đột lịch trình với các tác vụ được lên lịch thủ công (có sẵn cho Project 2010 trở lên):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Thêm dấu cách trước nhãn
Đặt thêm dấu cách trước giá trị số và chữ viết tắt thời gian:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Định cấu hình hiển thị nhãn cho đơn vị thời gian
Tùy chỉnh cách hiển thị các đơn vị thời gian khác nhau:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Hiển thị nhiệm vụ tóm tắt dự án
Hiển thị thông tin tóm tắt về toàn bộ dự án trên một hàng:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Bật đề xuất lịch trình nhiệm vụ
Cho phép hiển thị gợi ý xung đột lịch trình với các tác vụ được lên lịch thủ công:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Gạch chân các siêu liên kết
Đặt để gạch chân các siêu liên kết trong dự án:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Bước 3: Lưu dự án
Cuối cùng, lưu dự án với các tùy chọn hiển thị được áp dụng:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách định cấu hình các tùy chọn hiển thị MS Project bằng Aspose.Tasks cho .NET. Với những khả năng này, bạn có thể tùy chỉnh giao diện của tệp dự án một cách hiệu quả theo chương trình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể chỉ áp dụng các tùy chọn hiển thị này cho các tác vụ cụ thể không?
Trả lời: Có, bạn có thể áp dụng có chọn lọc các tùy chọn hiển thị cho từng tác vụ riêng lẻ bằng API Aspose.Tasks.
### Câu hỏi: Các tùy chọn hiển thị này có ảnh hưởng đến dữ liệu dự án cơ bản không?
Trả lời: Không, các tùy chọn này chỉ sửa đổi cách trình bày trực quan của dự án và không thay đổi dữ liệu cơ bản.
### Câu hỏi: Các tùy chọn hiển thị này có tương thích với tất cả các phiên bản của Microsoft Project không?
Đáp: Không, một số tùy chọn có thể dành riêng cho một số phiên bản MS Project nhất định. Tham khảo tài liệu để biết chi tiết về khả năng tương thích.
### H: Tôi có thể hoàn nguyên các tùy chọn hiển thị về cài đặt mặc định không?
Trả lời: Có, bạn có thể đặt lại các tùy chọn hiển thị về giá trị mặc định bằng API Aspose.Tasks.
### Câu hỏi: Có bất kỳ hạn chế nào đối với việc tùy chỉnh các tùy chọn hiển thị theo chương trình không?
Trả lời: Mặc dù Aspose.Tasks cung cấp khả năng tùy chỉnh rộng rãi nhưng một số tùy chọn hiển thị nhất định có thể không truy cập được bằng chương trình do những hạn chế trong định dạng tệp MS Project.