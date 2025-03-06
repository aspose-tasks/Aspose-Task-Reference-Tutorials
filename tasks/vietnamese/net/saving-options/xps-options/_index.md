---
title: Chuyển đổi tùy chọn MSP sang XPS với Aspose.Tasks
linktitle: Tùy chọn XPS cho Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách chuyển đổi tệp Microsoft Project sang định dạng XPS bằng Aspose.Tasks cho .NET. Tích hợp dễ dàng, chức năng mạnh mẽ.
type: docs
weight: 21
url: /vi/net/saving-options/xps-options/
---
## Giới thiệu
Microsoft Project (MSP) là một công cụ được sử dụng rộng rãi để quản lý dự án, tạo điều kiện thuận lợi cho việc lập kế hoạch, theo dõi và báo cáo các hoạt động của dự án. Aspose.Tasks for .NET cung cấp chức năng mạnh mẽ để thao tác các tệp MSP theo chương trình, trao quyền cho các nhà phát triển tự động hóa các tác vụ khác nhau liên quan đến quản lý dự án. Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc tận dụng Aspose.Tasks cho .NET để tạo tệp XPS từ tài liệu MSP, khám phá các bước cần thiết và cân nhắc.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Cài đặt Aspose.Tasks cho .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[trang mạng](https://releases.aspose.com/tasks/net/).
2. Tài liệu Microsoft Project: Chuẩn bị tài liệu Microsoft Project (.mpp) mà bạn định chuyển đổi sang định dạng XPS.

## Nhập không gian tên
Để bắt đầu quá trình, hãy nhập các vùng tên cần thiết trong dự án .NET của bạn:
```csharp

using Aspose.Tasks.Saving;
```

## Bước 1: Đặt đường dẫn thư mục tài liệu
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
```
 Thay thế`"Your Document Directory"` với đường dẫn chứa tài liệu MSP của bạn.
## Bước 2: Tải tài liệu MSP
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
 Ở đây, chúng ta khởi tạo một cái mới`Project` đối tượng bằng cách chuyển đường dẫn của tài liệu MSP.
## Bước 3: Tạo tùy chọn lưu XPS
```csharp
// Tạo tùy chọn lưu XPS và điều chỉnh các thông số
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
 Ở bước này, chúng ta khởi tạo`XpsOptions`và cấu hình các tham số. Cài đặt`RenderMetafileAsBitmap` ĐẾN`true` đảm bảo hiển thị đúng các siêu tập tin.
## Bước 4: Lưu tài liệu dưới dạng XPS
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
 Cuối cùng, chúng tôi gọi`Save` phương pháp trên`Project` đối tượng, chỉ định đường dẫn tệp đầu ra và cấu hình trước đó`XpsOptions`.

## Phần kết luận
Tóm lại, Aspose.Tasks for .NET đơn giản hóa quá trình chuyển đổi tài liệu Microsoft Project sang định dạng XPS theo chương trình. Bằng cách làm theo các bước được nêu trong hướng dẫn này, các nhà phát triển có thể tích hợp liền mạch chức năng này vào các ứng dụng .NET của họ, nâng cao quy trình quản lý dự án một cách dễ dàng.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks cho .NET có thể xử lý các tệp MSP phức tạp không?
Trả lời: Có, Aspose.Tasks cho .NET có thể xử lý các tệp Microsoft Project phức tạp một cách hiệu quả, đảm bảo chuyển đổi chính xác sang nhiều định dạng khác nhau.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?
 Đ: Có, bạn có thể tải phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Aspose.Tasks cho .NET có hỗ trợ các định dạng đầu ra khác ngoài XPS không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ nhiều định dạng đầu ra khác nhau như PDF, HTML, PNG và JPEG, cùng nhiều định dạng khác.
### Hỏi: Tôi có thể tùy chỉnh các tùy chọn hiển thị cho tệp đầu ra không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks for .NET cung cấp các tùy chọn mở rộng để tùy chỉnh các tham số hiển thị theo yêu cầu của bạn.
### Câu hỏi: Tôi có thể tìm hỗ trợ hoặc hỗ trợ bổ sung cho Aspose.Tasks cho .NET ở đâu?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) nếu có bất kỳ thắc mắc hoặc hỗ trợ nào liên quan đến Aspose.Tasks for .NET.