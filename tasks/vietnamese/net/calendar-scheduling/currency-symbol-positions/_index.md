---
date: 2026-07-19
description: Tìm hiểu cách kiểm soát ký hiệu tiền tệ sau số tiền trong các dự án .NET
  một cách dễ dàng với Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Vị trí ký hiệu tiền tệ trong Aspose.Tasks
og_description: Tìm hiểu cách đặt ký hiệu tiền tệ sau số tiền bằng cách sử dụng Aspose.Tasks
  cho .NET. Thực hiện các hướng dẫn từng bước và các thực tiễn tốt nhất.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Ký hiệu tiền tệ sau số tiền trong Aspose.Tasks — Hướng dẫn nhanh
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Cách đặt ký hiệu tiền tệ sau số tiền trong Aspose.Tasks
url: /vi/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Ký Hiệu Tiền Tệ Sau Số Tiền trong Aspose.Tasks

## Giới thiệu

Khi bạn tạo báo cáo chi phí dự án, việc **kí hiệu tiền tệ sau số tiền** có thể ảnh hưởng đến khả năng đọc và tuân thủ các tiêu chuẩn khu vực. Aspose.Tasks cho .NET cho phép bạn kiểm soát định dạng này chỉ với vài dòng mã, đảm bảo mọi con số tài chính hiển thị chính xác như các bên liên quan mong đợi. Trong hướng dẫn này, chúng tôi sẽ đi qua các bước cần thiết, giải thích vì sao cài đặt này quan trọng, và chỉ cho bạn cách áp dụng nó trong một dự án .NET thực tế.

## Câu trả lời nhanh
- **Ký hiệu tiền tệ sau số tiền có nghĩa là gì?** Nó hiển thị ký hiệu (ví dụ, $) sau giá trị số, như `100 $`.
- **Thuộc tính nào kiểm soát vị trí?** `CurrencySymbolPosition` trên đối tượng `Project`.
- **Tôi có cần giấy phép không?** Bản dùng thử hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.
- **Các loại tiền tệ được hỗ trợ?** Hơn 50 loại tiền tệ được tích hợp sẵn, bao phủ hầu hết các thị trường toàn cầu.
- **Tôi có thể thay đổi cài đặt này tại thời gian chạy không?** Có, bạn có thể cập nhật bất kỳ lúc nào trước khi lưu tệp dự án.

## Cài đặt “ký hiệu tiền tệ sau số tiền” là gì?
Tùy chọn **ký hiệu tiền tệ sau số tiền** xác định ký hiệu tiền tệ sẽ xuất hiện trước hay sau giá trị số trong tất cả các trường tiền tệ của dự án. Điều chỉnh cài đặt này giúp báo cáo tuân thủ các quy ước kế toán địa phương mà không cần xử lý thủ công. Nó cũng cải thiện khả năng đọc cho những người quen với định dạng này.

## Tại sao nên sử dụng Aspose.Tasks cho định dạng tiền tệ?
Aspose.Tasks hỗ trợ **hơn 50 loại tiền tệ** và có thể xử lý các dự án với **hơn 10.000 nhiệm vụ** mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại hiệu suất nhanh ngay cả trên phần cứng khiêm tốn. API cung cấp kiểm soát lập trình, loại bỏ nhu cầu chỉnh sửa bảng tính thủ công. Điều này làm cho việc báo cáo tài chính quy mô lớn trở nên hiệu quả và đáng tin cậy.

## Yêu cầu trước

