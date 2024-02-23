---
title: Nắm vững việc thu thập dữ liệu theo pha thời gian trong Aspose.Tasks
linktitle: Thu thập dữ liệu theo pha thời gian trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Khám phá việc thu thập dữ liệu theo pha thời gian trong Aspose.Tasks cho .NET. Hướng dẫn từng bước, Câu hỏi thường gặp và hơn thế nữa. Hãy nâng cao khả năng quản lý dự án của bạn ngay hôm nay!
type: docs
weight: 15
url: /vi/net/text-view-configuration/timephased-data-collection/
---
## Giới thiệu
Bạn đang tìm cách khai thác sức mạnh của dữ liệu phân đoạn thời gian trong các ứng dụng .NET của mình bằng Aspose.Tasks? Đừng tìm đâu xa! Hướng dẫn toàn diện này sẽ hướng dẫn bạn quy trình thu thập dữ liệu theo pha thời gian với Aspose.Tasks cho .NET, đảm bảo rằng bạn tận dụng tối đa thư viện mạnh mẽ này.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.Tasks for .NET Library: Tải xuống và cài đặt thư viện từ[Aspose.Tasks Tài liệu .NET](https://reference.aspose.com/tasks/net/).
2. Môi trường phát triển .NET: Đảm bảo bạn đã thiết lập môi trường phát triển .NET đang hoạt động.
3. Thư mục tài liệu của bạn: Thay thế phần giữ chỗ "Thư mục tài liệu của bạn" trong đoạn mã bằng đường dẫn đến thư mục tài liệu của bạn.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết để tận dụng các chức năng của Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Tạo dự án và tài nguyên
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Thêm nhiệm vụ vào dự án
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Đặt thuộc tính nhiệm vụ...
var task2 = project.RootTask.Children.Add("Task 2");
// Đặt thuộc tính task2...
```
## 3. Gán tài nguyên cho nhiệm vụ
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Đặt thuộc tính bài tập...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Đặt thuộc tính gán2...
```
## 4. Làm việc với dữ liệu theo pha thời gian
```csharp
// Đặt đường viền làm việc theo đường viền
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Kiểm tra xem việc thu thập dữ liệu theo pha thời gian có ở chế độ chỉ đọc hay không
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Xóa dữ liệu theo pha thời gian được tạo
assignment.TimephasedData.Clear();
// Tạo và thêm dữ liệu theo pha thời gian
var td = new TimephasedData
{
    // Đặt thuộc tính dữ liệu theo pha thời gian...
};
assignment.TimephasedData.Add(td);
// Thêm danh sách dữ liệu theo pha thời gian
var list = new List<TimephasedData>();
// Thêm nhiều mục dữ liệu theo pha thời gian hơn vào danh sách...
assignment.TimephasedData.AddRange(list);
// Lọc dữ liệu theo pha thời gian theo loại và phạm vi ngày
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// In dữ liệu theo pha thời gian đã lọc...
```
## 5. Thao tác dữ liệu theo pha thời gian
```csharp
//Thêm một mục dữ liệu theo pha thời gian sai rồi xóa nó
var td4 = new TimephasedData
{
    // Đặt thuộc tính dữ liệu theo pha thời gian sai...
};
assignment.TimephasedData.Add(td4);
// Xóa mục dữ liệu theo pha thời gian sai
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Lặp lại tất cả các mục theo pha thời gian
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // In chi tiết mục theo pha thời gian...
}
```
## 6. Sao chép dữ liệu theo pha thời gian sang bài tập khác
```csharp
// Sao chép dữ liệu theo pha thời gian sang bài tập khác
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Chuyển đổi bộ sưu tập thành một danh sách đơn giản
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Xóa từng mục dữ liệu theo pha thời gian
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Phần kết luận
Tóm lại, hướng dẫn này đã cung cấp hướng dẫn chi tiết về cách thu thập dữ liệu theo pha thời gian bằng cách sử dụng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể tích hợp liền mạch chức năng này vào các dự án của mình, cho phép theo dõi thời gian và quản lý tài nguyên hiệu quả.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho .NET với các công cụ quản lý dự án khác không?
Có, Aspose.Tasks for .NET được thiết kế để hoạt động với các công cụ quản lý dự án phổ biến và hỗ trợ nhiều định dạng tệp khác nhau.
### Có giới hạn nào về số lượng tài nguyên và nhiệm vụ mà tôi có thể quản lý bằng Aspose.Tasks không?
Aspose.Tasks xử lý các dự án có quy mô khác nhau và không có giới hạn nghiêm ngặt về số lượng tài nguyên và nhiệm vụ.
### Làm cách nào tôi có thể nhận được hỗ trợ cho bất kỳ vấn đề hoặc truy vấn nào liên quan đến Aspose.Tasks cho .NET?
 Để được hỗ trợ, hãy truy cập[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để kết nối với cộng đồng và nhận được sự trợ giúp.
### Tôi có thể dùng thử Aspose.Tasks cho .NET trước khi mua nó không?
 Có, bạn có thể khám phá các tính năng của Aspose.Tasks for .NET bằng cách truy cập[dùng thử miễn phí](https://releases.aspose.com/).
### Tôi có thể mua giấy phép Aspose.Tasks cho .NET ở đâu?
 Bạn có thể mua giấy phép Aspose.Tasks cho .NET[đây](https://purchase.aspose.com/buy).