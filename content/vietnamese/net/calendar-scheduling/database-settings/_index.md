---
title: Cài đặt cơ sở dữ liệu trong Aspose.Tasks
linktitle: Cài đặt cơ sở dữ liệu trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách nhập dự án từ cơ sở dữ liệu Primavera bằng Aspose.Tasks cho .NET. Nhận hướng dẫn từng bước trong hướng dẫn toàn diện này.
type: docs
weight: 29
url: /vi/net/calendar-scheduling/database-settings/
---
## Giới thiệu

Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project trong các ứng dụng .NET của họ. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc nhập các dự án từ cơ sở dữ liệu Primavera bằng Aspose.Tasks.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Visual Studio được cài đặt trên hệ thống của bạn.
-  Aspose.Tasks cho thư viện .NET đã được cài đặt. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
- Truy cập vào cơ sở dữ liệu Primavera, cùng với các quyền cần thiết.

## Nhập không gian tên

Trước tiên, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để làm việc với Aspose.Tasks cho .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Bây giờ, hãy chia mã ví dụ được cung cấp thành nhiều bước:

## Bước 1: Xác định chuỗi kết nối

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 Trong bước này, chúng tôi xác định chuỗi kết nối để kết nối với cơ sở dữ liệu Primavera. Đảm bảo rằng bạn thay thế`DataDir` với thư mục chứa tệp cơ sở dữ liệu của bạn.

## Bước 2: Tạo cài đặt cơ sở dữ liệu

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Ở đây, chúng ta tạo một thể hiện của`PrimaveraDbSettings` class, chuyển chuỗi kết nối và ID dự án làm tham số. Điều chỉnh ID dự án theo yêu cầu của bạn.

## Bước 3: Đặt tên bất biến của nhà cung cấp

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Chỉ định tên bất biến của nhà cung cấp. Trong ví dụ này, chúng tôi đang sử dụng SQLite nhưng bạn có thể thay đổi tùy theo nhà cung cấp cơ sở dữ liệu của mình.

## Bước 4: Tải dự án

```csharp
var project = new Project(settings);
```

 Tạo một cái mới`Project` đối tượng, chuyển các cài đặt cơ sở dữ liệu dưới dạng tham số.

## Bước 5: Lưu dự án

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Cuối cùng, lưu dự án vào vị trí mong muốn với định dạng tệp được chỉ định.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách nhập dự án từ cơ sở dữ liệu Primavera bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể tích hợp liền mạch chức năng nhập dự án vào các ứng dụng .NET của mình.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể nhập dự án từ các nhà cung cấp cơ sở dữ liệu khác nhau bằng Aspose.Tasks cho .NET không?

Câu trả lời 1: Có, bạn có thể nhập dự án từ nhiều nhà cung cấp cơ sở dữ liệu khác nhau bằng cách điều chỉnh chuỗi kết nối và tên bất biến của nhà cung cấp cho phù hợp.

### Câu hỏi 2: Có bản dùng thử miễn phí dành cho Aspose.Tasks dành cho .NET không?

 Câu trả lời 2: Có, bạn có thể dùng thử miễn phí Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/).

### Câu hỏi 3: Tôi có thể tìm tài liệu về Aspose.Tasks cho .NET ở đâu?

 A3: Bạn có thể tìm thấy tài liệu[đây](https://reference.aspose.com/tasks/net/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks cho .NET?

 Câu trả lời 4: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).

### Câu hỏi 5: Tôi có cần giấy phép tạm thời để sử dụng Aspose.Tasks cho .NET không?

 Câu trả lời 5: Nếu bạn muốn đánh giá toàn bộ chức năng của thư viện, bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).