---
title: Trích xuất thông tin dự án MS trong Aspose.Tasks
linktitle: Trích xuất thông tin dự án trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách trích xuất thông tin MS Project một cách dễ dàng bằng Aspose.Tasks for .NET. Đi sâu vào hướng dẫn toàn diện của chúng tôi.
type: docs
weight: 20
url: /vi/net/project-management-integration/project-information/
---
## Giới thiệu
Bạn đang tìm cách trích xuất thông tin từ các tệp Microsoft Project một cách hiệu quả bằng Aspose.Tasks cho .NET? Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình. Nhưng trước khi đi sâu vào chi tiết triển khai, trước tiên hãy đảm bảo bạn có mọi thứ mình cần.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
### 1. Aspose.Tasks cho .NET
 Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Tasks for .NET. Nếu bạn chưa làm như vậy, bạn có thể tải xuống từ[Aspose.Tasks cho trang web .NET](https://releases.aspose.com/tasks/net/).
### 2. Thông tin xác thực cho SharePoint
Bạn sẽ cần thông tin xác thực để truy cập SharePoint nơi lưu trữ tệp MS Project của bạn. Hãy chắc chắn rằng bạn có những thông tin sau:
- Địa chỉ miền SharePoint
- Tên tài khoản
- Mật khẩu
## Nhập không gian tên
Khi bạn đã sắp xếp xong các điều kiện tiên quyết, đã đến lúc nhập các vùng tên cần thiết vào dự án của bạn.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Bây giờ chúng ta hãy chia quá trình trích xuất thông tin MS Project thành nhiều bước.
## Bước 1: Cung cấp thông tin xác thực
Trước tiên, bạn cần cung cấp thông tin xác thực SharePoint của mình để truy cập Máy chủ dự án.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Bước 2: Khởi tạo Trình quản lý máy chủ dự án
 Tiếp theo, khởi tạo một`ProjectServerManager` ví dụ với thông tin xác thực được cung cấp.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Bước 3: Truy xuất danh sách dự án
Bây giờ, bạn có thể truy xuất danh sách các dự án từ Máy chủ dự án.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Bước 4: In thông tin dự án
Cuối cùng, duyệt qua danh sách các dự án và in thông tin của chúng.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách trích xuất thông tin MS Project bằng Aspose.Tasks cho .NET. Với kiến thức này, giờ đây bạn có thể tích hợp chức năng này vào các ứng dụng .NET của mình một cách liền mạch.
## Câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks cho .NET với bất kỳ phiên bản Microsoft Project nào không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, bao gồm 2003, 2007, 2010, 2013, 2016 và 2019.
### Câu hỏi 2: Aspose.Tasks dành cho .NET có tương thích với cả nền tảng Windows và Linux không?
Trả lời: Có, Aspose.Tasks cho .NET tương thích với cả nền tảng Windows và Linux, khiến nó trở nên linh hoạt cho các môi trường phát triển khác nhau.
### Câu hỏi 3: Tôi có thể trích xuất các phần phụ thuộc của tác vụ bằng Aspose.Tasks cho .NET không?
Đ: Chắc chắn rồi! Aspose.Tasks for .NET cung cấp chức năng mạnh mẽ để trích xuất không chỉ thông tin cơ bản của dự án mà còn cả các phụ thuộc của nhiệm vụ và các chi tiết phức tạp khác.
### Câu hỏi 4: Aspose.Tasks dành cho .NET có cung cấp hỗ trợ kỹ thuật không?
 Đáp: Có, bạn có thể nhận hỗ trợ kỹ thuật cho Aspose.Tasks for .NET thông qua[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15), nơi bạn có thể đặt câu hỏi và tìm kiếm sự trợ giúp từ các chuyên gia.
### Câu hỏi 5: Tôi có thể dùng thử Aspose.Tasks cho .NET trước khi mua không?
 Đ: Chắc chắn rồi! Bạn có thể tận dụng bản dùng thử miễn phí Aspose.Tasks cho .NET từ[trang phát hành](https://releases.aspose.com/), cho phép bạn khám phá các tính năng của nó trước khi đưa ra quyết định mua hàng.