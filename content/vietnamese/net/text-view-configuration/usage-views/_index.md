---
title: Định cấu hình Chế độ xem sử dụng trong Aspose.Tasks
linktitle: Định cấu hình Chế độ xem sử dụng trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách định cấu hình chế độ xem sử dụng tác vụ trong Aspose.Tasks cho .NET. Tăng cường trực quan hóa dự án với các bước chi tiết. Tải thư viện ngay bây giờ!
type: docs
weight: 17
url: /vi/net/text-view-configuration/usage-views/
---
## Giới thiệu
Nếu bạn là nhà phát triển .NET đang tìm cách nâng cao khả năng quản lý dự án của mình thì Aspose.Tasks là một công cụ mạnh mẽ cho phép bạn thao tác các tệp Microsoft Project một cách dễ dàng. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc định cấu hình chế độ xem sử dụng bằng Aspose.Tasks cho .NET. Hãy theo dõi để hiểu rõ hơn về cách hiển thị các chế độ xem sử dụng tác vụ cùng với các chi tiết để trực quan hóa dự án tốt hơn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Thư viện Aspose.Tasks: Đảm bảo bạn đã tích hợp thư viện Aspose.Tasks vào dự án .NET của mình. Nếu không, bạn có thể tải xuống[đây](https://releases.aspose.com/tasks/net/) và làm theo hướng dẫn cài đặt.
- Thư mục tài liệu: Thiết lập một thư mục nơi lưu trữ tài liệu dự án của bạn. Thay thế "Thư mục tài liệu của bạn" trong đoạn mã bằng đường dẫn thực tế đến thư mục tài liệu của bạn.
## Nhập không gian tên
Trong đoạn mã được cung cấp, bạn sẽ nhận thấy việc sử dụng các không gian tên nhất định. Đảm bảo đưa những thứ này vào dự án của bạn để tích hợp liền mạch:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## Bước 1: Hiển thị chế độ xem sử dụng tác vụ với thông tin chi tiết
Hãy bắt đầu bằng cách hiển thị chế độ xem sử dụng tác vụ với các chi tiết. Thực hiện theo các bước sau:
## Bước 1.1: Tải dự án
```csharp
// Đường dẫn tới thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## Bước 1.2: Nhận chế độ xem
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## Bước 1.3: Tùy chỉnh cài đặt chế độ xem
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## Bước 1.4: Lưu dự án dưới dạng PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## Bước 2: Hiển thị chi tiết cột tiêu đề
Trong bước này, chúng tôi sẽ sửa đổi cài đặt chế độ xem để hiển thị cột tiêu đề chi tiết và lưu dự án dưới dạng PDF:
## Bước 2.1: Hiển thị chi tiết cột tiêu đề
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## Bước 2.2: Lặp lại tiêu đề chi tiết trên tất cả các hàng
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## Bước 2.3: Lưu dự án dưới dạng PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## Phần kết luận
Chúc mừng! Bạn đã định cấu hình thành công chế độ xem sử dụng trong Aspose.Tasks. Hướng dẫn này cung cấp nền tảng để quản lý và trực quan hóa dự án hiệu quả bằng thư viện Aspose.Tasks.

### Câu hỏi thường gặp
### Câu hỏi: Tôi có thể tìm tài liệu Aspose.Tasks ở đâu?
 Tài liệu đầy đủ có sẵn[đây](https://reference.aspose.com/tasks/net/).
### Câu hỏi: Làm cách nào tôi có thể tải xuống Aspose.Tasks cho .NET?
 Tải xuống thư viện[đây](https://releases.aspose.com/tasks/net/).
### Câu hỏi: Tôi có thể mua Aspose.Tasks ở đâu?
 Bạn có thể mua Aspose.Tasks[đây](https://purchase.aspose.com/buy).
### Hỏi: Có bản dùng thử miễn phí không?
 Có, hãy khám phá bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Hỏi: Cần hỗ trợ hoặc có thắc mắc?
 Truy cập diễn đàn hỗ trợ[đây](https://forum.aspose.com/c/tasks/15).