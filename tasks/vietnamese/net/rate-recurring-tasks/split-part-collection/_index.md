---
title: Thu thập dự án MS của các bộ phận phân chia trong Aspose.Tasks
linktitle: Bộ sưu tập các phần phân chia trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thu thập các phần được phân tách trong MS Project bằng Aspose.Tasks for .NET. Hướng dẫn toàn diện này sẽ hướng dẫn bạn thực hiện quy trình theo từng bước.
type: docs
weight: 19
url: /vi/net/rate-recurring-tasks/split-part-collection/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào cách thu thập các phần được phân chia trong MS Project bằng cách sử dụng Aspose.Tasks cho .NET. Chia nhiệm vụ thành nhiều phần có thể là một khía cạnh quan trọng trong quản lý dự án và Aspose.Tasks cung cấp các phương pháp thuận tiện để xử lý việc này một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Cài đặt Aspose.Tasks cho .NET: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
2. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có ích vì chúng ta sẽ viết các đoạn mã trong C#.

## Nhập không gian tên
Trong dự án C# của bạn, hãy bao gồm các không gian tên cần thiết:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Bước 1: Thiết lập dự án của bạn
Trước tiên, hãy tạo một dự án mới trong IDE ưa thích của bạn và đảm bảo Aspose.Tasks for .NET được tham chiếu chính xác.
## Bước 2: Khởi tạo đối tượng dự án
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Khởi tạo một đối tượng Project mới với đường dẫn đến tệp MS Project của bạn.
## Bước 3: Truy xuất tác vụ và lặp lại các phần được chia nhỏ
```csharp
var task = project.RootTask.Children.GetById(1);
// Lặp lại các phần được chia nhỏ
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Truy xuất nhiệm vụ từ dự án và lặp lại các phần được phân chia của nó, in ra ngày bắt đầu và ngày kết thúc của chúng.
## Bước 4: Nhận chia phần theo chỉ mục
```csharp
// Lấy phần theo chỉ mục
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Truy xuất một phần được phân chia cụ thể theo chỉ mục và in ra ngày bắt đầu của nó.

## Phần kết luận
Quản lý các phần được phân tách trong tệp MS Project có thể nâng cao đáng kể hiệu quả quản lý dự án. Aspose.Tasks for .NET đơn giản hóa quy trình này bằng cách cung cấp các API trực quan để xử lý các tác vụ được phân chia một cách liền mạch.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể phân chia nhiệm vụ một cách linh hoạt trong thời gian chạy không?
Trả lời: Có, bạn có thể phân chia nhiệm vụ theo chương trình bằng cách sử dụng Aspose.Tasks cho .NET.
### Câu hỏi: Aspose.Tasks có hỗ trợ tất cả các phiên bản của tệp MS Project không?
Trả lời: Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp MS Project, đảm bảo khả năng tương thích trên các nền tảng khác nhau.
### Hỏi: Có phiên bản dùng thử nào dành cho mục đích thử nghiệm không?
 Đ: Có, bạn có thể tải phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/) để đánh giá.
### Hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho các dự án của mình?
 Đáp: Giấy phép tạm thời có thể được lấy từ[đây](https://purchase.aspose.com/temporary-license/) để sử dụng trong thời gian ngắn.
### Câu hỏi: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ về Aspose.Tasks ở đâu?
 Trả lời: Bạn có thể truy cập diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15)để tìm kiếm sự hỗ trợ từ cộng đồng hoặc nhóm hỗ trợ Aspose.