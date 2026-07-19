---
date: 2026-07-19
description: Tìm hiểu cách thêm loại trường tùy chỉnh trong Aspose.Tasks cho .NET
  với mã hướng dẫn từng bước, các điều kiện tiên quyết và câu hỏi thường gặp.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Loại Trường Tùy Chỉnh trong Aspose.Tasks
og_description: Tìm hiểu cách thêm loại trường tùy chỉnh trong Aspose.Tasks cho .NET.
  Thực hiện theo hướng dẫn từng bước này để tạo, định nghĩa và sử dụng các thuộc tính
  mở rộng một cách hiệu quả.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Cách Thêm Loại Trường Tùy Chỉnh trong Aspose.Tasks cho .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Cách Thêm Loại Trường Tùy Chỉnh trong Aspose.Tasks cho .NET
url: /vi/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Các Loại Trường Tùy Chỉnh trong Aspose.Tasks

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá **cách thêm trường tùy chỉnh** vào tệp Microsoft Project bằng cách sử dụng Aspose.Tasks cho .NET. Trường tùy chỉnh cho phép bạn lưu trữ thông tin bổ sung—như điểm rủi ro, mã phòng ban, hoặc ghi chú tùy chỉnh—trực tiếp trên các tác vụ, nguồn lực, hoặc dự án. Chúng tôi sẽ hướng dẫn toàn bộ quy trình, từ thiết lập môi trường đến định nghĩa, thêm và xác minh một trường văn bản tùy chỉnh.

## Câu trả lời nhanh
- **What is a custom field?** Một cột do người dùng định nghĩa có thể chứa văn bản, số, ngày hoặc cờ trên tác vụ/nguồn lực.  
- **Which class defines a custom field?** `ExtendedAttributeDefinition`.  
- **Can I add a custom field to an existing project?** Có—tải dự án, tạo định nghĩa, sau đó thêm vào bộ sưu tập.  
- **Do I need a license for Aspose.Tasks?** Cần có giấy phép cho môi trường sản xuất; bản dùng thử miễn phí đủ cho việc đánh giá.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “Cách thêm trường tùy chỉnh” trong Aspose.Tasks là gì?
**How to add custom field** đề cập đến quá trình tạo một `ExtendedAttributeDefinition` và gắn nó vào bộ sưu tập `ExtendedAttributes` của dự án. Điều này cho phép bạn lưu trữ siêu dữ liệu bổ sung không có trong lược đồ Project tiêu chuẩn. Nó có thể được sử dụng cho tác vụ, nguồn lực, hoặc chính dự án, cho phép bạn ghi lại thông tin như mức độ rủi ro, mã phòng ban, hoặc ghi chú tùy chỉnh mà các trường mặc định không cung cấp.

## Tại sao nên sử dụng trường tùy chỉnh trong quản lý dự án?
Aspose.Tasks hỗ trợ **hơn 50 loại thuộc tính mở rộng tích hợp** và cho phép bạn định nghĩa **bất kỳ số lượng trường tùy chỉnh nào** mà không ảnh hưởng đáng kể đến kích thước tệp. Khi sử dụng trường tùy chỉnh, bạn có thể:  
Các trường này xuất hiện như các cột bổ sung trong Microsoft Project và có thể được tham chiếu trong công thức, báo cáo và bộ lọc. Chúng được lưu trong tệp dự án và đi cùng với nó, đảm bảo rằng bất kỳ công cụ nào phía sau cũng giữ được dữ liệu tùy chỉnh.

## Yêu cầu trước

### 1. Cài đặt Visual Studio
Đảm bảo Visual Studio (2019 hoặc mới hơn) đã được cài đặt trên máy của bạn. Bạn có thể tải xuống từ trang web của Microsoft.

