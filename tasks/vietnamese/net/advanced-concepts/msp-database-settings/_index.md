---
title: Cài đặt cho Cơ sở dữ liệu Microsoft Project trong Aspose.Tasks
linktitle: Cài đặt cho Cơ sở dữ liệu Microsoft Project trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách định cấu hình cài đặt cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks để tích hợp liền mạch vào các ứng dụng .NET.
weight: 19
url: /vi/net/advanced-concepts/msp-database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cài đặt cho Cơ sở dữ liệu Microsoft Project trong Aspose.Tasks

## Giới thiệu

Nếu bạn đang làm việc với cơ sở dữ liệu Microsoft Project trong các ứng dụng .NET bằng Aspose.Tasks, bạn sẽ cần định cấu hình các cài đặt cần thiết để nhập dữ liệu dự án một cách liền mạch. Hướng dẫn này sẽ hướng dẫn bạn từng bước thực hiện quy trình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks từ[đây](https://releases.aspose.com/tasks/net/).
2. Quyền truy cập vào Cơ sở dữ liệu Microsoft Project: Bạn phải có quyền truy cập vào cơ sở dữ liệu Microsoft Project để nhập dữ liệu từ đó.

## Nhập không gian tên

Trước tiên, hãy đảm bảo bạn nhập các không gian tên cần thiết vào dự án của mình:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Bước 1: Tạo chuỗi kết nối

Xây dựng chuỗi kết nối tới cơ sở dữ liệu Microsoft Project của bạn. Đây là một ví dụ:

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

Đảm bảo thay thế các giá trị giữ chỗ bằng thông tin xác thực cơ sở dữ liệu thực tế của bạn.

## Bước 2: Định cấu hình MspDbSettings

 Tạo một thể hiện của`MspDbSettings` và chỉ định chuỗi kết nối cùng với GUID dự án:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Bước 3: Tải dữ liệu dự án

 Khởi tạo một`Project` đối tượng bằng cách sử dụng các cài đặt đã định cấu hình:

```csharp
var project = new Project(settings);
```

## Bước 4: Lưu dữ liệu dự án

Lưu dữ liệu dự án đã tải vào một tệp:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách định cấu hình cài đặt để truy cập cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể nhập dữ liệu dự án vào ứng dụng của mình một cách liền mạch, tạo điều kiện quản lý dự án hiệu quả.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks với các phiên bản cơ sở dữ liệu Microsoft Project khác nhau không?

Trả lời 1: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của cơ sở dữ liệu Microsoft Project, cho phép tích hợp linh hoạt.

### Câu hỏi 2: Làm cách nào để khắc phục sự cố kết nối với cơ sở dữ liệu?

 Câu trả lời 2: Đảm bảo rằng chuỗi kết nối của bạn được đặt cấu hình chính xác với thông tin xác thực và chi tiết cơ sở dữ liệu phù hợp. Bạn cũng có thể tham khảo tài liệu hoặc tìm kiếm sự hỗ trợ từ[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Câu hỏi 3: Có phiên bản dùng thử cho Aspose.Tasks không?

 Câu trả lời 3: Có, bạn có thể truy cập phiên bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).

### Câu hỏi 4: Tôi có thể tùy chỉnh lược đồ để tương tác với cơ sở dữ liệu không?

 Đ4: Có, bạn có thể chỉ định lược đồ cho`MspDbSettings` đối tượng theo cấu trúc cơ sở dữ liệu của bạn.

### Câu hỏi 5: Tôi có thể tìm tài liệu chi tiết hơn về cách sử dụng Aspose.Tasks ở đâu?

 Câu trả lời 5: Bạn có thể khám phá tài liệu toàn diện[đây](https://reference.aspose.com/tasks/net/) để biết thông tin chi tiết về các chức năng của Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
