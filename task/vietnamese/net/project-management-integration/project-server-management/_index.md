---
title: Quản lý MS Project Server với Aspose.Tasks
linktitle: Quản lý máy chủ dự án với Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Mở khóa khả năng quản lý MS Project Server liền mạch với Aspose.Tasks cho .NET. Tự động hóa các nhiệm vụ dự án một cách dễ dàng.
type: docs
weight: 23
url: /vi/net/project-management-integration/project-server-management/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc quản lý MS Project Server bằng Aspose.Tasks cho .NET. Aspose.Tasks là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình, cho phép tích hợp và thao tác liền mạch dữ liệu dự án.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào quản lý MS Project Server bằng Aspose.Tasks, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
1. Microsoft Project Server: Bạn cần quyền truy cập vào phiên bản Microsoft Project Server nơi bạn có đặc quyền quản trị hoặc ít nhất là quyền tạo và quản lý dự án.
2.  Aspose.Tasks for .NET Library: Đảm bảo bạn đã tải xuống và cài đặt thư viện Aspose.Tasks for .NET. Bạn có thể tải nó xuống từ[trang mạng](https://releases.aspose.com/tasks/net/).
3. Thông tin xác thực: Lấy thông tin xác thực cần thiết để xác thực với phiên bản MS Project Server của bạn. Điều này thường bao gồm tên người dùng và mật khẩu.
## Nhập không gian tên
Trước khi bắt đầu, hãy đảm bảo bạn đã nhập các vùng tên được yêu cầu trong mã C# của mình:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.IO;
    using System.Net;
    
```
## Bước 1: Thiết lập thông tin xác thực
Trước tiên, bạn cần thiết lập thông tin xác thực để kết nối với phiên bản MS Project Server của mình. Điều này bao gồm địa chỉ tên miền, tên người dùng và mật khẩu.
```csharp
const string sharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(sharepointDomainAddress, UserName, Password);
```
## Bước 2: Tải dự án
Tiếp theo, tải tệp MS Project mà bạn muốn quản lý bằng Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Bước 3: Tạo Trình quản lý máy chủ dự án
 Khởi tạo một`ProjectServerManager` đối tượng bằng cách sử dụng thông tin xác thực được xác định trước đó.
```csharp
var manager = new ProjectServerManager(credentials);
```
## Bước 4: Xác định tùy chọn lưu
Xác định bất kỳ tùy chọn lưu cụ thể nào cho dự án của bạn. Ví dụ: bạn có thể đặt thời gian chờ cho thao tác.
```csharp
var options = new ProjectServerSaveOptions
{
    Timeout = TimeSpan.FromSeconds(10)
};
```
## Bước 5: Tạo hoặc cập nhật dự án
Cuối cùng, tạo hoặc cập nhật dự án trên MS Project Server.
```csharp
manager.CreateNewProject(project, options);
```
Chúc mừng! Bạn đã quản lý thành công MS Project Server bằng Aspose.Tasks for .NET.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách quản lý MS Project Server theo chương trình bằng cách sử dụng Aspose.Tasks cho .NET. Với các bước được cung cấp, bạn có thể tích hợp liền mạch Aspose.Tasks vào các ứng dụng .NET của mình để tự động hóa các tác vụ quản lý dự án trên MS Project Server.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản của Microsoft Project Server không?
Trả lời: Aspose.Tasks hỗ trợ tích hợp với nhiều phiên bản khác nhau của Microsoft Project Server, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Câu hỏi: Tôi có thể thực hiện các thao tác hàng loạt trên các dự án bằng Aspose.Tasks không?
Trả lời: Có, Aspose.Tasks cho phép bạn thực hiện các thao tác hàng loạt như tạo, cập nhật và xóa dự án trên MS Project Server.
### Câu hỏi: Aspose.Tasks có hỗ trợ lập kế hoạch dự án và quản lý tài nguyên không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks cung cấp hỗ trợ toàn diện cho các chức năng lập lịch dự án, phân bổ nguồn lực và quản lý tác vụ.
### Câu hỏi: Có thể tự động hóa các tác vụ báo cáo bằng Aspose.Tasks không?
Trả lời: Có, Aspose.Tasks cho phép bạn tự động hóa việc tạo báo cáo tùy chỉnh dựa trên dữ liệu dự án, tạo điều kiện thuận lợi cho việc giám sát và phân tích dự án hiệu quả.
### Hỏi: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?
 Trả lời: Có, bạn có thể khám phá các khả năng của Aspose.Tasks bằng cách truy cập bản dùng thử miễn phí từ[trang mạng](https://purchase.aspose.com/temporary-license/).