### 2. Aspose.Tasks cho .NET
Thêm gói NuGet Aspose.Tasks vào dự án của bạn. Tải phiên bản mới nhất từ [here](https://releases.aspose.com/tasks/net/).

### 3. Kiến thức C# cơ bản
Bạn nên quen thuộc với cú pháp C#, các lớp, và cấu trúc dự án .NET.

## Nhập không gian tên

Các lớp `Project`, `ExtendedAttributeDefinition`, và các enum liên quan nằm trong không gian tên `Aspose.Tasks`. Nhập nó ở đầu tệp của bạn:

Không gian tên `Aspose.Tasks` cung cấp tất cả các kiểu cốt lõi để xử lý tệp Microsoft Project.

```csharp

```

## Cách thêm trường tùy chỉnh vào dự án?

Tải dự án hiện có, tạo định nghĩa trường tùy chỉnh, và thêm nó vào bộ sưu tập thuộc tính mở rộng của dự án—tất cả trong ba bước ngắn gọn. Mẫu này hoạt động cho tác vụ, nguồn lực và chính dự án, và đảm bảo trường tùy chỉnh được lưu lại khi bạn lưu tệp.

### Bước 1: Tạo Đối tượng Project
`Project` là đối tượng cấp cao nhất của Aspose.Tasks đại diện cho một tệp Project duy nhất trong bộ nhớ. Khi khởi tạo, nó tải tệp và cho phép bạn truy cập vào các tác vụ, nguồn lực và thuộc tính mở rộng.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Bước 2: Định nghĩa Trường Tùy chỉnh
`ExtendedAttributeDefinition` mô tả một cột mới. Trong ví dụ này chúng ta tạo một trường tùy chỉnh loại **Text** cho các tác vụ và đặt biệt danh là “MyText”. Giá trị enum `ExtendedAttributeTask.Text1` cho Aspose.Tasks biết nơi lưu trữ giá trị.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Bước 3: Thêm Định nghĩa Trường Tùy chỉnh vào Dự án
Bộ sưu tập `ExtendedAttributes` của dự án chứa tất cả các định nghĩa trường tùy chỉnh. Thêm định nghĩa này sẽ làm cho nó khả dụng cho mọi tác vụ trong dự án.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Các vấn đề thường gặp và giải pháp
- **Field not appearing in MS Project UI** – Đảm bảo bạn đã đặt thuộc tính `Alias`; MS Project sẽ hiển thị biệt danh làm tiêu đề cột.  
- **Saving throws an exception** – Kiểm tra xem tệp dự án có phải chỉ đọc không và bạn có giấy phép hợp lệ không.  
- **Custom field values are lost after reload** – Đảm bảo bạn gọi `project.Save("output.mpp")` sau khi gán giá trị cho các tác vụ.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các framework .NET khác không?**  
A: Có, Aspose.Tasks hoạt động với .NET Framework, .NET Core và .NET 5/6/7.

**Q: Aspose.Tasks có phù hợp cho các ứng dụng cấp doanh nghiệp không?**  
A: Chắc chắn. Nó hỗ trợ xử lý các dự án với **tối đa 10.000 tác vụ** và có thể chạy trong môi trường máy chủ đa luồng.

**Q: Aspose.Tasks có hỗ trợ nhiều định dạng tệp dự án không?**  
A: Có—Aspose.Tasks đọc và ghi các định dạng MPP, XML, HTML và CSV, bao phủ **tất cả các phiên bản Microsoft Project chính**.

**Q: Tôi có thể thao tác dữ liệu nguồn lực bằng Aspose.Tasks không?**  
A: Có, bạn có thể thêm, cập nhật và xóa nguồn lực, cũng như gán các trường tùy chỉnh cho chúng.

**Q: Có diễn đàn cộng đồng cho người dùng Aspose.Tasks không?**  
A: Có, bạn có thể truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để tương tác với các người dùng khác và nhận hỗ trợ từ đội ngũ Aspose.

---

**Cập nhật lần cuối:** 2026-07-19  
**Kiểm tra với:** Aspose.Tasks 24.12 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Tổng quan Định nghĩa Thuộc tính Mở rộng trong MS Project bằng Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Thao tác Thuộc tính Mở rộng MS Project với Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Trợ lý Trường tích hợp MS Project trong Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}