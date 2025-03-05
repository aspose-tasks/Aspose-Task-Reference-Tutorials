---
title: Làm chủ các chế độ xem biểu đồ Gantt trong Aspose.Tasks
linktitle: Lượt xem biểu đồ Gantt trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách tùy chỉnh chế độ xem biểu đồ Gantt trong tệp Microsoft Project bằng Aspose.Tasks cho .NET. Hướng dẫn từng bước để quản lý dự án hiệu quả.
type: docs
weight: 22
url: /vi/net/tasks-project-management/gantt-chart-views/
---
## Giới thiệu
Biểu đồ Gantt là công cụ mạnh mẽ được sử dụng trong quản lý dự án để trực quan hóa các nhiệm vụ, mốc thời gian và mối quan hệ phụ thuộc. Aspose.Tasks for .NET cung cấp các khả năng mạnh mẽ để làm việc với các chế độ xem biểu đồ Gantt trong các tệp Microsoft Project. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Aspose.Tasks để thao tác với các chế độ xem biểu đồ Gantt, tùy chỉnh giao diện của chúng và lưu chúng dưới dạng tệp PDF.
## Điều kiện tiên quyết
Trước khi tiếp tục, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### 1. Cài đặt Aspose.Tasks cho .NET
 Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET. Bạn có thể tải thư viện từ[đây](https://releases.aspose.com/tasks/net/) và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu[đây](https://reference.aspose.com/tasks/net/).
### 2. Tệp dự án Microsoft
Chuẩn bị tệp Microsoft Project (`Project2.mpp`) mà bạn sẽ sử dụng để làm việc với các dạng xem biểu đồ Gantt.
### 3. Kiến thức cơ bản về C# và .NET Framework
Hướng dẫn này giả sử bạn có hiểu biết cơ bản về ngôn ngữ lập trình C# và .NET framework.
## Nhập không gian tên
Trước khi bắt đầu làm việc với các chế độ xem biểu đồ Gantt trong Aspose.Tasks, bạn cần nhập các vùng tên cần thiết vào mã C# của mình. Đây là cách bạn có thể làm điều đó:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Hãy chia mã ví dụ được cung cấp thành nhiều bước và giải thích chi tiết từng bước:
## Bước 1: Tải tệp dự án
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Bước này liên quan đến việc tải tệp Microsoft Project (`Project2.mpp` ) vào một thể hiện của`Project` lớp học.
## Bước 2: Đặt ngày trạng thái
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Ở đây, chúng tôi đặt ngày trạng thái của dự án thành ngày bắt đầu.
## Bước 3: Truy cập Chế độ xem biểu đồ Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Chúng tôi truy cập chế độ xem biểu đồ Gantt từ dự án. Aspose.Tasks cho phép truy cập các chế độ xem như Biểu đồ Gantt, Sơ đồ mạng và Cách sử dụng tác vụ.
## Bước 4: Tùy chỉnh chế độ xem biểu đồ Gantt
Bây giờ, hãy tùy chỉnh các khía cạnh khác nhau của chế độ xem biểu đồ Gantt:
### Đặt làm tròn thanh
```csharp
view.BarRounding = false;
```
Điều này đặt xem các thanh trên biểu đồ Gantt có làm tròn đến ngày gần nhất hay không.
### Đặt kích thước thanh
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Điều này xác định chiều cao của thanh Gantt trong biểu đồ.
### Ẩn thanh cuộn
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Chỉ định xem thanh tổng số có bị ẩn khi mở rộng tác vụ tóm tắt hay không.
### Đặt màu thời gian không làm việc
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Xác định màu cho thời gian không làm việc trên biểu đồ Gantt.
### Thanh cuộn Gantt
```csharp
view.RollUpGanttBars = true;
```
Chỉ định xem các thanh trên biểu đồ Gantt có phải được cuộn lên hay không.
### Hiển thị phần tách thanh
```csharp
view.ShowBarSplits = true;
```
Xác định xem có phải hiển thị các phần phân chia nhiệm vụ trên biểu đồ Gantt hay không.
### Hiển thị bản vẽ
```csharp
view.ShowDrawings = true;
```
Chỉ định xem có phải hiển thị các bản vẽ trên biểu đồ Gantt hay không.
### Tỷ lệ phần trăm kích thước thang thời gian
```csharp
view.TimescaleSizePercentage = 10;
```
Đặt tỷ lệ phần trăm để điều chỉnh khoảng cách giữa các đơn vị trên bậc thời gian.
## Bước 5: Lưu dạng xem biểu đồ Gantt dưới dạng PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Cuối cùng, chúng tôi lưu chế độ xem biểu đồ Gantt tùy chỉnh dưới dạng tệp PDF.
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách làm việc với các chế độ xem biểu đồ Gantt trong Aspose.Tasks dành cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể thao tác và tùy chỉnh biểu đồ Gantt một cách hiệu quả theo yêu cầu dự án của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tùy chỉnh thêm hình thức của thanh biểu đồ Gantt không?
Trả lời: Có, Aspose.Tasks cung cấp các tùy chọn mở rộng để tùy chỉnh giao diện của thanh biểu đồ Gantt, bao gồm màu sắc, hình dạng và kích thước.
### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.
### Câu hỏi: Tôi có thể xuất các dạng xem biểu đồ Gantt sang các định dạng khác ngoài PDF không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks hỗ trợ xuất chế độ xem biểu đồ Gantt sang nhiều định dạng, bao gồm PNG, JPEG và XPS.
### Câu hỏi: Aspose.Tasks có hỗ trợ các thuật toán lập kế hoạch dự án phức tạp không?
Trả lời: Có, Aspose.Tasks cung cấp các thuật toán lập lịch nâng cao để xử lý lịch trình dự án phức tạp một cách hiệu quả.
### Câu hỏi: Có diễn đàn cộng đồng nào để tôi có thể tìm kiếm trợ giúp hoặc chia sẻ trải nghiệm của mình với Aspose.Tasks không?
 Đ: Có, bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để tương tác với những người dùng khác, đặt câu hỏi và tìm giải pháp cho các truy vấn của bạn.