---
date: 2026-09-20
description: Tìm hiểu cách trích xuất ký hiệu tiền tệ mpp và cập nhật các thuộc tính
  dự án bằng Aspose.Tasks cho Java. Thay đổi và lấy lại ký hiệu chỉ trong vài dòng
  mã.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Trích xuất ký hiệu tiền tệ mpp bằng Aspose.Tasks cho Java
og_description: Tìm hiểu cách trích xuất ký hiệu tiền tệ mpp và cập nhật các thuộc
  tính dự án bằng Aspose.Tasks cho Java. Nhanh chóng, đáng tin cậy và sẵn sàng cho
  môi trường sản xuất.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Cách trích xuất ký hiệu tiền tệ mpp bằng Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Cách trích xuất ký hiệu tiền tệ mpp bằng Aspose.Tasks Java
url: /vi/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất ký hiệu tiền tệ mpp bằng Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách làm việc với **java project properties** — cụ thể là cách **extract currency symbol mpp** từ tệp Microsoft Project (MPP) và cách **change currency symbol java** hoặc **retrieve currency symbol java** bằng thư viện Aspose.Tasks. Cho dù bạn đang xây dựng công cụ báo cáo tài chính, tích hợp dữ liệu Project vào hệ thống ERP, hoặc chỉ cần hiển thị ký hiệu tiền tệ đúng trong giao diện người dùng, việc nắm vững nhiệm vụ nhỏ nhưng quan trọng này sẽ giúp các ứng dụng Java của bạn trở nên mạnh mẽ hơn và thân thiện với người dùng.

## Câu trả lời nhanh
- **What does “extract currency symbol mpp” mean?** Nó có nghĩa là đọc ký hiệu tiền tệ được lưu trong tệp MPP (Microsoft Project).  
- **Which library handles this?** Aspose.Tasks for Java cung cấp một API đơn giản cho công việc này.  
- **Do I need a license?** Một bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **How long does it take?** Với đoạn mã dưới đây, bạn có thể lấy ký hiệu trong vòng chưa đầy một phút.  
- **Can I also change the symbol?** Có – bạn có thể đặt giá trị mới bằng cách sử dụng cùng thuộc tính `Prj.CURRENCY_SYMBOL`.

## “Trích xuất ký hiệu tiền tệ mpp” là gì?
Việc trích xuất ký hiệu tiền tệ từ tệp MPP có nghĩa là đọc chuỗi ký tự đơn mà Microsoft Project lưu trong phần đầu của tệp để biểu thị đơn vị tiền tệ của dự án. Thao tác này cho phép bạn hiển thị ký hiệu đúng (như $, €, £) trong các ứng dụng của mình mà không cần mã cứng một giá trị.

## Tại sao cần cập nhật ký hiệu tiền tệ trong thuộc tính dự án Java?
Cập nhật ký hiệu tiền tệ cho phép bạn địa phương hoá báo cáo, hoá đơn và bảng điều khiển ngay lập tức. Các doanh nghiệp thực hiện dự án trên nhiều khu vực có thể thay đổi ký hiệu chỉ trong một bước, tránh việc phải sao chép toàn bộ tệp dự án. Aspose.Tasks có thể sửa đổi thuộc tính trong bộ nhớ và lưu lại tệp, hỗ trợ các dự án có tới 2.000 nhiệm vụ mà không gây ảnh hưởng đáng kể đến hiệu năng.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. **Java Development Kit (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ [trang tải Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Một tệp **project.mpp** hợp lệ được đặt trong thư mục bạn có thể tham chiếu từ mã của mình.

## Nhập các gói
Đầu tiên, nhập các lớp chúng ta sẽ cần để làm việc với các tệp Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Bước 1: xác định thư mục dữ liệu
Cho ứng dụng biết vị trí tệp *.mpp* của bạn.

```java
String dataDir = "Your Data Directory";
```

> **Mẹo:** Sử dụng `System.getProperty("user.dir")` để xây dựng đường dẫn tuyệt đối hoạt động trên bất kỳ máy nào.

## Bước 2: tải tệp MS Project
`Project` là đối tượng cấp cao nhất của Aspose.Tasks đại diện cho một tệp Microsoft Project duy nhất trong bộ nhớ. Tạo đối tượng này sẽ tải cấu trúc tệp mà không cần cài đặt Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Bước 3: lấy (và tùy chọn thay đổi) ký hiệu tiền tệ
`Prj.CURRENCY_SYMBOL` là khóa thuộc tính lưu ký hiệu tiền tệ. Đọc nó sẽ trả về ký hiệu hiện tại; gán một chuỗi mới sẽ cập nhật định nghĩa tiền tệ của dự án.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Lệnh `System.out.println` sẽ in ký hiệu (ví dụ, `$`) ra console, xác nhận việc trích xuất đã thành công.

## Các vấn đề thường gặp & cách khắc phục
| Triệu chứng | Nguyên nhân khả dĩ | Giải pháp |
|------------|-------------------|-----------|
| `NullPointerException` trên `project.get(...)` | Đường dẫn tệp sai hoặc không tìm thấy tệp | Kiểm tra `dataDir` và tên tệp; sử dụng `new File(dataDir).exists()` để gỡ lỗi |
| Ký hiệu không mong muốn (ví dụ, `?`) | Dự án được tạo với locale không chuẩn | Đảm bảo tệp MPP nguồn thực sự định nghĩa ký hiệu tiền tệ; bạn có thể đặt một ký hiệu bằng chương trình như đã trình bày ở trên |
| Lỗi giấy phép | Sử dụng bản dùng thử mà không có tệp giấy phép hợp lệ | Tải giấy phép của bạn bằng `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` trước khi tạo đối tượng `Project` |

## Câu hỏi thường gặp

**Q: Tôi có thể thao tác các thuộc tính dự án khác ngoài ký hiệu tiền tệ bằng Aspose.Tasks không?**  
A: Có, Aspose.Tasks cho phép bạn chỉnh sửa nhiệm vụ, nguồn lực, phân công, lịch, và nhiều thuộc tính dự án khác.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp MS Project khác nhau không?**  
A: Chắc chắn. Nó hỗ trợ các định dạng MPP, MPT và XML từ Project 98 đến các phiên bản mới nhất.

**Q: Aspose.Tasks có cung cấp tài liệu và hỗ trợ cho nhà phát triển không?**  
A: Tài liệu API toàn diện, ví dụ mã, và diễn đàn hỗ trợ riêng có sẵn trên trang web Aspose.Tasks.

**Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
A: Có – bản dùng thử đầy đủ chức năng có thể tải xuống từ [trang web Aspose](https://purchase.aspose.com/buy).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Tasks?**  
A: Giấy phép tạm thời được cung cấp trên [trang giấy phép tạm thời của Aspose](https://purchase.aspose.com/temporary-license/) cho mục đích đánh giá.

**Last Updated:** 2026-09-20  
**Được kiểm tra với:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thuộc tính Dự án Java – Đọc Metadata với Aspose.Tasks](/tasks/java/project-properties/)
- [Cách Lấy Tiền tệ từ MS Project bằng Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Đặt Ngày Bắt đầu Dự án trong MS Project bằng Aspose.Tasks cho Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}