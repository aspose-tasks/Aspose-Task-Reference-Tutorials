---
date: 2025-12-04
description: Tìm hiểu cách đọc các thuộc tính tiền tệ trong Java từ các tệp MS Project
  bằng Aspose.Tasks cho Java. Hãy làm theo hướng dẫn từng bước này để trích xuất mã
  tiền tệ, ký hiệu, số chữ số và vị trí một cách lập trình.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Đọc các thuộc tính tiền tệ Java với các dự án Aspose.Tasks
url: /vi/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Thuộc tính Tiền tệ Java với Dự án Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này bạn sẽ **đọc thuộc tính tiền tệ Java** từ các tệp Microsoft Project bằng cách sử dụng API Aspose.Tasks cho Java. Aspose.Tasks cho phép bạn làm việc với các tệp .mpp mà không cần cài đặt Microsoft Project, làm cho nó trở nên lý tưởng cho việc báo cáo tự động, di chuyển dữ liệu, hoặc tích hợp vào các ứng dụng doanh nghiệp dựa trên Java. Khi kết thúc hướng dẫn này, bạn sẽ có thể trích xuất mã tiền tệ, ký hiệu, số chữ số thập phân và vị trí ký hiệu trực tiếp từ một tệp dự án.

## Câu trả lời nhanh
- **“đọc thuộc tính tiền tệ java” có nghĩa là gì?** Nó đề cập đến việc lấy siêu dữ liệu liên quan đến tiền tệ (mã, ký hiệu, chữ số, vị trí) từ một tệp MS Project bằng mã Java.  
- **Tôi có cần giấy phép để thử không?** Có một bản dùng thử miễn phí của Aspose.Tasks; giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản JDK nào được yêu cầu?** Java 8 hoặc cao hơn.  
- **Tôi có thể sửa đổi cài đặt tiền tệ sau khi đọc không?** Có, Aspose.Tasks cho phép cả thao tác đọc và ghi trên các thuộc tính tiền tệ.  
- **Điều này có tương thích với tất cả các phiên bản .mpp không?** API hỗ trợ các tệp được tạo bằng Microsoft Project 2003‑2021.

## Đọc thuộc tính tiền tệ Java là gì?
Đọc thuộc tính tiền tệ trong Java có nghĩa là truy cập các cài đặt ở mức dự án xác định cách hiển thị giá trị tiền tệ trong tệp Microsoft Project. Các cài đặt này bao gồm mã tiền tệ ISO (ví dụ, **USD**), ký hiệu (**$**), số chữ số thập phân, và việc ký hiệu xuất hiện trước hay sau số tiền.

