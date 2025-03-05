---
title: Nắm vững các đường cơ sở của nhiệm vụ trong Aspose.Tasks cho .NET
linktitle: Xử lý các đường cơ sở của nhiệm vụ trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý các đường cơ sở của nhiệm vụ trong Aspose.Tasks for .NET với hướng dẫn toàn diện này. Hãy nâng cao kỹ năng quản lý dự án của bạn ngay hôm nay!
type: docs
weight: 16
url: /vi/net/task-table-management/task-baselines/
---
## Giới thiệu
Trong thế giới năng động của quản lý dự án, việc luôn tổ chức và cập nhật thông tin là rất quan trọng. Aspose.Tasks for .NET cung cấp một giải pháp mạnh mẽ để xử lý các đường cơ sở của nhiệm vụ, cho phép bạn truy cập thông tin cơ sở có giá trị một cách hiệu quả. Hướng dẫn từng bước này sẽ hướng dẫn bạn thực hiện quy trình, đảm bảo bạn nắm bắt từng khái niệm một cách rõ ràng.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Thiết lập môi trường: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET trong môi trường phát triển của mình. Nếu không, bạn có thể tải xuống từ[Tài liệu Aspose.Tasks](https://reference.aspose.com/tasks/net/).
- Kiến thức cơ bản về C#: Làm quen với các kiến thức cơ bản về ngôn ngữ lập trình C#, vì hướng dẫn này giả định bạn có hiểu biết cơ bản.
- Môi trường phát triển tích hợp (IDE): Sử dụng IDE ưa thích như Visual Studio để theo dõi một cách liền mạch.
## Nhập không gian tên
Để bắt đầu, hãy nhập các không gian tên cần thiết vào dự án của bạn. Điều này đảm bảo bạn có quyền truy cập vào chức năng Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
```
Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước để hướng dẫn bạn xử lý các đường cơ sở của nhiệm vụ trong Aspose.Tasks.
## Bước 1: Tạo dự án
```csharp
var project = new Project();
```
 Bắt đầu bằng cách khởi tạo một dự án mới bằng cách sử dụng`Project` lớp học.
## Bước 2: Tạo nhiệm vụ và đặt đường cơ sở
```csharp
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
```
 Thêm một nhiệm vụ vào dự án và thiết lập đường cơ sở của nó bằng cách sử dụng`SetBaseline` phương pháp.
## Bước 3: Hiển thị thông tin cơ bản của nhiệm vụ
```csharp
var baseline = task.Baselines.ToList()[0];
Console.WriteLine("Baseline Start: {0}", baseline.Start);
Console.WriteLine("Baseline duration: {0}", baseline.Duration);
Console.WriteLine("Baseline duration format: {0}", baseline.Duration.TimeUnit);
Console.WriteLine("Is it estimated duration?: {0}", baseline.EstimatedDuration);
Console.WriteLine("Baseline Finish: {0}", baseline.Finish);
```
Truy xuất và hiển thị thông tin chính về đường cơ sở của nhiệm vụ, chẳng hạn như thời gian bắt đầu, thời lượng và thời gian kết thúc.
## Bước 4: Chi tiết cơ sở bổ sung
```csharp
Console.WriteLine("Interim: {0}", baseline.Interim);
Console.WriteLine("Fixed Cost: {0}", baseline.FixedCost);
```
Khám phá các chi tiết bổ sung, bao gồm liệu đường cơ sở có phải là Đường cơ sở tạm thời hay không và chi phí cố định liên quan đến nó.
## Bước 5: In dữ liệu theo pha thời gian
```csharp
Console.WriteLine("Number of timephased items: " + baseline.TimephasedData.Count);
foreach (var data in baseline.TimephasedData)
{
    Console.WriteLine(" Uid: " + data.Uid);
    Console.WriteLine(" Start: " + data.Start);
    Console.WriteLine(" Finish: " + data.Finish);
}
```
Hiểu dữ liệu theo pha thời gian được liên kết với đường cơ sở của nhiệm vụ, cung cấp thông tin chi tiết về các mốc thời gian khác nhau của dự án.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách xử lý các đường cơ sở của nhiệm vụ trong Aspose.Tasks cho .NET. Kiến thức này sẽ nâng cao khả năng quản lý dự án của bạn, đảm bảo theo dõi và lập kế hoạch chính xác.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các khung .NET khác không?
Trả lời: Aspose.Tasks tương thích với nhiều khung .NET, mang lại sự linh hoạt trong môi trường phát triển của bạn.
### Câu hỏi: Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks không?
 Đáp: Có, bạn có thể tìm sự hỗ trợ và tương tác với cộng đồng tại[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Tasks?
 Đáp: Ghé thăm[đây](https://purchase.aspose.com/temporary-license/)để có được giấy phép tạm thời cho Aspose.Tasks.
### Câu hỏi: Có hướng dẫn nào ngoài các hướng dẫn cơ bản về nhiệm vụ không?
 A: Khám phá[tài liệu](https://reference.aspose.com/tasks/net/) để biết nhiều hướng dẫn về các tính năng của Aspose.Tasks.
### Câu hỏi: Tôi có thể mua Aspose.Tasks cho .NET ở đâu?
 Trả lời: Bạn có thể mua Aspose.Tasks một cách thuận tiện[đây](https://purchase.aspose.com/buy).