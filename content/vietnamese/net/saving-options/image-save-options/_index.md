---
title: Lưu hình ảnh Tùy chọn dự án MS cho Aspose.Tasks
linktitle: Tùy chọn lưu hình ảnh cho Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách lưu các tùy chọn MS Project dưới dạng hình ảnh bằng Aspose.Tasks cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
type: docs
weight: 11
url: /vi/net/saving-options/image-save-options/
---

## Giới thiệu
Trong thế giới phát triển phần mềm, việc xử lý các nhiệm vụ dự án một cách hiệu quả là rất quan trọng để quản lý dự án thành công. Aspose.Tasks for .NET cung cấp một giải pháp mạnh mẽ cho các nhà phát triển làm việc với các tệp Microsoft Project, cho phép họ thao tác, chuyển đổi và quản lý các tác vụ dự án một cách liền mạch trong các ứng dụng .NET của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào sử dụng Aspose.Tasks cho .NET để lưu các tùy chọn MS Project dưới dạng hình ảnh, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### 1. Cài đặt Aspose.Tasks cho .NET
Để bắt đầu, bạn cần cài đặt Aspose.Tasks for .NET trong môi trường phát triển của mình. Bạn có thể tải xuống thư viện từ[trang mạng](https://releases.aspose.com/tasks/net/) và làm theo hướng dẫn cài đặt được cung cấp.
### 2. Lấy giấy phép (Tùy chọn)
 Mặc dù Aspose.Tasks cho .NET có thể được sử dụng mà không cần giấy phép trong chế độ đánh giá, nhưng bạn nên lấy giấy phép để có đầy đủ chức năng và loại bỏ các giới hạn đánh giá. Bạn có thể nhận được giấy phép từ[trang mua hàng](https://purchase.aspose.com/buy) hoặc chọn một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) cho mục đích thử nghiệm.
### 3. Kiến thức cơ bản về phát triển C# và .NET
Cần có hiểu biết cơ bản về ngôn ngữ lập trình C# và .NET framework để làm theo các ví dụ và tích hợp các chức năng Aspose.Tasks vào ứng dụng của bạn một cách hiệu quả.
## Nhập không gian tên
Trước khi chúng tôi bắt đầu lưu các tùy chọn MS Project dưới dạng hình ảnh bằng Aspose.Tasks cho .NET, hãy đảm bảo chúng tôi nhập các vùng tên cần thiết vào dự án C# của mình:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Bước 1: Thiết lập đường dẫn thư mục tài liệu
Đảm bảo bạn có một thư mục được chỉ định cho tài liệu của mình và đặt đường dẫn phù hợp:
```csharp
String DataDir = "Your Document Directory";
```
## Bước 2: Tải tệp dự án MS
 Khởi tạo một cái mới`Project` đối tượng bằng cách tải tệp MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Bước 3: Xác định tùy chọn lưu hình ảnh
 Tạo một thể hiện của`ImageSaveOptions`và chỉ định các cài đặt mong muốn:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Bước 4: Chỉ định trang để lưu
Nếu cần, hãy chỉ định các trang sẽ được lưu. Trong ví dụ này, chúng tôi đang thêm trang 2:
```csharp
options.Pages.Add(2);
```
## Bước 5: Lưu hình ảnh
Cuối cùng, lưu các trang đã chọn dưới dạng hình ảnh với các tùy chọn được chỉ định:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Phần kết luận
Aspose.Tasks for .NET đơn giản hóa quá trình làm việc với các tệp MS Project, cho phép các nhà phát triển dễ dàng thao tác các tác vụ dự án. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể lưu các tùy chọn MS Project dưới dạng hình ảnh một cách hiệu quả trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks cho .NET mà không cần giấy phép không?
Trả lời: Có, bạn có thể sử dụng Aspose.Tasks cho .NET mà không cần giấy phép ở chế độ đánh giá. Tuy nhiên, bạn nên có giấy phép để có đầy đủ chức năng và loại bỏ các giới hạn đánh giá.
### Câu hỏi 2: Làm cách nào tôi có thể xin được giấy phép thử nghiệm tạm thời?
 Đáp: Bạn có thể xin giấy phép tạm thời cho mục đích thử nghiệm từ[trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).
### Câu hỏi 3: Aspose.Tasks dành cho .NET có tương thích với các khung .NET khác không?
Trả lời: Có, Aspose.Tasks cho .NET tương thích với nhiều khung .NET khác nhau, bao gồm .NET Core và .NET Standard.
### Q4: Tôi có thể tùy chỉnh thêm các tùy chọn lưu hình ảnh không?
Trả lời: Có, bạn có thể tùy chỉnh các tùy chọn lưu hình ảnh theo yêu cầu cụ thể của mình, chẳng hạn như điều chỉnh kích thước trang, độ phân giải hoặc định dạng đầu ra.
### Câu hỏi 5: Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho .NET ở đâu?
 Trả lời: Bạn có thể tìm thấy sự hỗ trợ và trợ giúp dành cho Aspose.Tasks for .NET trên[diễn đàn](https://forum.aspose.com/c/tasks/15).