## Tại sao nên đọc thuộc tính tiền tệ Java với Aspose.Tasks?
- **Không cần cài đặt Microsoft Project** – API hoạt động trên bất kỳ nền tảng nào hỗ trợ Java.  
- **Trích xuất nhanh, trong‑process** – lý tưởng cho việc lý hàng loạt số lượng lớn tệp dự án.  
- **Kiểm soát đầy đủ** – bạn có thể kết hợp các giá trị đã lấy với báo cáo tùy chỉnh hoặc tích hợp chúng vào hệ thống ERP.  
- **Hỗ trợ đa phiên bản** – hoạt động với các tệp .mpp từ Project 2003 tới bản phát hành mới nhất 2021.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – Java 8 hoặc mới hơn đã được cài đặt và cấu hình trong `PATH` của bạn.  
2. **Aspose.Tasks for Java JAR** – tải thư viện mới nhất từ [đây](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án.  

## Nhập gói
Bắt đầu bằng cách nhập namespace Aspose.Tasks cần thiết cho việc thao tác dự án:

```java
import com.aspose.tasks.*;
```

## Bước 1: Thiết lập Thư mục Dự án của Bạn
Xác định thư mục chứa tệp `.mpp` mà bạn muốn phân tích. Việc giữ đường dẫn trong một biến giúp mã có thể tái sử dụng:

```java
String dataDir = "Your Data Directory";
```

*Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối hoặc tương đối tới thư mục chứa `project.mpp`.*

## Bước 2: Tạo một Instance Đọc Dự án
Tải tệp Microsoft Project vào một đối tượng `Project`. Đối tượng này cung cấp quyền truy cập vào tất cả các thuộc tính dự án, bao gồm cài đặt tiền tệ:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Nếu tệp của bạn có tên khác, hãy thay đổi `"project.mpp"` cho phù hợp.*

## Bước 3: Hiển thị Thuộc tính Tiền tệ
Bây giờ hãy lấy từng thuộc tính tiền tệ bằng cách sử dụng enum `Prj` và in kết quả ra console. API trả về các đối tượng mà bạn có thể chuyển thành chuỗi để hiển thị:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Bạn sẽ thấy:**  
- **Currency Code** – mã ISO‑4217 như `USD`, `EUR`, `JPY`.  
- **Currency Digits** – thường là `2` cho hầu hết các tiền tệ, `0` cho Yên Nhật.  
- **Currency Symbol** – ký tự hiển thị trong báo cáo (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` cho **trước** số tiền, `1` cho **sau**.

## Bước 4: Hoàn thành Quy trình
Thông báo rằng việc trích xuất đã hoàn thành thành công. Thông báo đơn giản này hữu ích khi mã chạy như một phần của công việc batch lớn hơn:

```java
System.out.println("Process completed Successfully");
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|--------|-------------|----------------|
| **FileNotFoundException** | `dataDir` không đúng hoặc tên tệp bị viết sai. | Kiểm tra chuỗi thư mục và đảm bảo tệp `.mpp` tồn tại tại vị trí đã chỉ định. |
| **NullPointerException on `project.get(...)`** | Tệp dự án không chứa thông tin tiền tệ (không phổ biến) hoặc khóa thuộc tính sai. | Sử dụng `project.contains(Prj.CURRENCY_CODE)` để kiểm tra tồn tại trước khi đọc. |
| **LicenseException** | Chạy mà không có giấy phép Aspose.Tasks hợp lệ trong môi trường sản xuất. | Áp dụng tệp giấy phép bằng cách sử dụng `License license = new License(); license.setLicense("Aspose.Tasks.lic");` trước khi tạo đối tượng `Project`. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks có tương thích với tất cả các phiên bản của Microsoft Project không?**  
A: Aspose.Tasks hỗ trợ các tệp .mpp được tạo bởi Microsoft Project 2003‑2021, bao gồm cả các định dạng cũ và mới nhất.

**Q: Tôi có thể sửa đổi thuộc tính tiền tệ bằng Aspose.Tasks không?**  
A: Có, bạn có thể đọc và ghi cài đặt tiền tệ. Sử dụng `project.set(Prj.CURRENCY_CODE, "EUR");` và sau đó lưu dự án.

**Q: Aspose.Tasks có phù hợp cho việc sử dụng thương mại không?**  
A: Chắc chắn. Đây là thư viện thương mại; bạn có thể mua giấy phép [tại đây](https://purchase.aspose.com/buy).

**Q: Aspose.Tasks có cung cấp bản dùng thử miễn phí không?**  
A: Có, bản dùng thử đầy đủ chức năng có sẵn từ [đây](https://releases.aspose.com/).

**Q: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ cho Aspose.Tasks ở đâu?**  
A: Diễn đàn chính thức của Aspose.Tasks là nơi tốt nhất để được hỗ trợ – truy cập [đây](https://forum.aspose.com/c/tasks/15).

## Kết luận
Bạn đã học cách **đọc thuộc tính tiền tệ Java** từ một tệp MS Project bằng Aspose.Tasks cho Java. Khả năng này cho phép bạn tích hợp siêu dữ liệu tiền tệ vào các báo cáo tùy chỉnh, phân tích tài chính, hoặc các pipeline tích hợp mà không cần phụ thuộc vào Microsoft Project. Hãy thoải mái thử nghiệm việc sửa đổi các thuộc tính hoặc kết hợp dữ liệu này với các thuộc tính dự án khác để xây dựng các giải pháp phong phú hơn.

---

**Cập nhật lần cuối:** 2025-12-04  
**Được kiểm tra với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}