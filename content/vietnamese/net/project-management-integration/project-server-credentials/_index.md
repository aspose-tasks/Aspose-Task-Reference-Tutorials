---
title: Quản lý thông tin xác thực máy chủ MS Project trong Aspose.Tasks
linktitle: Quản lý thông tin xác thực máy chủ dự án trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý thông tin đăng nhập MS Project Server một cách liền mạch với Aspose.Tasks cho .NET. Nâng cao hiệu quả quản lý dự án.
type: docs
weight: 22
url: /vi/net/project-management-integration/project-server-credentials/
---
## Giới thiệu
Trong lĩnh vực quản lý dự án, sự phối hợp hiệu quả và giao tiếp liền mạch là yếu tố then chốt để thực hiện dự án thành công. Aspose.Tasks for .NET cung cấp giải pháp toàn diện để quản lý thông tin đăng nhập Microsoft Project Server, cho phép người dùng truy cập và thao tác dữ liệu dự án một cách an toàn. Hướng dẫn này đi sâu vào quy trình quản lý thông tin đăng nhập MS Project Server bằng Aspose.Tasks cho .NET, hướng dẫn người dùng qua từng bước để đảm bảo trải nghiệm suôn sẻ.
## Điều kiện tiên quyết
Trước khi bắt đầu hành trình quản lý thông tin đăng nhập MS Project Server bằng Aspose.Tasks cho .NET, hãy đảm bảo đáp ứng các điều kiện tiên quyết sau:
### 1. Cài đặt Aspose.Tasks cho .NET
 Để bắt đầu, hãy tải xuống và cài đặt Aspose.Tasks for .NET từ gói được cung cấp[Liên kết tải xuống](https://releases.aspose.com/tasks/net/). Làm theo hướng dẫn cài đặt để tích hợp thư viện vào môi trường .NET của bạn một cách liền mạch.
### 2. Thông tin xác thực truy cập
Thu thập thông tin xác thực cần thiết để truy cập MS Project Server. Điều này bao gồm địa chỉ miền SharePoint, tên người dùng và mật khẩu được liên kết với Máy chủ dự án.

## Nhập không gian tên
Trong dự án .NET của bạn, hãy nhập các vùng tên cần thiết để sử dụng các chức năng do Aspose.Tasks cung cấp cho .NET một cách hiệu quả.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Bước 1: Xác định đường dẫn thư mục tài liệu
```csharp
String DataDir = "Your Document Directory";
```
## Bước 2: Đặt địa chỉ miền SharePoint, tên người dùng và mật khẩu
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Bước 3: Tạo thông tin xác thực máy chủ dự án
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Bước 4: Tải tệp dự án
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Bước 5: Khởi tạo Trình quản lý máy chủ dự án
```csharp
var manager = new ProjectServerManager(credentials);
```
## Bước 6: Tạo dự án mới
```csharp
manager.CreateNewProject(newProject);
```
## Bước 7: Truy xuất danh sách dự án
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Bước 8: Lặp lại danh sách dự án
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Phần kết luận
Quản lý hiệu quả thông tin đăng nhập MS Project Server là điều tối quan trọng để quản lý dự án hợp lý. Aspose.Tasks for .NET đơn giản hóa quy trình này bằng cách cung cấp một bộ chức năng mạnh mẽ. Bằng cách làm theo hướng dẫn từng bước được nêu trong hướng dẫn này, người dùng có thể tích hợp liền mạch Aspose.Tasks cho .NET vào dự án của họ, đảm bảo quyền truy cập và thao tác an toàn đối với dữ liệu dự án.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks dành cho .NET có tương thích với tất cả các phiên bản của Microsoft Project Server không?
Trả lời: Aspose.Tasks for .NET được thiết kế để tương thích với nhiều phiên bản khác nhau của Microsoft Project Server, đảm bảo tính linh hoạt và linh hoạt cho người dùng.
### Câu hỏi: Tôi có thể tích hợp Aspose.Tasks cho .NET vào dự án .NET hiện tại của mình không?
Trả lời: Có, Aspose.Tasks cho .NET có thể được tích hợp liền mạch vào các dự án .NET hiện có, tạo điều kiện thuận lợi cho khả năng quản lý dự án hiệu quả.
### Câu hỏi: Aspose.Tasks cho .NET có hỗ trợ truy cập tài nguyên dự án không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks for .NET cung cấp hỗ trợ toàn diện để truy cập và thao tác các tài nguyên dự án, nâng cao hiệu quả quản lý dự án.
### Câu hỏi: Có bất kỳ tùy chọn cấp phép nào có sẵn cho Aspose.Tasks cho .NET không?
Trả lời: Có, Aspose.Tasks cho .NET cung cấp các tùy chọn cấp phép linh hoạt, bao gồm giấy phép tạm thời cho mục đích dùng thử và giấy phép đầy đủ cho mục đích sử dụng thương mại.
### Câu hỏi: Tôi có thể tìm kiếm sự trợ giúp hoặc hỗ trợ cho Aspose.Tasks cho .NET ở đâu?
 Trả lời: Nếu có bất kỳ thắc mắc hoặc trợ giúp nào về Aspose.Tasks cho .NET, bạn có thể truy cập diễn đàn hỗ trợ tại[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Mã nguồn hoàn chỉnh