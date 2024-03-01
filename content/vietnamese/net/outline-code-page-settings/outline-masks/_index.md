---
title: Làm chủ các mặt nạ phác thảo của Microsoft Project trong Aspose.Tasks
linktitle: Làm việc với Mặt nạ phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách làm việc với các tệp Microsoft Project theo chương trình bằng Aspose.Tasks cho .NET. Làm chủ phác thảo mặt nạ một cách hiệu quả.
type: docs
weight: 14
url: /vi/net/outline-code-page-settings/outline-masks/
---
## Giới thiệu
Trong lĩnh vực quản lý dự án và theo dõi nhiệm vụ, Microsoft Project được coi là công cụ nền tảng. Tuy nhiên, khi nói đến việc thao tác và quản lý các tệp dự án theo chương trình, Aspose.Tasks for .NET nổi lên như một giải pháp mạnh mẽ. Hướng dẫn này sẽ đi sâu vào một khía cạnh cụ thể khi làm việc với các tệp MS Project bằng Aspose.Tasks for .NET: xử lý các mặt nạ phác thảo.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có những điều sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình C#.
- Đã cài đặt Visual Studio với .NET framework.
- Làm quen với các định dạng tệp Microsoft Project.
-  Đã tải xuống và cài đặt Aspose.Tasks cho thư viện .NET. Nếu không, bạn có thể lấy nó[đây](https://releases.aspose.com/tasks/net/).
- Hiểu biết cơ bản về các khái niệm quản lý dự án.
## Nhập không gian tên
Trước khi tiếp tục hướng dẫn, hãy nhập các vùng tên cần thiết vào tệp C# của bạn:
```csharp
    
```
## Bước 1: Tải tệp dự án
Bước đầu tiên là tải tệp Microsoft Project bằng thư viện Aspose.Tasks.
```csharp
// Đường dẫn đến thư mục tài liệu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Bước 2: Xác định mã phác thảo
Tiếp theo, xác định định nghĩa mã phác thảo cho dự án.
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
project.OutlineCodes.Add(outline);
```
## Bước 3: Xác định mặt nạ phác thảo
Bây giờ, tạo mặt nạ phác thảo cho mã phác thảo.
```csharp
var mask = new OutlineMask();
// Đặt loại mặt nạ
mask.Type = MaskType.Characters;
// Đặt dấu phân cách của các giá trị mã
mask.Separator = "/";
// Đặt mức độ của mặt nạ
mask.Level = 1;
// Đặt độ dài tối đa (tính bằng ký tự) của các giá trị mã phác thảo. 0 nếu độ dài không được xác định.
mask.Length = 2;
// Thêm mặt nạ vào định nghĩa
outline.Masks.Add(mask);
```
## Bước 4: Xác định giá trị phác thảo
Xác định giá trị phác thảo cho mã phác thảo.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
Hướng dẫn từng bước này bao gồm quá trình làm việc với mặt nạ phác thảo trong Aspose.Tasks cho .NET. Bằng cách làm theo các bước này, bạn có thể quản lý hiệu quả các mặt nạ phác thảo trong tệp Microsoft Project của mình theo chương trình.

## Phần kết luận
Việc thành thạo thao tác trên các tệp Microsoft Project theo chương trình sẽ mở ra nhiều khả năng trong tự động hóa quản lý dự án. Với Aspose.Tasks cho .NET, việc xử lý các mặt nạ phác thảo trở nên hợp lý và hiệu quả, trao quyền cho các nhà phát triển tạo ra các giải pháp phù hợp để theo dõi và quản lý dự án.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với các công cụ quản lý dự án khác không?
Đ: Chắc chắn rồi! Mặc dù Aspose.Tasks chủ yếu tập trung vào các tệp Microsoft Project, nhưng nó cung cấp khả năng tương tác với các định dạng quản lý dự án khác nhau.
### Câu hỏi: Aspose.Tasks có hỗ trợ cả đọc và ghi tệp Microsoft Project không?
Trả lời: Có, Aspose.Tasks cho phép các nhà phát triển vừa đọc vừa ghi vào tệp Microsoft Project, cho phép thao tác toàn diện.
### Câu hỏi: Có diễn đàn cộng đồng nào dành cho Aspose.Tasks để tôi có thể tìm kiếm trợ giúp không?
A: Thật vậy, bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi, chia sẻ ý tưởng và tương tác với những người dùng khác.
### Câu hỏi: Tôi có thể dùng thử Aspose.Tasks cho .NET trước khi mua không?
 Đ: Tất nhiên! Bạn có thể truy cập bản dùng thử miễn phí của Aspose.Tasks[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể lấy giấy phép tạm thời cho Aspose.Tasks ở đâu?
 Đáp: Nếu bạn cần giấy phép tạm thời cho mục đích đánh giá hoặc thử nghiệm, bạn có thể lấy một giấy phép[đây](https://purchase.aspose.com/temporary-license/).