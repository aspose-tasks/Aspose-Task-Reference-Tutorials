---
title: Các loại tài nguyên trong Aspose.Tasks
linktitle: Các loại tài nguyên trong Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Tìm hiểu cách làm việc với các loại tài nguyên khác nhau trong Aspose.Tasks cho .NET, bao gồm tài nguyên công việc, vật liệu và chi phí, thông qua hướng dẫn từng bước.
weight: 14
url: /vi/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Các loại tài nguyên trong Aspose.Tasks

## Giới thiệu
Aspose.Tasks for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project theo chương trình. Cho dù bạn đang quản lý nhiệm vụ, tài nguyên hay lịch trình, Aspose.Tasks sẽ đơn giản hóa quy trình bằng cách cung cấp một bộ API toàn diện. Trong hướng dẫn này, chúng ta sẽ đi sâu vào các loại tài nguyên khác nhau mà bạn có thể sử dụng trong các dự án của mình bằng Aspose.Tasks cho .NET.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Visual Studio: Cài đặt Visual Studio, môi trường phát triển tích hợp (IDE) mạnh mẽ để phát triển .NET.
2.  Aspose.Tasks for .NET: Tải xuống và cài đặt thư viện Aspose.Tasks for .NET từ[đây](https://releases.aspose.com/tasks/net/).
3. Kiến thức cơ bản về C#: Làm quen với C#, ngôn ngữ lập trình được sử dụng để phát triển .NET.

## Nhập không gian tên
Trước tiên, hãy nhập các không gian tên cần thiết để truy cập các chức năng của Aspose.Tasks cho .NET:
```csharp
    
```

## Bước 1: Tạo một phiên bản Project mới
```csharp
var project = new Project();
```
Dòng này khởi tạo một đối tượng Project mới, đóng vai trò là nơi chứa tất cả dữ liệu và hoạt động liên quan đến dự án.
## Bước 2: Thêm tài nguyên công việc
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Ở đây, chúng tôi tạo một tài nguyên công việc mới có tên là "Tài nguyên công việc" và chỉ định loại của nó là ResourceType.Work.
## Bước 3: Thêm tài nguyên vật liệu
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Bước này thêm một tài nguyên vật liệu có tên là "Tài nguyên vật liệu" với loại được đặt thành ResourceType.Material. Ngoài ra, chúng tôi chỉ định nhãn vật liệu là "kg" để biểu thị đơn vị đo lường.
## Bước 4: Thêm nguồn lực chi phí
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Cuối cùng, chúng tôi thêm một tài nguyên chi phí có tên là "Tài nguyên chi phí" và đặt loại của nó là ResourceType.Cost. Ngoài ra, chúng tôi đặt giá trị chi phí thành 59,99, thể hiện giá trị tiền tệ được liên kết với tài nguyên này.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã khám phá cách làm việc với các loại tài nguyên khác nhau trong Aspose.Tasks cho .NET, bao gồm các tài nguyên công việc, vật liệu và chi phí. Bằng cách làm theo hướng dẫn từng bước, bạn có thể quản lý hiệu quả các tài nguyên trong dự án của mình theo chương trình.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.Tasks cho .NET với các định dạng phần mềm quản lý dự án khác không?
Trả lời: Có, Aspose.Tasks hỗ trợ nhiều định dạng khác nhau, bao gồm Microsoft Project (MPP), Primavera P6, v.v.
### Câu hỏi: Có bản dùng thử miễn phí Aspose.Tasks cho .NET không?
 Đ: Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ kỹ thuật cho Aspose.Tasks cho .NET?
 Trả lời: Bạn có thể truy cập diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15) để được hỗ trợ kỹ thuật.
### Câu hỏi: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho .NET không?
 Đáp: Có, bạn có thể mua giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Aspose.Tasks cho .NET có cung cấp tài liệu để tham khảo không?
 A: Có, bạn có thể tìm tài liệu[đây](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
