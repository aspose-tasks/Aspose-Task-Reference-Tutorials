---
date: 2026-10-15
description: Tìm hiểu cách thêm thuộc tính tùy chỉnh và quản lý các thuộc tính dự
  án tùy chỉnh trong Aspose.Tasks cho .NET, nâng cao khả năng kiểm soát siêu dữ liệu
  dự án của bạn.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Quản lý bộ sưu tập thuộc tính dự án tùy chỉnh trong Aspose.Tasks
og_description: Thêm thuộc tính tùy chỉnh vào các tệp dự án của bạn với Aspose.Tasks
  cho .NET. Hướng dẫn này chỉ cho bạn cách quản lý các thuộc tính tùy chỉnh, đọc chúng
  và thêm giá trị boolean hoặc chuỗi một cách hiệu quả.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Thêm thuộc tính tùy chỉnh bằng Aspose.Tasks .NET API cho dự án
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Cách thêm thuộc tính tùy chỉnh trong Aspose.Tasks cho .NET
url: /vi/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm thuộc tính tùy chỉnh trong Aspose.Tasks cho .NET

## Giới thiệu

Hỗ trợ thêm thuộc tính tùy chỉnh cho phép bạn lưu trữ siêu dữ liệu đặc thù của dự án mà các trường tích hợp không bao phủ. Trong hướng dẫn này, bạn sẽ học cách **thêm thuộc tính tùy chỉnh**, đọc lại nó, và quản lý toàn bộ bộ sưu tập thuộc tính tùy chỉnh bằng Aspose.Tasks cho .NET. Khi kết thúc, bạn sẽ có thể tùy chỉnh các tệp dự án với các giá trị Boolean, DateTime, Double và String phù hợp với quy tắc kinh doanh của bạn.

## Câu trả lời nhanh
- **Tôi có thể thêm thuộc tính tùy chỉnh kiểu Boolean không?** Có – sử dụng `CustomPropertyType.Boolean`.
- **Có bao nhiêu loại thuộc tính tùy chỉnh được hỗ trợ?** Bốn loại: Boolean, DateTime, Double, String.
- **Bộ sưu tập thuộc tính tùy chỉnh có phải chỉ đọc không?** Nó có thể chỉ đọc nếu dự án được tải từ nguồn chỉ đọc.
- **Tôi có cần giấy phép để sử dụng tính năng này không?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.
- **Các phiên bản .NET nào tương thích?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Thuộc tính tùy chỉnh là gì?

Thuộc tính tùy chỉnh là một trường siêu dữ liệu do người dùng định nghĩa mà bạn gắn vào đối tượng Project. Nó cho phép bạn lưu trữ thông tin bổ sung như “Mức độ rủi ro”, “Mã khách hàng”, hoặc bất kỳ cờ Boolean nào mà các trường tiêu chuẩn của MS‑Project không bao phủ.

## Tại sao nên thêm thuộc tính tùy chỉnh trong Aspose.Tasks?

Aspose.Tasks hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý các dự án với **tối đa 10.000 nhiệm vụ** mà không cần tải toàn bộ tệp vào bộ nhớ. Thêm thuộc tính tùy chỉnh cho phép bạn nhúng dữ liệu quan trọng cho doanh nghiệp trực tiếp vào tệp dự án, loại bỏ nhu cầu sử dụng cơ sở dữ liệu bên ngoài và đảm bảo dữ liệu đi cùng dự án.

## Yêu cầu trước

