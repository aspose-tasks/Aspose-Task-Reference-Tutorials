---
title: Làm chủ mặt nạ phác thảo dự án MS với Aspose.Tasks
linktitle: Bộ sưu tập các mặt nạ phác thảo trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách thao tác với mặt nạ phác thảo của bộ sưu tập MS Project bằng Aspose.Tasks cho .NET. Nâng cao năng suất với hướng dẫn toàn diện này.
weight: 15
url: /vi/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Làm chủ mặt nạ phác thảo dự án MS với Aspose.Tasks

## Giới thiệu
Bạn đang muốn khai thác sức mạnh của mặt nạ phác thảo của Microsoft Project bằng Aspose.Tasks cho .NET? Bạn đã đến đúng nơi! Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn từng bước thực hiện quy trình, đảm bảo bạn hiểu rõ về cách thao tác hiệu quả các mặt nạ phác thảo trong dự án của mình. Cho dù bạn là nhà phát triển dày dạn hay chỉ mới bắt đầu, hướng dẫn này sẽ trang bị cho bạn kiến thức và kỹ năng cần thiết để tối ưu hóa quy trình làm việc của bạn.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
### 1. Cài đặt Aspose.Tasks cho .NET
Đảm bảo rằng bạn đã cài đặt Aspose.Tasks for .NET trong môi trường phát triển của mình. Bạn có thể tải xuống thư viện từ trang web Aspose[đây](https://releases.aspose.com/tasks/net/).
### 2. Kiến thức cơ bản về C# và .NET Framework
Hãy tự làm quen với ngôn ngữ lập trình C# và .NET Framework vì hướng dẫn này sẽ sử dụng cả hai.
### 3. Tệp dự án Microsoft
Chuẩn bị sẵn tệp Microsoft Project (MPP) cho mục đích thử nghiệm. Bạn có thể sử dụng tệp hiện có hoặc tạo tệp mới để thử nghiệm.
## Nhập không gian tên
Hãy bắt đầu bằng cách nhập các không gian tên cần thiết vào dự án C# của bạn. Bước này đảm bảo rằng bạn có quyền truy cập vào các lớp và chức năng cần thiết do Aspose.Tasks cho .NET cung cấp.

Thêm các không gian tên sau vào đầu tệp mã của bạn:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước và giải thích chi tiết từng bước:
## Bước 1: Khởi tạo đối tượng dự án
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Ở đây, chúng ta tạo một phiên bản mới của`Project` class và tải tệp Microsoft Project hiện có có tên "OutlineValues2010.mpp".
## Bước 2: Truy cập mã phác thảo
```csharp
var outline = project.OutlineCodes[0];
```
Chúng tôi truy cập các mã phác thảo từ dự án. Mã phác thảo là các trường tùy chỉnh trong Microsoft Project cho phép bạn phân loại và sắp xếp các nhiệm vụ.
## Bước 3: Xóa mặt nạ phác thảo
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Bước này đảm bảo rằng mọi mặt nạ phác thảo hiện có sẽ bị xóa trước khi tiếp tục.
## Bước 4: Tạo mặt nạ phác thảo
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Chúng tôi tạo các mặt nạ phác thảo mới và chỉ định loại của chúng. Trong ví dụ này, chúng tôi tạo một mặt nạ phác thảo hợp lệ và một mặt nạ sai.
## Bước 5: Chèn và chỉnh sửa mặt nạ
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Ở đây, chúng tôi chèn sai mặt nạ vào bộ sưu tập và chỉnh sửa độ dài của mặt nạ bằng chỉ mục của nó.
## Bước 6: Tháo mặt nạ
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Chúng tôi xóa mặt nạ sai khỏi bộ sưu tập dựa trên chỉ mục của nó.
## Bước 7: Lặp lại mặt nạ
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Vòng lặp này lặp qua từng mặt nạ phác thảo trong bộ sưu tập và in ra các thuộc tính của nó như độ dài, cấp độ, dấu phân cách và loại.
## Bước 8: Sao chép mặt nạ sang dự án khác
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Cuối cùng, chúng tôi sao chép các mặt nạ phác thảo từ dự án này sang dự án khác, đảm bảo tính nhất quán giữa các dự án khác nhau.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thao tác các mặt nạ phác thảo của bộ sưu tập MS Project bằng Aspose.Tasks cho .NET. Bằng cách làm theo hướng dẫn này, giờ đây bạn đã được trang bị các kỹ năng để quản lý hiệu quả các mặt nạ phác thảo trong dự án của mình, cuối cùng là nâng cao năng suất và quy trình làm việc của bạn.
## Câu hỏi thường gặp
### Câu hỏi 1: Tôi có thể sử dụng Aspose.Tasks cho .NET với các phiên bản khác nhau của tệp Microsoft Project không?
Trả lời: Có, Aspose.Tasks for .NET hỗ trợ nhiều phiên bản khác nhau của tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.
### Câu hỏi 2: Aspose.Tasks dành cho .NET có tương thích với .NET Core không?
Trả lời: Có, Aspose.Tasks for .NET tương thích với .NET Core, cho phép bạn sử dụng nó trong các ứng dụng đa nền tảng.
### Câu hỏi 3: Tôi có thể tùy chỉnh các thuộc tính của mặt nạ phác thảo theo yêu cầu dự án của mình không?
Đ: Chắc chắn rồi! Bạn có thể tùy chỉnh mặt nạ phác thảo bằng cách điều chỉnh độ dài, cấp độ, dấu phân cách và loại của chúng để phù hợp với nhu cầu dự án cụ thể của bạn.
### Câu hỏi 4: Aspose.Tasks dành cho .NET có cung cấp tài liệu và hỗ trợ không?
Đáp: Có, Aspose.Tasks for .NET cung cấp tài liệu toàn diện và hỗ trợ tận tình thông qua trang web và[diễn đàn](https://forum.aspose.com/c/tasks/15).
### Câu hỏi 5: Có bản dùng thử miễn phí dành cho Aspose.Tasks dành cho .NET không?
 Đáp: Có, bạn có thể truy cập bản dùng thử miễn phí Aspose.Tasks dành cho .NET từ trang web của họ.[trang mạng](https://releases.aspose.com/tasks/net/). để khám phá các tính năng và chức năng của nó trước khi mua hàng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
