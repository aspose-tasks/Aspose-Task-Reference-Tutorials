---
title: Quản lý giá trị phác thảo dự án MS với Aspose.Tasks
linktitle: Bộ sưu tập các giá trị phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách quản lý các giá trị phác thảo trong tệp Microsoft Project bằng Aspose.Tasks cho .NET. Hướng dẫn từng bước với các ví dụ về mã.
weight: 17
url: /vi/net/outline-code-page-settings/outline-value-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý giá trị phác thảo dự án MS với Aspose.Tasks

## Giới thiệu
Aspose.Tasks for .NET cung cấp một bộ tính năng toàn diện để tương tác với các tệp Microsoft Project. Một tính năng như vậy là khả năng quản lý các giá trị phác thảo trong một dự án. Trong hướng dẫn này, chúng ta sẽ khám phá cách thu thập và thao tác các giá trị phác thảo bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Aspose.Tasks for .NET: Bạn có thể tải xuống thư viện từ[đây](https://releases.aspose.com/tasks/net/).
2. Môi trường phát triển: Đảm bảo bạn đã cài đặt IDE phù hợp, chẳng hạn như Visual Studio.
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# sẽ có lợi.
## Nhập không gian tên
Trong tệp mã C# của bạn, hãy nhập các không gian tên cần thiết để truy cập các lớp và phương thức Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Hãy chia ví dụ được cung cấp thành nhiều bước:
## Bước 1: Tải tệp dự án
 Đầu tiên, khởi tạo một`Project` đối tượng bằng cách tải tệp Microsoft Project hiện có:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Bước 2: Xóa các giá trị phác thảo hiện có
Tiếp theo, xóa mọi giá trị phác thảo hiện có khỏi dự án:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Bước 3: Xác định mã phác thảo mới
Bây giờ, hãy xác định mã phác thảo mới với mô tả và giá trị:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Bước 4: Cập nhật giá trị phác thảo
Cập nhật giá trị của mã phác thảo:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Bước 5: Lặp lại các giá trị phác thảo
Lặp lại các giá trị phác thảo và in chi tiết của chúng:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Bước 6: Thao tác các giá trị phác thảo
Thực hiện các thao tác như xóa, chèn và sao chép các giá trị phác thảo nếu cần:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách làm việc với các giá trị phác thảo trong tệp Microsoft Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể quản lý hiệu quả các giá trị phác thảo trong dự án của mình, cho phép kiểm soát và linh hoạt hơn.
## Câu hỏi thường gặp
### Hỏi: Tôi có thể thao tác đồng thời nhiều mã phác thảo không?
Trả lời: Có, bạn có thể xác định và thao tác nhiều mã phác thảo trong một dự án bằng Aspose.Tasks.
### Câu hỏi: Aspose.Tasks có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP và XML.
### Câu hỏi: Làm cách nào để xử lý lỗi khi làm việc với các giá trị phác thảo?
Trả lời: Bạn có thể triển khai các cơ chế xử lý lỗi như khối thử bắt để quản lý các ngoại lệ một cách khéo léo.
### Câu hỏi: Tôi có thể tùy chỉnh giao diện của các giá trị phác thảo trong dự án của mình không?
Trả lời: Có, Aspose.Tasks cung cấp các API mở rộng để tùy chỉnh giao diện và hành vi của các giá trị phác thảo theo yêu cầu của bạn.
### Câu hỏi: Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Tasks ở đâu?
 Đáp: Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ cộng đồng và khám phá[tài liệu](https://reference.aspose.com/tasks/net/) để biết thông tin chi tiết về API và tính năng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
