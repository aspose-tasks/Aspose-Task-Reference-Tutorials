---
title: Định nghĩa xử lý mã phác thảo dự án MS trong Aspose.Tasks
linktitle: Xử lý các định nghĩa mã phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách xử lý các định nghĩa mã phác thảo MS Project bằng Aspose.Tasks cho .NET, trao quyền cho các ứng dụng quản lý dự án của bạn.
weight: 12
url: /vi/net/outline-code-page-settings/outline-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Định nghĩa xử lý mã phác thảo dự án MS trong Aspose.Tasks

## Giới thiệu
Microsoft Project là một công cụ mạnh mẽ để quản lý dự án và Aspose.Tasks dành cho .NET cung cấp hỗ trợ toàn diện để thao tác các tệp dự án theo chương trình. Một khía cạnh thiết yếu của quản lý dự án là tổ chức các nhiệm vụ bằng cách sử dụng mã phác thảo. Trong hướng dẫn này, chúng ta sẽ khám phá cách xử lý các định nghĩa mã phác thảo MS Project bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào triển khai, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
### 1. Cài đặt Aspose.Tasks cho .NET
 Đảm bảo bạn đã cài đặt Aspose.Tasks for .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/net/).
### 2. Hiểu biết cơ bản về C# và .NET Framework
Làm quen với ngôn ngữ lập trình C# và .NET framework vì hướng dẫn này yêu cầu kiến thức C# ở trình độ trung cấp.
### 3. Môi trường phát triển tích hợp (IDE)
Hãy cài đặt một IDE như Visual Studio trên hệ thống của bạn để mã hóa và gỡ lỗi.
## Nhập không gian tên
Trước khi bắt đầu viết mã, hãy nhập các không gian tên cần thiết để làm việc với Aspose.Tasks cho .NET.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước để hiểu rõ hơn.
## Bước 1: Tải tệp dự án
Đầu tiên, chúng ta cần tải tệp MS Project vào ứng dụng của mình.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Bước 2: Tạo định nghĩa mã phác thảo
Bây giờ, hãy tạo một định nghĩa mã phác thảo mới.
```csharp
var outline = new OutlineCodeDefinition();
```
## Bước 3: Đặt số và tên trường
Đặt số trường và tên cho mã phác thảo.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## Bước 4: Đặt GUID và các thuộc tính khác
Đặt GUID và các thuộc tính khác của mã phác thảo.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Bước 5: Thêm mặt nạ phác thảo
Thêm mặt nạ phác thảo vào mã phác thảo.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Bước 6: Đặt thuộc tính khác
Đặt thuộc tính bổ sung của mã phác thảo.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Bước 7: Thêm giá trị phác thảo
Cuối cùng, hãy thêm giá trị phác thảo vào mã phác thảo.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách xử lý các định nghĩa mã phác thảo MS Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể thao tác hiệu quả các mã phác thảo trong tệp dự án của mình theo chương trình.
## Câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks cho .NET với các phiên bản khác nhau của tệp MS Project không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của tệp MS Project, bao gồm các định dạng MPP và XML.
### Câu hỏi 2: Aspose.Tasks dành cho .NET có tương thích với .NET Core không?
Trả lời: Có, Aspose.Tasks for .NET tương thích với .NET Core, cho phép bạn phát triển các ứng dụng đa nền tảng.
### Câu hỏi 3: Tôi có thể thao tác các thao tác gán tài nguyên bằng Aspose.Tasks cho .NET không?
Trả lời: Có, Aspose.Tasks cho .NET cung cấp các tính năng mở rộng để thao tác các nhiệm vụ tài nguyên, bao gồm thêm, cập nhật và xóa các nhiệm vụ.
### Câu hỏi 4: Aspose.Tasks dành cho .NET có hỗ trợ đọc các trường tùy chỉnh từ tệp MS Project không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks dành cho .NET hỗ trợ đọc và ghi các trường tùy chỉnh, bao gồm mã phác thảo, từ các tệp MS Project.
### Câu hỏi 5: Có diễn đàn cộng đồng nào dành cho Aspose.Tasks dành cho .NET không?
 Trả lời: Có, bạn có thể tham gia diễn đàn cộng đồng Aspose.Tasks for .NET[đây](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi, chia sẻ kiến thức và cộng tác với các nhà phát triển khác.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
