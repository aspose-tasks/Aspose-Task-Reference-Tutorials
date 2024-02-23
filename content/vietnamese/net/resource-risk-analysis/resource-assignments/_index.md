---
title: Xử lý các bài tập tài nguyên dự án MS trong Aspose.Tasks
linktitle: Xử lý việc gán tài nguyên trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý hiệu quả các nhiệm vụ tài nguyên MS Project bằng cách sử dụng Aspose.Tasks cho .NET. Toàn diện này cung cấp hướng dẫn từng bước cho các nhà phát triển.
type: docs
weight: 11
url: /vi/net/resource-risk-analysis/resource-assignments/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào cách xử lý các bài tập tài nguyên Microsoft Project một cách hiệu quả bằng cách sử dụng Aspose.Tasks cho .NET. Aspose.Tasks là một API mạnh mẽ cho phép các nhà phát triển thao tác với các tệp Microsoft Project theo chương trình. Bằng cách làm theo các bước này, bạn sẽ học cách quản lý việc gán tài nguyên một cách hiệu quả trong các ứng dụng .NET của mình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết để sử dụng các chức năng Aspose.Tasks trong dự án .NET của mình. Điêu nay bao gôm:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Bây giờ, hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hiểu toàn diện về cách xử lý các bài tập tài nguyên MS Project bằng Aspose.Tasks.
## Bước 1: Thiết lập cài đặt dự án và lịch
Để bắt đầu, hãy tạo một phiên bản Dự án mới và thiết lập cài đặt lịch của dự án:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Bước 2: Thêm tác vụ vào dự án
Tiếp theo, thêm một tác vụ mới vào tác vụ gốc của dự án:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Bước 3: Tạo phân công tài nguyên và tạo dữ liệu theo pha thời gian
Bây giờ, hãy tạo phân công tài nguyên mới cho tác vụ và tạo dữ liệu theo pha thời gian:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Bước 4: Chia nhiệm vụ
Chia nhiệm vụ thành nhiều phần bằng cách cung cấp ngày bắt đầu và ngày kết thúc:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Bước 5: Đặt đường viền công việc
Đặt loại đường viền công việc cho nhiệm vụ:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Bước 6: Lưu dự án
Cuối cùng, lưu tệp dự án với những thay đổi được thực hiện:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Phần kết luận
Tóm lại, việc xử lý các bài tập tài nguyên Microsoft Project bằng Aspose.Tasks cho .NET là một quá trình đơn giản. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể quản lý hiệu quả việc gán tài nguyên trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Aspose.Tasks có thể xử lý các cấu trúc dự án phức tạp không?
Có, Aspose.Tasks cung cấp các chức năng toàn diện để xử lý các cấu trúc dự án phức tạp một cách hiệu quả.
### Aspose.Tasks có tương thích với các phiên bản khác nhau của Microsoft Project không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Tôi có thể tùy chỉnh việc phân công nguồn lực dựa trên các yêu cầu cụ thể không?
Hoàn toàn có thể, Aspose.Tasks cung cấp các tùy chọn tùy chỉnh mở rộng cho việc phân công tài nguyên để đáp ứng các nhu cầu dự án cụ thể.
### Aspose.Tasks có hỗ trợ xuất dữ liệu dự án sang các định dạng khác không?
Có, Aspose.Tasks cho phép xuất dữ liệu dự án sang nhiều định dạng khác nhau như XML, PDF và HTML, cùng nhiều định dạng khác.
### Người dùng Aspose.Tasks có được hỗ trợ kỹ thuật không?
Có, Aspose cung cấp hỗ trợ kỹ thuật chuyên dụng thông qua diễn đàn và các kênh khác để hỗ trợ người dùng nếu có bất kỳ thắc mắc hoặc vấn đề nào.