---
title: Trích xuất thông tin tác vụ định kỳ trong Aspose.Tasks
linktitle: Trích xuất thông tin tác vụ định kỳ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách trích xuất thông tin tác vụ định kỳ từ tệp MS Project bằng Aspose.Tasks for .NET. Tích hợp dễ dàng cho các nhà phát triển .NET.
weight: 13
url: /vi/net/rate-recurring-tasks/recurring-task-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất thông tin tác vụ định kỳ trong Aspose.Tasks

## Giới thiệu
Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project trong các ứng dụng .NET của họ. Trong hướng dẫn này, chúng ta sẽ khám phá cách trích xuất thông tin tác vụ định kỳ từ các tệp MS Project bằng Aspose.Tasks.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Hiểu biết cơ bản về ngôn ngữ lập trình C#.
2. Visual Studio được cài đặt trên hệ thống của bạn.
3.  Aspose.Tasks cho thư viện .NET đã được cài đặt. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
## Nhập không gian tên
Để bắt đầu, hãy nhập các vùng tên cần thiết trong mã C# của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Bây giờ, hãy chia ví dụ thành nhiều bước:
## Bước 1: Thiết lập đường dẫn file dự án
```csharp
String DataDir = "Your Document Directory";
```
 Thay thế`"Your Document Directory"` với đường dẫn đến tệp MS Project của bạn.
## Bước 2: Tải tệp MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Dòng này khởi tạo một cái mới`Project` đối tượng bằng cách tải tệp MS Project được chỉ định bởi đường dẫn.
## Bước 3: Đọc thông tin định kỳ của nhiệm vụ
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Truy cập và hiển thị thông tin nhiệm vụ định kỳ
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Tiếp tục hiển thị thông tin nhiệm vụ định kỳ khác nếu cần
}
```
Vòng lặp này lặp qua tất cả các nhiệm vụ trong dự án và kiểm tra xem mỗi nhiệm vụ có thông tin định kỳ liên quan đến nó hay không. Nếu đúng như vậy, nó sẽ truy xuất và hiển thị các thuộc tính khác nhau của tác vụ định kỳ, chẳng hạn như ngày bắt đầu, thời lượng, ngày kết thúc, v.v.
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách trích xuất thông tin tác vụ định kỳ từ các tệp MS Project bằng Aspose.Tasks cho .NET. Với kiến thức này, giờ đây bạn có thể tích hợp chức năng này vào các ứng dụng .NET của mình để làm việc với các tác vụ định kỳ hiệu quả hơn.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sửa đổi thông tin tác vụ định kỳ bằng Aspose.Tasks cho .NET không?
Đáp: Có, bạn có thể sửa đổi thông tin nhiệm vụ định kỳ theo chương trình bằng cách sử dụng các API được cung cấp.
### Câu hỏi: Aspose.Tasks có hỗ trợ các định dạng tệp dự án khác ngoài MS Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án khác nhau như MPP, XML và CSV.
### Câu hỏi: Có bản dùng thử miễn phí Aspose.Tasks cho .NET không?
 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm tài liệu về Aspose.Tasks cho .NET ở đâu?
 A: Bạn có thể tìm tài liệu[đây](https://reference.aspose.com/tasks/net/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ kỹ thuật cho Aspose.Tasks cho .NET?
 Trả lời: Bạn có thể nhận hỗ trợ kỹ thuật từ diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
