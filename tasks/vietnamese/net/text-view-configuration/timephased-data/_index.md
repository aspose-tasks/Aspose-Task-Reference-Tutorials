---
title: Làm chủ việc xử lý dữ liệu theo pha thời gian với Aspose.Tasks cho .NET
linktitle: Xử lý dữ liệu theo pha thời gian trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá Aspose.Tasks dành cho .NET để dễ dàng xử lý dữ liệu theo pha thời gian, nâng cao khả năng lập kế hoạch dự án và tối ưu hóa việc quản lý tài nguyên. #Aspose #Tasks #MS Project
weight: 14
url: /vi/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Làm chủ việc xử lý dữ liệu theo pha thời gian với Aspose.Tasks cho .NET

## Giới thiệu
Trong thế giới quản lý dự án, việc xử lý hiệu quả dữ liệu theo pha thời gian là rất quan trọng để phân bổ nguồn lực, ước tính chi phí và lập kế hoạch tổng thể cho dự án. Aspose.Tasks for .NET cung cấp một giải pháp mạnh mẽ để làm việc liền mạch với dữ liệu theo pha thời gian tùy chỉnh. Hướng dẫn này sẽ hướng dẫn bạn quy trình xử lý dữ liệu theo pha thời gian bằng Aspose.Tasks, cho phép bạn tối ưu hóa việc quản lý tài nguyên trong các dự án của mình.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Hiểu biết cơ bản về các khái niệm quản lý dự án.
-  Đã cài đặt Aspose.Tasks cho .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/tasks/net/).
- Trình chỉnh sửa mã, chẳng hạn như Visual Studio, để triển khai các ví dụ được cung cấp.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy đảm bảo nhập các vùng tên cần thiết để tận dụng các chức năng của Aspose.Tasks. Thêm các dòng sau vào đầu tệp mã của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước để hướng dẫn bạn xử lý dữ liệu theo pha thời gian bằng Aspose.Tasks:
## Bước 1: Thiết lập dự án
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Ở đây, chúng ta khởi tạo một dự án mới và thiết lập chế độ tính toán cho nó.
## Bước 2: Xác định nguồn lực và nhiệm vụ
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Tạo các nguồn lực công việc và chi phí cũng như một nhiệm vụ để mô phỏng cấu trúc dự án.
## Bước 3: Gán tài nguyên cho nhiệm vụ
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Phân công công việc và nguồn lực chi phí cho nhiệm vụ.
## Bước 4: Thêm dữ liệu theo thời gian tùy chỉnh
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Các bước tương tự cho phân bổ chi phí
costAssignment.TimephasedData.Clear();
```
Thêm dữ liệu theo pha thời gian tùy chỉnh cho cả nhiệm vụ công việc và chi phí.
## Bước 5: Hiển thị dữ liệu theo pha thời gian
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Hiển thị thông tin liên quan về từng mục nhập dữ liệu theo pha thời gian
    }
}
```
Cuối cùng, hiển thị dữ liệu theo pha thời gian cho mỗi bài tập.
#
## Phần kết luận
Việc xử lý hiệu quả dữ liệu theo pha thời gian trong Aspose.Tasks mở ra những khả năng mới để lập kế hoạch dự án chi tiết và quản lý tài nguyên. Bằng cách làm theo hướng dẫn từng bước này, bạn đã học được cách thao tác dữ liệu theo pha thời gian để đáp ứng nhu cầu cụ thể cho dự án của mình.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho .NET với các công cụ quản lý dự án khác không?
Aspose.Tasks được thiết kế chủ yếu để phát triển .NET. Tuy nhiên, chức năng của nó có thể bổ sung cho nhiều công cụ quản lý dự án khác nhau.
### Có bản dùng thử miễn phí dành cho Aspose.Tasks cho .NET không?
 Có, bạn có thể khám phá bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?
 Tham quan[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để hỗ trợ cộng đồng.
### Giấy phép tạm thời là gì và làm cách nào để có được giấy phép?
 Tìm hiểu về giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể tìm tài liệu về Aspose.Tasks cho .NET ở đâu?
 Tham khảo toàn diện[tài liệu](https://reference.aspose.com/tasks/net/) để biết thông tin chi tiết.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
