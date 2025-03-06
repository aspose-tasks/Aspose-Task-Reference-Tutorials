---
title: Máy chủ Lưu tùy chọn dự án MS cho Aspose.Tasks
linktitle: Tùy chọn lưu máy chủ dự án cho Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách lưu các tùy chọn Microsoft Project cho Aspose.Tasks bằng cách tích hợp Project Server. Tăng cường quy trình quản lý dự án của bạn.
weight: 16
url: /vi/net/saving-options/project-server-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Máy chủ Lưu tùy chọn dự án MS cho Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc lưu các tùy chọn Microsoft Project cho Aspose.Tasks bằng Project Server. Aspose.Tasks là một API .NET mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình. Tận dụng các khả năng của Project Server, chúng tôi có thể tích hợp liền mạch Aspose.Tasks vào quy trình quản lý dự án của mình. Hướng dẫn này sẽ hướng dẫn bạn từng bước thực hiện quy trình.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Aspose.Tasks cho .NET: Cài đặt Aspose.Tasks cho .NET từ[Liên kết tải xuống](https://releases.aspose.com/tasks/net/).
   
2. Truy cập vào Máy chủ dự án: Bạn sẽ cần thông tin xác thực truy cập và URL của phiên bản Máy chủ dự án của bạn. Nếu chưa có, bạn có thể dùng thử miễn phí từ[đây](https://releases.aspose.com/).
3. Tệp dự án Microsoft: Chuẩn bị tệp Microsoft Project (.mpp) mà bạn muốn lưu bằng Aspose.Tasks.

## Nhập không gian tên
Trước tiên, bạn cần nhập các không gian tên cần thiết trong dự án của mình:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Bước 1: Khởi tạo dự án và thông tin xác thực
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Đảm bảo bạn thay thế`"Your Document Directory"`, `URL`, `Domain`, `UserName` , Và`Password` với giá trị thực tế của bạn.
## Bước 2: Tạo Trình quản lý máy chủ dự án
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Bước 3: Xác định tùy chọn lưu
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Điều chỉnh`ProjectGuid`, `ProjectName`, `Timeout` , Và`PollingInterval` theo yêu cầu của bạn.
## Bước 4: Lưu dự án vào máy chủ
```csharp
manager.CreateNewProject(project, options);
```
Điều này sẽ lưu dự án vào Project Server với các tùy chọn đã chỉ định.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách lưu các tùy chọn Microsoft Project cho Aspose.Tasks bằng cách sử dụng tích hợp Project Server. Bằng cách làm theo các bước này, bạn có thể kết hợp liền mạch Aspose.Tasks vào quy trình quản lý dự án của mình, nâng cao hiệu quả và năng suất.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks với các phiên bản khác nhau của Microsoft Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.
### Câu hỏi: Có phiên bản dùng thử cho Aspose.Tasks không?
 Trả lời: Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.Tasks từ[đây](https://releases.aspose.com/).
### Câu hỏi: Aspose.Tasks có hỗ trợ đa luồng không?
Trả lời: Có, Aspose.Tasks được thiết kế an toàn theo luồng, cho phép truy cập đồng thời vào dữ liệu dự án.
### Câu hỏi: Tôi có thể tùy chỉnh các tùy chọn lưu khi sử dụng tích hợp Project Server không?
Trả lời: Có, bạn có thể điều chỉnh các tùy chọn lưu như tên dự án, thời gian chờ và khoảng thời gian bỏ phiếu cho phù hợp với yêu cầu của bạn.
### Câu hỏi: Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?
 Đáp: Bạn có thể tìm thấy sự hỗ trợ và trợ giúp trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