### 1. Cài đặt Aspose.Tasks cho .NET
Đảm bảo bạn đã cài đặt thư viện Aspose.Tasks. Bạn có thể tải xuống từ [here](https://releases.aspose.com/tasks/net/).

### 2. Kiến thức cơ bản về lập trình .NET
Cần có hiểu biết cơ bản về lập trình .NET để theo dõi các ví dụ.

## Nhập không gian tên

Không gian tên `Aspose.Tasks` cung cấp quyền truy cập vào lớp `Project` và các enum liên quan.

Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks, đại diện cho một tệp dự án duy nhất trong bộ nhớ. Sau khi nhập không gian tên, bạn có thể bắt đầu làm việc với dữ liệu dự án.

```csharp

```

Bây giờ, hãy phân tích ví dụ thành các bước rõ ràng, có thể hành động.

## Cách đặt ký hiệu tiền tệ sau số tiền?

`CurrencySymbolPosition` là một enumeration xác định ký hiệu tiền tệ xuất hiện trước hay sau giá trị số.

Tải dự án của bạn, đặt `CurrencySymbolPosition` thành `After`, sau đó lưu – đó là tất cả những gì bạn cần để hiển thị ký hiệu sau số tiền. Cách tiếp cận trực tiếp này hoạt động với bất kỳ loại tiền tệ nào được hỗ trợ và không yêu cầu logic định dạng bổ sung. Bạn cũng có thể xác minh cài đặt bằng cách xuất một báo cáo chi phí mẫu để đảm bảo ký hiệu hiển thị đúng.

### Bước 1: Tải tệp dự án
Lớp `Project` tải một tệp MS‑Project hiện có hoặc tạo một tệp mới trong bộ nhớ.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Bước 2: Đặt vị trí ký hiệu tiền tệ
`CurrencySymbolPosition` là một enum cho phép bạn chọn `Before` hoặc `After`. Đặt nó thành `After` sẽ đặt ký hiệu sau giá trị số.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Bước 3: Làm việc với dự án
Sau khi bạn đã cấu hình vị trí ký hiệu, bạn có thể tiếp tục thêm nhiệm vụ, nguồn lực hoặc trường tùy chỉnh theo nhu cầu. Cài đặt sẽ được lưu lại khi bạn lưu dự án.

```csharp
// Perform other operations with the project...
```

## Các vấn đề thường gặp và giải pháp
- **Ký hiệu vẫn xuất hiện trước số tiền:** Đảm bảo bạn đặt thuộc tính *trước* khi gọi `Save`. Thay đổi sau khi lưu yêu cầu lưu lại tệp một lần nữa.
- **Tiền tệ không được hỗ trợ:** Kiểm tra mã tiền tệ bạn sử dụng có nằm trong danh sách hỗ trợ của Aspose.Tasks (hơn 50 loại tiền tệ) không.
- **Hiệu suất chậm lại trên dự án lớn:** Sử dụng `ProjectReader` để stream các tệp lớn nếu bạn vượt quá 10.000 nhiệm vụ.

## Câu hỏi thường gặp

**H: Tôi có thể thay đổi vị trí ký hiệu tiền tệ nhiều lần trong cùng một dự án không?**  
A: Có, bạn có thể điều chỉnh `CurrencySymbolPosition` bao nhiêu lần cần thiết; chỉ cần đặt thuộc tính và lưu lại dự án.

**H: Aspose.Tasks có hỗ trợ các loại tiền tệ khác ngoài Đô la Mỹ không?**  
A: Chắc chắn. Aspose.Tasks hỗ trợ hơn 50 loại tiền tệ quốc tế, cho phép bạn làm việc với bất kỳ định dạng khu vực nào.

**H: Có phiên bản dùng thử cho Aspose.Tasks cho .NET không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí của Aspose.Tasks cho .NET từ [here](https://releases.aspose.com/).

**H: Tôi có thể tìm kiếm hỗ trợ nếu gặp vấn đề khi sử dụng Aspose.Tasks cho .NET không?**  
A: Chắc chắn! Bạn có thể tìm kiếm hỗ trợ và trợ giúp từ diễn đàn cộng đồng Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**H: Làm thế nào để mua giấy phép cho Aspose.Tasks cho .NET?**  
A: Bạn có thể mua giấy phép cho Aspose.Tasks cho .NET từ [here](https://purchase.aspose.com/buy).

## Kết luận

Kiểm soát **ký hiệu tiền tệ sau số tiền** là một phần quan trọng của báo cáo tài chính trong phần mềm quản lý dự án. Với Aspose.Tasks cho .NET, bạn có thể thiết lập tùy chọn này bằng mã, hỗ trợ hơn 50 loại tiền tệ và xử lý các dự án lớn một cách hiệu quả. Áp dụng các bước trên để đảm bảo báo cáo dự án của bạn đáp ứng đúng định dạng của bất kỳ địa phương nào.

---

**Cập nhật lần cuối:** 2026-07-19  
**Kiểm tra với:** Aspose.Tasks 24.11 cho .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Quản lý bộ sưu tập lịch trong Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Bộ sưu tập ngoại lệ lịch trong Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Xử lý mức phí MS Project với Aspose.Tasks cho .NET](/tasks/net/rate-recurring-tasks/handling-rates/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}