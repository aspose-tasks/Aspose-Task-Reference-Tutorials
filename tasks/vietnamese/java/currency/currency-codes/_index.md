---
date: 2026-09-25
description: Tìm hiểu cách lấy mã tiền tệ từ các tệp MS Project bằng Aspose.Tasks
  cho Java – cách nhanh chóng để có được mã tiền tệ mà các nhà phát triển Java cần.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Quản lý mã tiền tệ trong Aspose.Tasks
og_description: Lấy mã tiền tệ Java từ các tệp MS Project bằng Aspose.Tasks. Hướng
  dẫn này cho bạn biết cách đọc dự án, trích xuất định danh tiền tệ ISO và áp dụng
  nó trong các ứng dụng Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Lấy mã tiền tệ Java từ MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Lấy mã tiền tệ Java từ MS Project bằng Aspose.Tasks
url: /vi/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lấy mã tiền tệ java từ MS Project với Aspose.Tasks

## Giới thiệu
Trong tutorial này, bạn sẽ học **cách lấy mã tiền tệ java** từ một tệp MS Project bằng cách sử dụng Aspose.Tasks Java API. Cho dù bạn cần tạo báo cáo tài chính đa tiền tệ, hợp nhất các dự án trên các khu vực khác nhau, hoặc chỉ đơn giản là hiển thị ký hiệu tiền tệ đúng trong hệ thống downstream, các bước dưới đây sẽ đưa bạn từ việc thiết lập môi trường đến lời gọi một dòng duy nhất trả về định danh tiền tệ ISO. Khi kết thúc hướng dẫn, bạn sẽ tự tin tải bất kỳ định dạng tệp Project nào được hỗ trợ và trích xuất mã tiền tệ ba ký tự như `USD`, `EUR` hoặc `GBP`.

## Câu trả lời nhanh
- **API làm gì?** Nó đọc các tệp MS Project và cung cấp các thuộc tính như mã tiền tệ.  
- **Ngôn ngữ nào được sử dụng?** Java, thông qua thư viện Aspose.Tasks cho Java.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể lấy mã trong một dòng không?** Có—`prj.get(Prj.CURRENCY_CODE)` trả về chuỗi mã tiền tệ ngay lập tức.  
- **Có tương thích với tất cả các phiên bản Project không?** Aspose.Tasks hỗ trợ hơn 20 định dạng đầu vào, bao gồm MPP cổ điển, XML và các tệp XER.  

## Đọc tệp MS Project là gì?
Đọc một tệp MS Project có nghĩa là mở chương trình một cách lập trình một tệp *.mpp* (hoặc bất kỳ định dạng nào khác được hỗ trợ như XML hoặc XER) và truy cập vào các cấu trúc dữ liệu nội bộ của nó. Các cấu trúc này bao gồm các công việc, nguồn lực, lịch, bảng chi phí và cài đặt tài chính. Bằng cách phân tích tệp, bạn có thể trích xuất thông tin mà không cần khởi chạy Microsoft Project, cho phép quy trình báo cáo tự động, di chuyển và tích hợp.

## Tại sao nên sử dụng Aspose.Tasks để đọc tệp msproject?
Aspose.Tasks cung cấp giải pháp thuần Java loại bỏ nhu cầu sử dụng COM interop hoặc cài đặt Microsoft Project cục bộ. Nó hỗ trợ hơn 20 định dạng tệp, có thể xử lý các dự án với hàng nghìn công việc trong khi sử dụng dưới 100 MB bộ nhớ, và cung cấp một mô hình đối tượng phong phú. Truy cập trực tiếp vào các hằng số như `Prj.CURRENCY_CODE` cho phép bạn lấy thông tin tiền tệ ngay lập tức và đáng tin cậy.

## Yêu cầu trước
Trước khi chúng ta bắt đầu với mã, hãy chắc chắn rằng bạn có những thứ sau:

