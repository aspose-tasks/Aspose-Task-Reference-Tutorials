---
date: 2026-03-14
description: Tìm hiểu cách chỉ định lược đồ cơ sở dữ liệu cho cơ sở dữ liệu Microsoft
  Project bằng Aspose.Tasks và cách nhập dữ liệu dự án vào các ứng dụng .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Xác định lược đồ cơ sở dữ liệu cho Project DB với Aspose.Tasks
url: /vi/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cài đặt cho Cơ sở dữ liệu Microsoft Project trong Aspose.Tasks

## Giới thiệu

Nếu bạn đang làm việc với cơ sở dữ liệu Microsoft Project trong các ứng dụng .NET sử dụng Aspose.Tasks, bạn sẽ cần **chỉ định schema cơ sở dữ liệu** và cấu hình các thiết lập cần thiết để **nhập dữ liệu project** một cách liền mạch. Hướng dẫn này sẽ chỉ cho bạn từng bước quy trình, bao gồm **cách cấu hình kết nối**, **tạo .NET connection string**, và cuối cùng **lưu project dưới dạng MPP**.

## Câu trả lời nhanh
- **Mục tiêu chính là gì?** Chỉ định schema cơ sở dữ liệu và nhập một Project database vào ứng dụng .NET.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho .NET.  
- **Làm sao để kết nối tới Project Server?** Bằng cách xây dựng một connection string SQL hợp lệ và sử dụng `MspDbSettings`.  
- **Định dạng file được tạo ra là gì?** File MPP được lưu bằng `SaveFileFormat.Mpp`.  
- **Tôi có thể thay đổi tên schema không?** Có, đặt thuộc tính `Schema` trên `MspDbSettings`.

## Cách chỉ định schema cơ sở dữ liệu cho Project DB

Hiểu tại sao bạn có thể cần **chỉ định schema cơ sở dữ liệu** là rất quan trọng. Trong nhiều môi trường doanh nghiệp, cơ sở dữ liệu Project Server nằm dưới một schema tùy chỉnh (ví dụ: `dbo`, `psdata`). Bằng cách thiết lập schema một cách rõ ràng, bạn đảm bảo Aspose.Tasks truy vấn đúng các bảng, tránh lỗi thời gian chạy và đảm bảo việc nhập dữ liệu chính xác.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. Aspose.Tasks cho .NET: Tải và cài đặt thư viện Aspose.Tasks từ [here](https://releases.aspose.com/tasks/net/).  
2. Quyền truy cập vào một Microsoft Project Database: Bạn cần có quyền truy cập vào cơ sở dữ liệu Microsoft Project để nhập dữ liệu.

## Nhập các Namespace

Đầu tiên, hãy chắc chắn rằng bạn đã nhập các namespace cần thiết vào dự án của mình:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Bước 1: Tạo Connection String

Xây dựng connection string tới cơ sở dữ liệu Microsoft Project của bạn. Đây là nơi bạn **tạo .NET connection string** và đồng thời định nghĩa cách **kết nối tới Project Server**.

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

> **Mẹo chuyên nghiệp:** Kiểm tra lại các giá trị `DataSource` và `InitialCatalog`; chúng phải khớp với địa chỉ máy chủ và tên cơ sở dữ liệu đã công bố.

## Bước 2: Cấu hình MspDbSettings

Tạo một thể hiện của `MspDbSettings`, truyền vào connection string, và **chỉ định schema cơ sở dữ liệu** bằng cách đặt thuộc tính `Schema`. Điều này cho Aspose.Tasks biết schema nào sẽ được truy vấn.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Ở đây chúng tôi cũng cung cấp GUID của project để xác định dự án cụ thể mà bạn muốn tải.

## Bước 3: Tải dữ liệu Project

Khởi tạo một đối tượng `Project` bằng cách sử dụng các thiết lập đã cấu hình. Bước này thực hiện **cách nhập dữ liệu project** từ cơ sở dữ liệu vào một đối tượng .NET.

```csharp
var project = new Project(settings);
```

## Bước 4: Lưu dữ liệu Project

Cuối cùng, ghi lại project đã tải vào một file MPP trên đĩa. Điều này minh họa **lưu project dưới dạng MPP** bằng API của Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Sau khi chạy mã, bạn sẽ thấy file `ImportProjectDataFromDatabase_out.mpp` trong thư mục output, sẵn sàng mở bằng Microsoft Project.

## Kết luận

Trong hướng dẫn này, bạn đã học cách **chỉ định schema cơ sở dữ liệu** cho một Microsoft Project database, **cấu hình kết nối**, **nhập dữ liệu project**, và **lưu project dưới dạng MPP** bằng Aspose.Tasks cho .NET. Những bước này cho phép tích hợp liền mạch dữ liệu Project Server vào các ứng dụng tùy chỉnh của bạn, giúp xây dựng các giải pháp quản lý dự án mạnh mẽ.

## Câu hỏi thường gặp

### Q1: Tôi có thể sử dụng Aspose.Tasks với các phiên bản khác nhau của Microsoft Project databases không?
A1: Có, Aspose.Tasks hỗ trợ nhiều phiên bản của Microsoft Project databases, mang lại tính linh hoạt trong việc tích hợp.

### Q2: Làm sao để khắc phục các vấn đề kết nối với cơ sở dữ liệu?
A2: Đảm bảo rằng connection string của bạn được cấu hình đúng với thông tin xác thực và chi tiết cơ sở dữ liệu. Bạn cũng có thể tham khảo tài liệu hoặc tìm hỗ trợ tại [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q3: Có phiên bản dùng thử cho Aspose.Tasks không?
A3: Có, bạn có thể tải phiên bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

### Q4: Tôi có thể tùy chỉnh schema cho việc tương tác với cơ sở dữ liệu không?
A4: Có, bạn có thể chỉ định schema cho đối tượng `MspDbSettings` theo cấu trúc cơ sở dữ liệu của mình.

### Q5: Tôi có thể tìm tài liệu chi tiết hơn về việc sử dụng Aspose.Tasks ở đâu?
A5: Bạn có thể khám phá tài liệu đầy đủ tại [here](https://reference.aspose.com/tasks/net/) để có những hiểu biết sâu hơn về các chức năng của Aspose.Tasks.

**Q: Phương pháp này có hoạt động với Azure SQL databases không?**  
A: Hoàn toàn có thể. Chỉ cần điều chỉnh `DataSource` thành tên máy chủ Azure của bạn và đảm bảo bật cài đặt TLS/SSL.

**Q: Làm sao để xử lý các Project databases lớn mà không bị timeout?**  
A: Tăng giá trị `ConnectTimeout` trong connection string và cân nhắc tải các project theo lô nếu cần.

---

**Last Updated:** 2026-03-14  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}