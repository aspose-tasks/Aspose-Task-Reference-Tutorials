---
date: 2025-12-04
description: Tìm hiểu cách thiết lập tiền tệ trong các dự án Aspose.Tasks Java, bao
  gồm cách thay đổi tiền tệ và ký hiệu tiền tệ trong Java. Thao tác các tệp Microsoft
  Project một cách dễ dàng.
language: vi
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Cách Đặt Tiền Tệ trong Dự Án Aspose.Tasks – Hướng Dẫn Java
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Tiền Tệ trong Dự Án Aspose.Tasks – Hướng Dẫn Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách đặt tiền tệ** cho tệp Microsoft Project bằng cách sử dụng Aspose.Tasks Java API. Cho dù bạn cần *thay đổi tiền tệ* cho các đội ngũ quốc tế hoặc điều chỉnh *ký hiệu tiền tệ* trong Java, các bước dưới đây sẽ hướng dẫn bạn qua quá trình với các giải thích rõ ràng và mã sẵn sàng chạy.

## Câu trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.Tasks for Java.  
- **Tôi có thể thay đổi ký hiệu tiền tệ không?** Có – sử dụng `CurrencySymbolPositionType` và `Prj.CURRENCY_SYMBOL`.  
- **Các định dạng tệp nào được hỗ trợ?** XML, MPP và nhiều định dạng khác qua `SaveFileFormat`.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; giấy phép cần thiết cho môi trường sản xuất.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 5‑10 phút cho cấu hình cơ bản.

## Tiền tệ là gì trong tệp Project?
Tiền tệ của một Project xác định cách hiển thị các giá trị chi phí—mã (ví dụ, `AUD`), số chữ số thập phân, ký hiệu (`$`), và vị trí của ký hiệu. Việc đặt các thuộc tính này đảm bảo rằng mọi trường liên quan đến chi phí (giá trị tài nguyên, ngân sách công việc, v.v.) phản ánh định dạng tiền tệ đúng cho người dùng của bạn.

## Tại sao nên sử dụng Aspose.Tasks để thay đổi tiền tệ?
- **Không cần cài đặt Microsoft Project** – thao tác với các tệp trên bất kỳ máy chủ nào.  
- **Bao phủ đầy đủ API** – tất cả các trường liên quan đến tiền tệ được mở ra qua các hằng số `Prj`.  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS với bất kỳ IDE nào tương thích Java.  
- **Hiệu năng cao** – xử lý các tệp dự án lớn nhanh chóng và đáng tin cậy.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ [trang tải xuống Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Một IDE** – Eclipse, IntelliJ IDEA, hoặc bất kỳ trình soạn thảo nào bạn thích.  
4. **Một thư mục có thể ghi** – nơi tệp dự án được tạo sẽ được lưu.

## Nhập các gói
Đầu tiên, nhập các lớp cung cấp quyền truy cập vào các thuộc tính dự án và xử lý tệp.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Hướng dẫn từng bước

### Bước 1: Xác định Thư mục Dữ liệu
Chỉ định thư mục chứa các tệp nguồn của bạn và nơi đầu ra sẽ được ghi.

```java
String dataDir = "Your Data Directory";
```

### Bước 2: Tạo một Instance Dự án Mới
Khởi tạo một đối tượng `Project` mới. Đối tượng này đại diện cho một tệp Microsoft Project trong bộ nhớ.

```java
Project project = new Project();
```

### Bước 3: Đặt Các Thuộc tính Tiền tệ
Đây là nơi chúng ta **cách đặt tiền tệ** các chi tiết như mã, số chữ số, ký hiệu và vị trí ký hiệu.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Mẹo chuyên nghiệp:** Nếu bạn cần **thay đổi tiền tệ** cho một dự án hiện có, chỉ cần tải tệp bằng `new Project("file.mpp")` trước khi áp dụng các cài đặt trên.

### Bước 4: Lưu Dự án Đã Cập Nhật
Ghi dự án trở lại đĩa ở định dạng mong muốn. Trong ví dụ này chúng tôi sử dụng định dạng XML, nhưng bạn cũng có thể chọn `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Bước 5: Xác nhận Thành công
In ra một thông báo thân thiện để bạn biết thao tác đã hoàn thành mà không có lỗi.

```java
System.out.println("Process completed Successfully");
```

## Các vấn đề thường gặp & Giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **`NullPointerException` khi `project.save`** | `dataDir` không phải là đường dẫn hợp lệ hoặc thiếu quyền ghi. | Đảm bảo thư mục tồn tại và quá trình Java của bạn có quyền ghi. |
| **Ký hiệu tiền tệ không hiển thị** | Vị trí ký hiệu được đặt không đúng cho locale của bạn. | Sử dụng `CurrencySymbolPositionType.Before` nếu ký hiệu nên đứng trước số tiền. |
| **Tệp dự án không mở được trong MS Project** | Lưu ở định dạng cũ với các cài đặt không tương thích. | Lưu bằng `SaveFileFormat.MPP` để tương thích đầy đủ với các phiên bản MS Project mới nhất. |

## Câu hỏi thường gặp

**Hỏi: Tôi có thể đặt nhiều tiền tệ trong một dự án duy nhất bằng Aspose.Tasks không?**  
**Đáp:** Có, Aspose.Tasks cho phép bạn xử lý nhiều tiền tệ trong một tệp dự án duy nhất bằng cách đặt các thuộc tính tiền tệ trên từng tài nguyên hoặc từng công việc.

**Hỏi: Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
**Đáp:** Hoàn toàn. Thư viện hỗ trợ các tệp MPP từ Project 2000 đến các phiên bản mới nhất, cũng như XML và các định dạng khác.

**Hỏi: Aspose.Tasks có hỗ trợ định dạng tiền tệ tùy chỉnh không?**  
**Đáp:** Có, bạn có thể định nghĩa ký hiệu tùy chỉnh, số chữ số thập phân và vị trí để đáp ứng bất kỳ yêu cầu khu vực nào.

**Hỏi: Tôi có thể tích hợp Aspose.Tasks với các thư viện hoặc framework Java khác không?**  
**Đáp:** Chắc chắn. API thuần Java, vì vậy nó hoạt động liền mạch với Spring, Hibernate, Maven, Gradle và các hệ sinh thái khác.

**Hỏi: Tôi có thể tìm hỗ trợ hoặc trợ giúp bổ sung cho Aspose.Tasks ở đâu?**  
**Đáp:** Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận trợ giúp từ cộng đồng, hoặc tham khảo tài liệu chính thức để có các tham chiếu API chi tiết.

## Kết luận
Bây giờ bạn đã biết **cách đặt tiền tệ**, cách **thay đổi giá trị tiền tệ**, và cách **thay đổi ký hiệu tiền tệ theo kiểu Java** bằng Aspose.Tasks cho Java. Những khả năng này cho phép bạn tùy chỉnh dữ liệu chi phí cho các đội ngũ toàn cầu, tạo báo cáo theo khu vực, và giữ cho các tệp dự án của bạn nhất quán trên mọi biên giới.

---

**Cập nhật lần cuối:** 2025-12-04  
**Kiểm thử với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}