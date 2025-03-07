---
title: Quản lý ngoại lệ trực tuyến của MS Project trong Aspose.Tasks
linktitle: Làm việc với các ngoại lệ của Project Online trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý các trường hợp ngoại lệ của Microsoft Project Online một cách liền mạch với Aspose.Tasks dành cho .NET. Hướng dẫn từng bước để quản lý dự án hiệu quả.
weight: 21
url: /vi/net/project-management-integration/project-online-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý ngoại lệ trực tuyến của MS Project trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào sự phức tạp của việc xử lý các ngoại lệ của Microsoft Project Online bằng Aspose.Tasks cho .NET. Aspose.Tasks là một API .NET mạnh mẽ cho phép các nhà phát triển thao tác và quản lý các tệp Microsoft Project một cách dễ dàng. Chúng tôi sẽ hướng dẫn từng bước quy trình này, đảm bảo hiểu biết toàn diện về cách làm việc với các ngoại lệ của MS Project Online trong các ứng dụng .NET của bạn.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:

## Nhập không gian tên
1. Aspose.Tasks: Nhập không gian tên Aspose.Tasks để truy cập chức năng do API Aspose.Tasks cung cấp.
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Net;

```

## Bước 1: Thiết lập thư mục tài liệu
 Đảm bảo bạn có một thư mục được chỉ định để làm việc với các tệp Dự án của mình. Thay thế`"Your Document Directory"` với đường dẫn đến thư mục tài liệu của bạn.
```csharp
String DataDir = "Your Document Directory";
```
## Bước 2: Xác định thông tin xác thực máy chủ dự án
Thiết lập URL, tên miền, tên người dùng và mật khẩu cho Máy chủ dự án của bạn.
```csharp
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
```
## Bước 3: Tải tệp dự án
Tải tệp Microsoft Project của bạn bằng Aspose.Tasks.
```csharp
var project = new Project(DataDir + @"Project1.mpp");
```
## Bước 4: Đặt thông tin xác thực Windows
Tạo thông tin đăng nhập mạng bằng tên người dùng, mật khẩu và tên miền được cung cấp.
```csharp
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
```
## Bước 5: Đặt thông tin xác thực máy chủ dự án
Tạo thông tin xác thực Project Server bằng cách sử dụng URL và thông tin xác thực Windows.
```csharp
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
## Bước 6: Khởi tạo Trình quản lý máy chủ dự án
Khởi tạo đối tượng Project Server Manager với thông tin xác thực Project Server.
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Bước 7: Tạo dự án mới
Tạo một dự án mới trên Project Server bằng cách sử dụng đối tượng Project đã tải.
```csharp
manager.CreateNewProject(project);
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách làm việc với các ngoại lệ của MS Project Online bằng Aspose.Tasks cho .NET. Với kiến thức này, bạn có thể xử lý các trường hợp ngoại lệ và quản lý các tệp Microsoft Project một cách hiệu quả trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các công cụ quản lý dự án khác không?
Trả lời: Có, Aspose.Tasks cung cấp hỗ trợ rộng rãi để làm việc với nhiều định dạng tệp quản lý dự án khác nhau, bao gồm Microsoft Project, Primavera, v.v.
### Câu hỏi: Aspose.Tasks có bản dùng thử miễn phí không?
 Trả lời: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Tasks từ[trang mạng](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm tài liệu về Aspose.Tasks ở đâu?
 Đáp: Đã có tài liệu chi tiết về Aspose.Tasks[đây](https://reference.aspose.com/tasks/net/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?
Trả lời: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Làm cách nào để mua giấy phép cho Aspose.Tasks?
 Trả lời: Bạn có thể mua giấy phép cho Aspose.Tasks từ[trang mua hàng](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
