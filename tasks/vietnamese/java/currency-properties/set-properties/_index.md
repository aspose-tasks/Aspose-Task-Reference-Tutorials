---
date: 2026-09-09
description: Tìm hiểu cách thay đổi ký hiệu tiền tệ trong các dự án Aspose.Tasks Java,
  thiết lập mã tiền tệ, điều chỉnh ký hiệu và áp dụng định dạng tùy chỉnh cho các
  tệp Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Đặt thuộc tính tiền tệ trong các dự án Aspose.Tasks
og_description: Cách thay đổi ký hiệu tiền tệ trong Aspose.Tasks bằng Java. Khám phá
  hướng dẫn chi tiết từng bước, các yêu cầu trước và mẹo để tùy chỉnh định dạng chi
  phí dự án.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Cách thay đổi ký hiệu tiền tệ trong Aspose.Tasks – Hướng dẫn Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Cách thay đổi ký hiệu tiền tệ trong các dự án Aspose.Tasks – Hướng dẫn Java
url: /vi/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thay đổi ký hiệu tiền tệ trong Aspose.Tasks – Hướng dẫn Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách thay đổi ký hiệu tiền tệ** cho tệp Microsoft Project bằng cách sử dụng Aspose.Tasks Java API. Cho dù bạn đang chuẩn bị báo cáo cho khách hàng ở nước ngoài, hợp nhất ngân sách trên nhiều khu vực, hoặc chỉ cần phù hợp với tiêu chuẩn kế toán của công ty, việc điều chỉnh ký hiệu tiền tệ đảm bảo mọi trường liên quan đến chi phí hiển thị dấu tiền đúng. Hướng dẫn sẽ đi qua từng bước, từ thiết lập môi trường phát triển đến lưu các thay đổi vào tệp dự án mới hoặc hiện có.

## Câu trả lời nhanh
- **Thư viện cần thiết là gì?** Aspose.Tasks for Java.  
- **Tôi có thể thay đổi ký hiệu tiền tệ không?** Có – đặt `Prj.CURRENCY_SYMBOL` và chọn `CurrencySymbolPositionType`.  
- **Các định dạng tệp nào được hỗ trợ?** XML, MPP và nhiều định dạng khác qua `SaveFileFormat`.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc kiểm tra; cần giấy phép cho môi trường sản xuất.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 5‑10 phút cho cấu hình cơ bản.

## Cách thay đổi ký hiệu tiền tệ trong Aspose.Tasks bằng Java?
Tải dự án mục tiêu (hoặc tạo một dự án mới), đặt các thuộc tính tiền tệ mong muốn và lưu tệp. Toàn bộ thao tác bao gồm ba lời gọi API: tạo hoặc tải đối tượng `Project`, gán mã tiền tệ, ký hiệu và vị trí, sau đó gọi `project.save`. Cách tiếp cận này hoạt động cho cả dự án mới và tệp hiện có mà không cần cài đặt Microsoft Project.

## Tại sao nên sử dụng Aspose.Tasks để thay đổi tiền tệ?
Aspose.Tasks cung cấp **sự bao phủ đầy đủ API cho hơn 30 thuộc tính liên quan đến tiền tệ**, cho phép bạn định nghĩa mã, ký hiệu, số chữ số thập phân và vị trí ở một nơi. Thư viện xử lý các tệp Project hàng trăm trang trong vòng chưa tới một giây trên phần cứng máy chủ tiêu chuẩn, và hoạt động trên Windows, Linux và macOS mà không cần bất kỳ phụ thuộc nào thêm.