### Bộ công cụ phát triển Java (JDK) đã được cài đặt
JDK mới (phiên bản 11 trở lên) là bắt buộc. Tải xuống từ trang chính thức của Oracle: [tại đây](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Thư viện Aspose.Tasks cho Java
Lấy các binary mới nhất của Aspose.Tasks cho Java và thêm chúng vào classpath của dự án. Tài liệu đầy đủ và các liên kết tải xuống có sẵn [tại đây](https://reference.aspose.com/tasks/java/).

## Nhập gói
Lớp `Project` và các hằng số `Prj` nằm trong không gian tên `com.aspose.tasks`. Nhập chúng ở đầu tệp nguồn Java của bạn:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Hướng dẫn từng bước

### Bước 1: thiết lập thư mục dữ liệu
Xác định thư mục chứa tệp *.mpp* của bạn. Điều chỉnh đường dẫn để phù hợp với môi trường của bạn để runtime có thể tìm thấy tệp dự án.

```java
String dataDir = "Your Data Directory";
```

### Bước 2: tải tệp dự án
Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks đại diện cho một tệp MS Project duy nhất trong bộ nhớ. Tạo một thể hiện sẽ đọc tệp và xây dựng mô hình trong bộ nhớ mà bạn có thể truy vấn.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Bước 3: lấy mã tiền tệ
Hằng số `Prj.CURRENCY_CODE` xác định thuộc tính lưu trữ định danh tiền tệ ISO. Gọi `prj.get(Prj.CURRENCY_CODE)` trả về mã ba ký tự trong một thao tác duy nhất.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Kết quả sẽ là mã ISO ba ký tự (ví dụ, `USD`, `EUR`, `GBP`) mà dự án được cấu hình sử dụng.

### Bước 4: cách lấy mã tiền tệ trong Java (ngữ cảnh bổ sung)
Tải dự án của bạn, gọi `prj.get(Prj.CURRENCY_CODE)`, và lưu kết quả vào một `String`. Sau đó bạn có thể truyền giá trị này tới bất kỳ dịch vụ tài chính, công cụ báo cáo, hoặc thành phần UI nào yêu cầu định danh tiền tệ.

### Bước 5: (tùy chọn) sử dụng mã tiền tệ
Các kịch bản downstream điển hình bao gồm:

- **Tạo báo cáo** – đặt trước mã vào các cột chi phí (`USD 1,200`).  
- **Tích hợp API** – gửi mã ISO tới các cổng thanh toán yêu cầu tham số tiền tệ.  
- **Hợp nhất dữ liệu** – nhóm nhiều dự án theo tiền tệ để phân tích ở cấp độ danh mục.  

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| **Null output** | Tệp dự án không xác định tiền tệ (mặc định là trống). | Đặt tiền tệ trong Microsoft Project hoặc gán nó qua `prj.set(Prj.CURRENCY_CODE, "USD");` trước khi đọc. |
| **File not found** | Đường dẫn `dataDir` không đúng. | Kiểm tra lại đường dẫn và đảm bảo tên tệp khớp chính xác, bao gồm cả phân biệt chữ hoa/thường. |
| **Unsupported file version** | Tệp *.mpp* quá cũ hoặc bị hỏng. | Nâng cấp lên phiên bản Aspose.Tasks mới nhất hoặc chuyển đổi tệp sang định dạng mới hơn trong Microsoft Project trước. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể xử lý cấu trúc dự án phức tạp không?**  
A: Có, API đọc các cây công việc đa cấp, pool nguồn lực, trường tùy chỉnh và lịch mà không bị giới hạn.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp MS Project khác nhau không?**  
A: Hoàn toàn. Nó hỗ trợ MPP, XML, XER và các định dạng khác từ Project 98 đến các bản Office mới nhất.

**Q: Aspose.Tasks có cung cấp tài liệu và hỗ trợ không?**  
A: Tham chiếu API toàn diện, ví dụ mã, và hỗ trợ kỹ thuật chuyên dụng có sẵn trên trang web Aspose.

**Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
A: Một bản dùng thử miễn phí được cung cấp để bạn có thể đánh giá tất cả các tính năng, bao gồm việc trích xuất mã tiền tệ.

**Q: Tôi có thể lấy giấy phép tạm thời để đánh giá ở đâu?**  
A: Giấy phép tạm thời có sẵn trên [trang web](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2026-09-25  
**Kiểm tra với:** Aspose.Tasks for Java (latest version)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thuộc tính Project Java – Đọc Metadata với Aspose.Tasks](/tasks/java/project-properties/)
- [Cách Đọc Thông tin Dự án từ Microsoft Project với Aspose.Tasks cho Java](/tasks/java/project-properties/read-project-info/)
- [Lấy Mã Outline của MS Project trong Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}