- Visual Studio (bất kỳ phiên bản gần đây nào) đã được cài đặt trên máy làm việc của bạn.  
- Aspose.Tasks cho .NET – tải xuống từ [download link](https://releases.aspose.com/tasks/net/).  
- Kiến thức cơ bản về cú pháp C# và cấu trúc dự án .NET.

## Nhập không gian tên

Các không gian tên sau cung cấp cho bạn quyền truy cập vào mô hình dự án cốt lõi và API thuộc tính tùy chỉnh.

```csharp
using Aspose.Tasks;
using System;


```

## Cách thêm thuộc tính tùy chỉnh trong Aspose.Tasks?

Để thêm một thuộc tính tùy chỉnh, đầu tiên tải dự án, sau đó tạo một đối tượng `CustomProperty`, đặt tên, kiểu và giá trị, và cuối cùng thêm nó vào bộ sưu tập `CustomProperties` của dự án. Thao tác này nhúng siêu dữ liệu trực tiếp vào tệp dự án, và các thay đổi sẽ được lưu khi bạn gọi `project.Save(...)`.  

`CustomProperty` đại diện cho một trường do người dùng định nghĩa gắn vào dự án.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Bước 1: khởi tạo dự án

`Project` là lớp chính đại diện cho tệp dự án trong Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Bước 2: kiểm tra tính sẵn sàng của bộ sưu tập thuộc tính tùy chỉnh

`CustomProperties` là bộ sưu tập chứa tất cả các đối tượng thuộc tính tùy chỉnh cho một dự án.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Bước 3: thêm thuộc tính tùy chỉnh

Phương thức `Add` chèn một thuộc tính tùy chỉnh mới vào bộ sưu tập của dự án.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Bước 4: truy cập thuộc tính tùy chỉnh

Bộ sưu tập `CustomProperties` triển khai IEnumerable, cho phép lặp qua từng `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Bước 5: lấy giá trị của thuộc tính tùy chỉnh

Phương thức `Get` trả về giá trị của thuộc tính tùy chỉnh theo tên của nó.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Bước 6: lặp qua các tên thuộc tính tùy chỉnh

Thuộc tính `Names` cung cấp danh sách tất cả các tên thuộc tính tùy chỉnh trong bộ sưu tập.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Bước 7: xóa hoặc xóa sạch các thuộc tính tùy chỉnh

Phương thức `Remove` xóa một thuộc tính cụ thể, trong khi `Clear` làm trống toàn bộ bộ sưu tập.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Những khó khăn thường gặp và khắc phục

- **Bộ sưu tập chỉ đọc** – Nếu `project.CustomProperties.IsReadOnly` trả về `true`, hãy chắc chắn tệp nguồn không được mở ở chế độ chỉ đọc độc quyền hoặc sao chép nó tới vị trí có thể ghi trước khi chỉnh sửa.  
- **Không khớp kiểu** – Gán một giá trị không phù hợp với `CustomPropertyType` đã khai báo sẽ gây ra `ArgumentException`. Luôn đặt `Value` sau khi xác định `Type` đúng.  
- **Lưu thay đổi** – Sau khi thêm hoặc xóa thuộc tính, gọi `project.Save("output.mpp")` để lưu lại các thay đổi; nếu không, các thay đổi sẽ chỉ tồn tại trong bộ nhớ.

## Câu hỏi thường gặp

**Q: Tôi có thể thêm thuộc tính tùy chỉnh của bất kỳ kiểu dữ liệu nào vào dự án của mình bằng Aspose.Tasks cho .NET không?**  
A: Có, bạn có thể thêm các thuộc tính tùy chỉnh hỗ trợ các kiểu Boolean, DateTime, Double và String.

**Q: Có thể lặp qua các tên thuộc tính tùy chỉnh trong Aspose.Tasks cho .NET không?**  
A: Chắc chắn, bạn có thể lặp qua các tên thuộc tính tùy chỉnh bằng cách sử dụng thuộc tính `Names`.

**Q: Làm thế nào để tôi xóa một thuộc tính tùy chỉnh cụ thể khỏi dự án?**  
A: Bạn có thể xóa một thuộc tính tùy chỉnh bằng tên của nó bằng phương thức `Remove`.

**Q: Aspose.Tasks cho .NET có hỗ trợ giấy phép tạm thời không?**  
A: Có, bạn có thể nhận giấy phép tạm thời từ trang web Aspose để mục đích đánh giá.

**Q: Tôi có thể tìm hỗ trợ hoặc trợ giúp thêm về Aspose.Tasks cho .NET ở đâu?**  
A: Bạn có thể truy cập diễn đàn Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để đặt câu hỏi hoặc nhận trợ giúp.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Hướng dẫn liên quan

- [Cách đọc các thuộc tính dự án tích hợp sẵn bằng Aspose.Tasks cho .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Quản lý Bộ sưu tập Thuộc tính MS Project trong Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Các Kiểu Trường Tùy chỉnh Aspose.Tasks – Lịch và Lập lịch](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}