## Yêu cầu trước
1. **Java Development Kit (JDK) 8 hoặc cao hơn** – API yêu cầu ít nhất JDK 8.  
2. **Aspose.Tasks for Java** – tải xuống JAR mới nhất từ [trang tải xuống Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Một IDE** – Eclipse, IntelliJ IDEA, hoặc bất kỳ trình chỉnh sửa nào hỗ trợ Java.  
4. **Một thư mục có quyền ghi** – nơi tệp dự án được tạo sẽ được lưu.

## Nhập các gói
Các lớp sau cung cấp quyền truy cập vào các thuộc tính dự án, xử lý tệp và cài đặt tiền tệ.  

`Project` – đại diện cho một tệp Microsoft Project trong bộ nhớ.  
`Prj` – chứa các hằng số cho tất cả các thuộc tính cấp dự án, bao gồm các trường tiền tệ.  
`CurrencySymbolPositionType` – liệt kê các vị trí có thể cho ký hiệu tiền tệ (trước hoặc sau số tiền).  

Các import này cần thiết trước khi bất kỳ đoạn mã nào có thể thao tác với dự án.

## Hướng dẫn từng bước

### Bước 1: Xác định thư mục dữ liệu
Chọn một thư mục chứa các tệp nguồn của bạn và nơi đầu ra sẽ được ghi. Đảm bảo thư mục tồn tại và quá trình Java của bạn có quyền ghi.

### Bước 2: Tạo một thể hiện dự án mới
Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks đại diện cho một tệp Project duy nhất trong bộ nhớ. Khi khởi tạo, nó tạo ra một dự án trống sẵn sàng cho cấu hình.

### Bước 3: Đặt các thuộc tính tiền tệ
Ở đây bạn cấu hình mã tiền tệ, số chữ số thập phân, ký hiệu và vị trí của ký hiệu.  

- **Mã tiền tệ** – mã ISO 4217 ba chữ như `AUD` hoặc `USD`.  
- **Số chữ số thập phân** – thường là 2 cho hầu hết các tiền tệ.  
- **Ký hiệu tiền tệ** – ký tự hoặc chuỗi hiển thị cùng với số tiền, ví dụ `$` hoặc `€`.  
- **Vị trí ký hiệu** – `CurrencySymbolPositionType.Before` đặt ký hiệu trước số; `After` đặt sau.

Các cài đặt này ảnh hưởng đến mọi trường liên quan đến chi phí (đơn giá tài nguyên, ngân sách nhiệm vụ, v.v.) trong dự án.

> **Mẹo:** Nếu bạn cần thay đổi tiền tệ cho một tệp hiện có, hãy tải nó bằng `new Project("file.mpp")` trước khi áp dụng các cài đặt trên.

### Bước 4: Lưu dự án đã cập nhật
Ghi dự án trở lại đĩa bằng định dạng mong muốn. Định dạng XML có thể đọc được bởi con người, trong khi `SaveFileFormat.MPP` giữ nguyên tính tương thích đầy đủ với Microsoft Project.

### Bước 5: Xác nhận thành công
In ra một thông báo ngắn hoặc mục nhật ký để bạn biết thao tác đã hoàn thành mà không có lỗi. Điều này đặc biệt hữu ích trong các pipeline tự động.

## Các vấn đề thường gặp & giải pháp
| Vấn đề | Lý do | Cách khắc phục |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` không phải là đường dẫn hợp lệ hoặc thiếu quyền ghi. | Đảm bảo thư mục tồn tại và quá trình Java của bạn có quyền ghi. |
| **Ký hiệu tiền tệ không hiển thị** | Vị trí ký hiệu được đặt không đúng cho locale của bạn. | Sử dụng `CurrencySymbolPositionType.Before` nếu ký hiệu nên đứng trước số. |
| **Tệp dự án không mở được trong MS Project** | Lưu ở định dạng cũ với các cài đặt không tương thích. | Lưu bằng `SaveFileFormat.MPP` để tương thích đầy đủ với các phiên bản MS Project mới nhất. |

## Câu hỏi thường gặp

**Q: Tôi có thể đặt nhiều tiền tệ trong một dự án duy nhất bằng Aspose.Tasks không?**  
A: Có, bạn có thể gán các cài đặt tiền tệ khác nhau cho từng tài nguyên hoặc nhiệm vụ bằng cách sửa đổi các trường chi phí tương ứng sau khi đã định nghĩa tiền tệ cấp dự án.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
A: Hoàn toàn có. Thư viện hỗ trợ các tệp MPP từ Project 2000 đến các bản phát hành mới nhất, cũng như XML và các định dạng trao đổi khác.

**Q: Aspose.Tasks có hỗ trợ định dạng tiền tệ tùy chỉnh không?**  
A: Có, bạn có thể định nghĩa ký hiệu, số chữ số thập phân và vị trí tùy chỉnh để đáp ứng bất kỳ yêu cầu khu vực nào, và các cài đặt này sẽ được lưu trong tệp đã lưu.

**Q: Tôi có thể tích hợp Aspose.Tasks với các framework Java khác không?**  
A: Chắc chắn. API thuần Java, vì vậy nó hoạt động liền mạch với Spring, Hibernate, Maven, Gradle và các hệ sinh thái khác.

**Q: Tôi có thể tìm thêm trợ giúp hoặc ví dụ ở đâu?**  
A: Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ cộng đồng, hoặc tham khảo tài liệu chính thức để có các tham chiếu API chi tiết.

## Kết luận
Bây giờ bạn đã biết **cách thay đổi ký hiệu tiền tệ** trong các dự án Aspose.Tasks bằng Java, cách đặt mã tiền tệ, điều chỉnh số chữ số thập phân và áp dụng ký hiệu tùy chỉnh. Những khả năng này cho phép bạn tạo báo cáo chi phí theo địa phương, đồng bộ ngân sách dự án với tiêu chuẩn kế toán khu vực, và giữ cho các tệp Microsoft Project của bạn nhất quán trên toàn bộ các đội ngũ toàn cầu.

---

**Cập nhật lần cuối:** 2026-09-09  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Hướng dẫn liên quan

- [thuộc tính dự án java – Trích xuất ký hiệu tiền tệ từ MPP bằng Aspose.Tasks cho Java](/tasks/java/currency/currency-symbols/)
- [Đọc thuộc tính tiền tệ Java với dự án Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Quản lý mã tiền tệ Java với Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}