---
title: Lưu tệp dự án MS ở các định dạng khác nhau trong Aspose.Tasks
linktitle: Lưu tệp ở nhiều định dạng khác nhau trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách lưu tệp MS Project ở nhiều định dạng khác nhau bằng Aspose.Tasks cho .NET. Các bước đơn giản để quản lý dự án hiệu quả
type: docs
weight: 17
url: /vi/net/rate-recurring-tasks/save-file-formats/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách lưu tệp Microsoft Project ở nhiều định dạng khác nhau bằng Aspose.Tasks cho .NET. Aspose.Tasks là một API mạnh mẽ cho phép các nhà phát triển thao tác và quản lý các tệp dự án theo chương trình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Aspose.Tasks for .NET: Tải xuống và cài đặt Aspose.Tasks cho .NET từ[đây](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển .NET, chẳng hạn như Visual Studio.
3. Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.

## Nhập không gian tên
Đảm bảo nhập các không gian tên cần thiết ở đầu tệp C# của bạn:
```csharp

using Aspose.Tasks.Saving;
```
## Bước 1: Tạo đối tượng dự án
Đầu tiên, tạo một đối tượng Project và tải tệp Microsoft Project của bạn.
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Bước 2: Lưu dự án ở định dạng CSV
Bây giờ, hãy lưu dự án ở định dạng CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Bước 3: Khám phá các định dạng khác
 Aspose.Tasks hỗ trợ nhiều định dạng khác nhau để lưu tệp dự án, chẳng hạn như XML, PDF, XLSX, v.v. Bạn có thể khám phá các định dạng này bằng cách thay đổi`SaveFileFormat` tham số trong`Save` phương pháp.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Bằng cách làm theo các bước này, bạn có thể dễ dàng lưu tệp Microsoft Project ở nhiều định dạng khác nhau bằng Aspose.Tasks cho .NET.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách lưu tệp MS Project ở các định dạng khác nhau bằng Aspose.Tasks cho .NET. Aspose.Tasks đơn giản hóa quá trình thao tác các tệp dự án theo chương trình, mang lại sự linh hoạt và hiệu quả cho các nhà phát triển.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có tương thích với tất cả các phiên bản Microsoft Project không?
Trả lời: Aspose.Tasks hỗ trợ các định dạng Microsoft Project 2003 XML, Microsoft Project 2007 MPP và Microsoft Project 2010 MPP.
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?
 Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Tasks?
Trả lời: Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Câu hỏi: Có giấy phép tạm thời cho Aspose.Tasks không?
 Đáp: Có, giấy phép tạm thời được cấp cho mục đích đánh giá. Bạn có thể có được một[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Giá của Aspose.Tasks là bao nhiêu?
 Trả lời: Bạn có thể tìm thấy thông tin về giá trên trang mua hàng Aspose.Tasks[đây](https://purchase.aspose.com/buy).