---
title: Nắm vững các chế độ xem sử dụng tác vụ trong Aspose.Tasks cho .NET
linktitle: Định cấu hình Chế độ xem sử dụng tác vụ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá Aspose.Tasks cho .NET và tìm hiểu cách định cấu hình chế độ xem sử dụng tác vụ. Tùy chỉnh cài đặt thang thời gian và nâng cao hình ảnh quản lý dự án của bạn.
type: docs
weight: 24
url: /vi/net/task-table-management/task-usage-views/
---
## Giới thiệu
Trong lĩnh vực quản lý dự án, việc trực quan hóa việc sử dụng nhiệm vụ là yếu tố then chốt để lập kế hoạch và thực hiện hiệu quả. Aspose.Tasks for .NET cung cấp một giải pháp mạnh mẽ để hiển thị các chế độ xem sử dụng tác vụ, cho phép bạn tùy chỉnh cài đặt thang thời gian và định dạng trình bày. Trong hướng dẫn này, chúng ta sẽ thực hiện các bước để định cấu hình chế độ xem sử dụng tác vụ bằng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET: Đảm bảo rằng bạn đã tích hợp thư viện Aspose.Tasks vào dự án .NET của mình. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/net/).
2. Môi trường .NET: Cài đặt môi trường .NET đang hoạt động trên máy của bạn.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy nhập các vùng tên cần thiết để truy cập các chức năng của Aspose.Tasks. Thêm các dòng sau vào mã của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Bước 1: Đặt đường dẫn thư mục tài liệu
 Trước khi làm việc với các chức năng Aspose.Tasks, hãy đặt đường dẫn đến thư mục tài liệu của bạn. Thay thế`"Your Document Directory"` với đường dẫn thực tế.
```csharp
String DataDir = "Your Document Directory";
```
## Bước 2: Tải dự án
 Khởi tạo Aspose.Tasks`Project` đối tượng bằng cách tải tệp dự án của bạn (ví dụ: TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Bước 3: Xác định tùy chọn lưu
 Tạo một`SaveOptions`đối tượng để chỉ định các tùy chọn hiển thị. Đặt khoảng thời gian thành 'Ngày' và định dạng bản trình bày thành 'TaskUsage'.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Bước 4: Lưu với Thang thời gian ngày
Lưu dự án với cài đặt khoảng thời gian được xác định trước là 'Ngày'.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Bước 5: Lưu với Khoảng thời gian ThirdsOfMonths
Thay đổi cài đặt thang thời gian thành 'ThirdsOfMonths' và lưu dự án.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Bước 6: Lưu theo thang thời gian theo tháng
Đặt khoảng thời gian thành 'Tháng' và lưu dự án với cài đặt đã cập nhật.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Phần kết luận
Định cấu hình chế độ xem sử dụng tác vụ bằng Aspose.Tasks cho .NET là một quá trình đơn giản. Bằng cách tùy chỉnh cài đặt thang thời gian, bạn có thể điều chỉnh trực quan hóa các nhiệm vụ dự án theo nhu cầu cụ thể của mình.
 Hãy thoải mái khám phá thêm các tính năng và chức năng trong[tài liệu](https://reference.aspose.com/tasks/net/).
## Các câu hỏi thường gặp
### Tôi có thể tùy chỉnh khoảng thời gian ngoài các cài đặt được xác định trước không?
Có, bạn có thể đặt khoảng thời gian tùy chỉnh bằng cách chỉ định các khoảng thời gian và đơn vị.
### Có sẵn các định dạng trình bày khác không?
Aspose.Tasks hỗ trợ nhiều định dạng trình bày khác nhau, bao gồm GanttChart, ResourceUsage, v.v.
### Aspose.Tasks có tương thích với các định dạng tệp dự án khác nhau không?
Có, Aspose.Tasks hỗ trợ các định dạng tệp dự án phổ biến như MPP, XML và CSV.
### Tôi có thể áp dụng các cài đặt thang thời gian khác nhau cho các tác vụ cụ thể không?
Hoàn toàn có thể, bạn có thể tùy chỉnh cài đặt thang thời gian cho từng tác vụ trong dự án của mình.
### Làm cách nào tôi có thể nhận được hỗ trợ hoặc tìm kiếm trợ giúp cho Aspose.Tasks?
 Tham quan[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được cộng đồng hỗ trợ và hướng dẫn.