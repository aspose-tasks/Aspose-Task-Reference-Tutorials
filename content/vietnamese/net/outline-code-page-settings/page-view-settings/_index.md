---
title: Tùy chỉnh cài đặt chế độ xem trang dự án MS trong Aspose.Tasks
linktitle: Định cấu hình cài đặt chế độ xem trang trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách định cấu hình cài đặt chế độ xem trang trong Aspose.Tasks cho .NET để điều chỉnh định dạng in của tài liệu Microsoft Project của bạn.
type: docs
weight: 21
url: /vi/net/outline-code-page-settings/page-view-settings/
---
## Giới thiệu
Microsoft Project là một công cụ mạnh mẽ để quản lý dự án, nhưng đôi khi bạn cần tùy chỉnh cách xem và in dự án của mình. Với Aspose.Tasks cho .NET, bạn có thể dễ dàng định cấu hình cài đặt chế độ xem trang để đáp ứng các yêu cầu cụ thể của mình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Aspose.Tasks for .NET: Đảm bảo bạn đã tải xuống và cài đặt thư viện Aspose.Tasks for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
2. Tệp dự án Microsoft: Chuẩn bị sẵn tệp Microsoft Project mà bạn muốn định cấu hình cài đặt chế độ xem trang.

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết để làm việc với Aspose.Tasks trong dự án .NET của mình.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Bước 1: Tải tệp dự án
 Bắt đầu bằng cách tải tệp Microsoft Project của bạn vào một phiên bản của`Project` lớp học.
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Bước 2: Đặt số cột đầu tiên
Chỉ định số cột đầu tiên sẽ được in trên tất cả các trang.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Bước 3: In ghi chú
Chọn có in ghi chú cùng với dự án hay không.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Bước 4: Điều chỉnh thang thời gian cho đến cuối trang
Quyết định xem có điều chỉnh thang thời gian đến cuối trang khi in hay không.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Bước 5: In tất cả các cột của trang tính
Chỉ định xem có in tất cả các cột trong trang tính của một dạng xem hay không.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Bước 6: In trang trống
Chọn có in các trang trống của chế độ xem hay không.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Bước 7: In cột đầu tiên trên tất cả các trang
Đặt xem có in số lượng cột đầu tiên được chỉ định trên tất cả các trang hay không.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Bước 8: Lưu dự án với cài đặt đã định cấu hình
Cuối cùng, lưu dự án với cài đặt chế độ xem trang đã định cấu hình, chỉ định định dạng đầu ra, chẳng hạn như PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Phần kết luận
Việc định cấu hình cài đặt chế độ xem trang Microsoft Project trong Aspose.Tasks cho .NET rất đơn giản và cho phép bạn điều chỉnh định dạng in theo nhu cầu chính xác của mình. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể đảm bảo rằng tài liệu dự án của mình được trình bày chính xác theo yêu cầu.
## Câu hỏi thường gặp
### H: Tôi có thể định cấu hình cài đặt xem trang cho các định dạng tệp khác ngoài PDF không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp khác nhau để lưu dự án, bao gồm XLSX, MPP và HTML.
### Câu hỏi: Có bất kỳ hạn chế nào về số lượng cột tôi có thể in không?
Trả lời: Aspose.Tasks cho phép bạn tùy chỉnh số lượng cột sẽ được in dựa trên yêu cầu của bạn.
### Câu hỏi: Tôi có thể áp dụng các cài đặt chế độ xem trang khác nhau cho các dự án khác nhau không?
Đáp: Có, bạn có thể điều chỉnh cài đặt chế độ xem trang một cách độc lập cho từng tệp dự án mà bạn làm việc.
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?
Trả lời: Aspose.Tasks cung cấp khả năng tương thích với Microsoft Project 2003 và các phiên bản mới hơn.
### Câu hỏi: Tôi có thể tìm thêm trợ giúp hoặc hỗ trợ cho Aspose.Tasks ở đâu?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15)nếu có bất kỳ thắc mắc hoặc vấn đề nào bạn gặp phải trong quá trình sử dụng.