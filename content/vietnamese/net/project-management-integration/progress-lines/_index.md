---
title: Xử lý dòng tiến độ dự án MS với Aspose.Tasks
linktitle: Xử lý các dòng tiến trình trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thao tác các dòng tiến trình trong tệp MS Project bằng Aspose.Tasks cho .NET, nâng cao khả năng quản lý và trực quan hóa dự án.
type: docs
weight: 15
url: /vi/net/project-management-integration/progress-lines/
---
## Giới thiệu
Microsoft Project (MS Project) là một công cụ mạnh mẽ để quản lý dự án, cho phép người dùng theo dõi các khía cạnh khác nhau của dự án của họ. Một tính năng quan trọng của MS Project là khả năng trực quan hóa các đường tiến độ, giúp các bên liên quan hiểu được trạng thái và quỹ đạo của dự án. Trong hướng dẫn này, chúng ta sẽ khám phá cách xử lý các dòng tiến trình trong MS Project bằng thư viện Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Visual Studio: Cài đặt Visual Studio hoặc bất kỳ môi trường phát triển .NET ưa thích nào khác.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.

## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Bây giờ, hãy chia nhỏ từng bước trong việc xử lý các dòng tiến trình:
## Bước 1: Tải tệp dự án
```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Ở đây chúng ta tải file MS Project`Project2.mpp` và thiết lập ngày trạng thái của nó.
## Bước 2: Xác định dạng xem biểu đồ Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Chúng tôi chuyển chế độ xem của dự án sang chế độ xem biểu đồ Gantt để thao tác thêm.
## Bước 3: Xác định dòng tiến độ
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Chúng tôi khởi tạo các dòng tiến trình cho chế độ xem biểu đồ Gantt.
## Bước 4: Định cấu hình cài đặt dòng tiến trình
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Ở đây, chúng tôi đặt các thuộc tính khác nhau cho các dòng tiến trình, chẳng hạn như màu dòng, mẫu, phông chữ, v.v.
## Bước 5: Kiểm tra cấu hình dòng tiến trình
```csharp
// Cài đặt dòng tiến trình đầu ra
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Xuất các cài đặt khác...
```
Chúng tôi xuất cài đặt dòng tiến trình đã định cấu hình để xác minh.
## Bước 6: Lưu tệp dự án
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Cuối cùng, chúng tôi lưu tệp dự án đã sửa đổi với các dòng tiến trình.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách xử lý các dòng tiến trình MS Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể tùy chỉnh và trực quan hóa các dòng tiến trình một cách hiệu quả trong các tệp MS Project của mình theo chương trình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tùy chỉnh thêm giao diện của dòng tiến trình không?
Trả lời: Có, bạn có thể điều chỉnh các thuộc tính khác nhau như màu đường, mẫu và phông chữ cho phù hợp với yêu cầu của mình.
### Câu hỏi: Aspose.Tasks có hỗ trợ các tính năng quản lý dự án khác không?
Trả lời: Có, Aspose.Tasks cung cấp hỗ trợ rộng rãi để thao tác các khía cạnh khác nhau của tệp MS Project, bao gồm các nhiệm vụ, tài nguyên và lịch.
### Câu hỏi: Tôi có thể tích hợp Aspose.Tasks với các thư viện .NET khác không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks được thiết kế để tích hợp liền mạch với các thư viện .NET khác, cho phép bạn nâng cao hơn nữa các ứng dụng quản lý dự án của mình.
### Câu hỏi: Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks không?
 Trả lời: Có, bạn có thể tìm thấy các tài nguyên hữu ích và tìm kiếm sự trợ giúp trên diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Aspose.Tasks có cung cấp giấy phép tạm thời cho mục đích đánh giá không?
 Đáp: Có, bạn có thể xin giấy phép tạm thời để đánh giá từ[đây](https://purchase.aspose.com/temporary-license/).