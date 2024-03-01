---
title: Quản lý bộ sưu tập tài nguyên dự án trong Aspose.Tasks
linktitle: Quản lý bộ sưu tập tài nguyên trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý hiệu quả các bộ sưu tập tài nguyên Microsoft Project trong .NET bằng API Aspose.Tasks. Tăng năng suất và tính linh hoạt.
type: docs
weight: 13
url: /vi/net/resource-risk-analysis/managing-resource-collection/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý hiệu quả các bộ sưu tập tài nguyên Microsoft Project bằng Aspose.Tasks cho .NET. Aspose.Tasks là một API mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình, cho phép tích hợp và thao tác liền mạch dữ liệu dự án.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1. Kiến thức về C# và .NET Framework: Hướng dẫn này đòi hỏi sự quen thuộc với ngôn ngữ lập trình C# và .NET Framework.
2. Cài đặt Aspose.Tasks cho .NET: Đảm bảo bạn đã cài đặt Aspose.Tasks cho .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
3. Thiết lập môi trường phát triển: Thiết lập môi trường phát triển của bạn với Visual Studio hoặc bất kỳ IDE ưa thích nào khác.

## Nhập không gian tên
Trước khi chúng ta bắt đầu, hãy nhập các không gian tên cần thiết để truy cập các chức năng của Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Bước 1: Tải tệp dự án
Đầu tiên, tải tệp Microsoft Project vào đối tượng dự án Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Bước 2: Thêm tài nguyên trống
Tiếp theo, hãy thêm một tài nguyên trống vào dự án:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Bước 3: Thêm tài nguyên có tên
Bây giờ, hãy thêm tài nguyên có tên được chỉ định vào dự án:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Bước 4: Thêm tài nguyên trước tài nguyên khác
Thêm tài nguyên có tên được chỉ định trước tài nguyên khác dựa trên ID của nó:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Bước 5: Truy cập tài nguyên bằng ID hoặc UID
Bạn có thể truy cập tài nguyên bằng ID hoặc UID của họ:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Bước 6: In thông tin tài nguyên
In thông tin về các tài nguyên của dự án:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Bước 7: Xóa tài nguyên
Xóa tài nguyên khỏi dự án:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Phần kết luận
Quản lý bộ sưu tập tài nguyên Microsoft Project bằng Aspose.Tasks cho .NET cung cấp cho các nhà phát triển một bộ công cụ mạnh mẽ để xử lý hiệu quả tài nguyên dự án theo chương trình. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể thao tác liền mạch các tài nguyên trong dự án của mình, nâng cao năng suất và tính linh hoạt trong các nhiệm vụ quản lý dự án.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Tasks có thể xử lý các tệp dự án quy mô lớn không?

Trả lời: Có, Aspose.Tasks được thiết kế để xử lý các tệp dự án quy mô lớn một cách hiệu quả, mang lại hiệu suất và độ tin cậy cao.

### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của Microsoft Project không?

Trả lời: Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của Microsoft Project, đảm bảo khả năng tương thích trên các môi trường khác nhau.

### Câu hỏi: Tôi có thể tùy chỉnh các thuộc tính tài nguyên bằng Aspose.Tasks không?

Trả lời: Hoàn toàn có thể, Aspose.Tasks cung cấp các khả năng mở rộng để tùy chỉnh các thuộc tính tài nguyên theo yêu cầu cụ thể của dự án.

### Câu hỏi: Aspose.Tasks có hỗ trợ đa luồng cho các hoạt động đồng thời không?

Trả lời: Có, Aspose.Tasks hỗ trợ đa luồng, cho phép thực hiện các hoạt động đồng thời trên dữ liệu dự án để cải thiện hiệu suất.

### Câu hỏi: Người dùng Aspose.Tasks có được hỗ trợ kỹ thuật không?

 Trả lời: Có, người dùng Aspose.Tasks có thể truy cập hỗ trợ kỹ thuật thông qua diễn đàn[đây](https://forum.aspose.com/c/tasks/15).