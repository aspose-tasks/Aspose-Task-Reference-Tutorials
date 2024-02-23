---
title: Định cấu hình các bậc thang thời gian của biểu đồ Gantt trong Aspose.Tasks
linktitle: Định cấu hình các bậc thang thời gian trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá Aspose.Tasks for .NET để định cấu hình các bậc thời gian trong chế độ xem Biểu đồ Gantt của bạn để trực quan hóa dòng thời gian dự án chính xác. #Aspose.Tasks #MS Project
type: docs
weight: 16
url: /vi/net/text-view-configuration/timescale-tiers/
---
## Giới thiệu
Trong bối cảnh năng động của quản lý dự án, việc hình dung hiệu quả là rất quan trọng để hiểu được các mốc thời gian và thời hạn. Aspose.Tasks cho .NET cung cấp một bộ công cụ mạnh mẽ và trong hướng dẫn này, chúng ta sẽ khám phá cách định cấu hình các bậc thang thời gian để thể hiện tối ưu trong chế độ xem Biểu đồ Gantt. Hãy làm theo các hướng dẫn từng bước này để nâng cao khả năng trực quan hóa dự án của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
- Kiến thức cơ bản về C# và .NET.
- Aspose.Tasks cho thư viện .NET đã được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/net/).
- Một môi trường phát triển được thiết lập để phát triển ứng dụng .NET.
## Nhập không gian tên
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Bây giờ, hãy chia nhỏ từng bước của ví dụ được cung cấp.
## Bước 1: Khởi tạo dự án và thêm liên kết tác vụ
```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Tại đây, chúng tôi tạo một dự án và thiết lập các liên kết nhiệm vụ giữa "Nhiệm vụ 1" và "Nhiệm vụ 2".
## Bước 2: Định cấu hình Chế độ xem biểu đồ Gantt
```csharp
var view = (GanttChartView)project.DefaultView;
```
Truy cập chế độ xem Biểu đồ Gantt để tùy chỉnh.
## Bước 3: Điều chỉnh cấp độ thời gian trung bình
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Tùy chỉnh bậc thời gian ở giữa để hiển thị các tuần với nhãn và căn chỉnh cụ thể.
## Bước 4: Thêm bậc thang thời gian hàng đầu
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Thêm cấp độ thời gian cao nhất để biểu thị tháng.
## Bước 5: Tùy chỉnh ngày cấp trung
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Cá nhân hóa nhãn tháng để hiển thị tốt hơn.
## Bước 6: Đặt thời gian dự án
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Xác định khoảng thời gian của dự án để kiểm soát dòng thời gian tổng thể.
## Bước 7: Lưu dự án với khoảng thời gian tùy chỉnh
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Lưu dự án với các cài đặt khoảng thời gian đã xác định.
## Phần kết luận
Tóm lại, việc định cấu hình các bậc thời gian trong Aspose.Tasks cho .NET cho phép trình bày các mốc thời gian của dự án phù hợp hơn và trực quan hơn. Các bước này cho phép bạn tạo chế độ xem Biểu đồ Gantt đáp ứng chính xác nhu cầu quản lý dự án của bạn.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks với các thư viện .NET khác không?
Có, Aspose.Tasks tích hợp liền mạch với các thư viện .NET khác, mang lại sự linh hoạt trong ngăn xếp phát triển của bạn.
### Giấy phép tạm thời có sẵn cho mục đích thử nghiệm không?
 Có, bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/) để đánh giá.
### Có tùy chọn tùy chỉnh bổ sung nào cho chế độ xem Biểu đồ Gantt không?
Hoàn toàn có thể, Aspose.Tasks cung cấp các tùy chọn tùy chỉnh mở rộng cho chế độ xem Biểu đồ Gantt để phù hợp với các yêu cầu đa dạng của dự án.
### Tôi có thể hiển thị thang thời gian ở các định dạng khác nhau không?
Chắc chắn, bạn có thể khám phá nhiều định dạng và phong cách khác nhau để biểu diễn thang thời gian sao cho phù hợp nhất với bối cảnh dự án của bạn.
### Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks không?
 Vâng, hãy ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được cộng đồng hỗ trợ và thảo luận.