---
date: 2026-02-07
description: Học cách đọc các thuộc tính tiền tệ trong Java và trích xuất ký hiệu
  tiền tệ trong Java từ các tệp MS Project bằng Aspose.Tasks for Java. Thực hiện theo
  hướng dẫn từng bước này để trích xuất mã tiền tệ, ký hiệu, số chữ số và vị trí của
  chúng một cách lập trình.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Đọc thuộc tính tiền tệ Java với các dự án Aspose.Tasks
url: /vi/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Thuộc tính Tiền tệ Java với Dự án Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **read currency properties java** từ các tệp Microsoft Project bằng cách sử dụng API Aspose.Tasks cho Java. Aspose.Tasks cho phép bạn làm việc với các tệp .mpp mà không cần cài đặt Microsoft Project, làm cho nó trở nên lý tưởng cho việc báo cáo tự động, di chuyển dữ liệu, hoặc tích hợp vào các ứng dụng doanh nghiệp dựa trên Java. Khi kết thúc hướng dẫn này, bạn sẽ có thể trích xuất mã tiền tệ, ký hiệu, số chữ số thập phân và vị trí ký hiệu trực tiếp từ tệp dự án.

## Câu trả lời nhanh
- **What does “read currency properties java” mean?** Nó đề cập đến việc lấy siêu dữ liệu liên quan đến tiền tệ (mã, ký hiệu, chữ số, vị trí) từ tệp MS Project bằng mã Java.  
- **Do I need a license to try this?** Một bản dùng thử miễn phí của Aspose.Tasks có sẵn; cần giấy phép thương mại cho việc sử dụng trong môi trường sản xuất.  
- **Which JDK version is required?** Java 8 trở lên.  
- **Can I modify the currency settings after reading them?** Có, Aspose.Tasks cho phép cả thao tác đọc và ghi trên các thuộc tính tiền tệ.  
- **Is this compatible with all .mpp versions?** API hỗ trợ các tệp được tạo bằng Microsoft Project 2003‑2021.

## read currency properties java là gì?
Đọc các thuộc tính tiền tệ trong Java có nghĩa là truy cập vào các cài đặt ở mức dự án xác định cách hiển thị giá trị tiền tệ trong tệp Microsoft Project. Các cài đặt này bao gồm mã tiền tệ ISO (ví dụ, **USD**), ký hiệu (**$**), số chữ số thập phân, và việc ký hiệu xuất hiện trước hay sau số tiền.

## Tại sao nên đọc currency properties java với Aspose.Tasks?
- **No Microsoft Project installation needed** – API hoạt động trên bất kỳ nền tảng nào hỗ trợ Java.  
- **Fast, in‑process extraction** – lý tưởng cho việc xử lý hàng loạt số lượng lớn tệp dự án.  
- **Full control** – bạn có thể kết hợp các giá trị đã lấy với báo cáo tùy chỉnh hoặc tích hợp chúng vào hệ thống ERP.  
- **Cross‑version support** – hoạt động với các tệp .mpp từ Project 2003 đến phiên bản mới nhất 2021.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Java Development Kit (JDK)** – Java 8 hoặc mới hơn đã được cài đặt và cấu hình trong `PATH` của bạn.  
2. **Aspose.Tasks for Java JAR** – tải xuống thư viện mới nhất từ [here](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án.  

## Nhập các gói
Bắt đầu bằng cách nhập namespace Aspose.Tasks cần thiết cho việc thao tác dự án:

```java
import com.aspose.tasks.*;
```

## Bước 1: Thiết lập Thư mục Dự án của bạn
Xác định thư mục chứa tệp `.mpp` mà bạn muốn phân tích. Giữ đường dẫn trong một biến giúp mã có thể tái sử dụng:

```java
String dataDir = "Your Data Directory";
```

*Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối hoặc tương đối tới thư mục chứa `project.mpp`.*

## Bước 2: Tạo một Instance Đọc Dự án
Tải tệp Microsoft Project vào một đối tượng `Project`. Đối tượng này cung cấp cho bạn quyền truy cập vào tất cả các thuộc tính dự án, bao gồm cài đặt tiền tệ:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Nếu tệp của bạn có tên khác, hãy thay đổi `"project.mpp"` cho phù hợp.*

## Bước 3: Hiển thị Các Thuộc tính Tiền tệ
Bây giờ lấy mỗi thuộc tính tiền tệ bằng cách sử dụng enumeration `Prj` và in kết quả ra console. API trả về các đối tượng mà bạn có thể chuyển đổi thành chuỗi để hiển thị:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Kết quả bạn sẽ thấy:**  
- **Currency Code** – mã ISO‑4217 như `USD`, `EUR`, `JPY`.  
- **Currency Digits** – thường là `2` cho hầu hết các tiền tệ, `0` cho Yên Nhật.  
- **Currency Symbol** – ký tự hiển thị trong báo cáo (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` cho **trước** số tiền, `1` cho **sau**.

## Cách trích xuất ký hiệu tiền tệ java?
Nếu bạn chỉ quan tâm đến ký hiệu, bạn có thể tập trung vào thuộc tính `Prj.CURRENCY_SYMBOL`. Lệnh gọi `project.get(...)` tương tự sẽ trả về ký hiệu, bạn có thể lưu, ghi log, hoặc truyền cho dịch vụ khác để xử lý tiếp. Điều này đặc biệt hữu ích khi bạn cần **extract currency symbol java** cho bảng điều khiển tài chính hoặc các thành phần UI được bản địa hoá.

## Bước 4: Hoàn thành Quy trình
Thông báo rằng việc trích xuất đã hoàn thành thành công. Thông điệp đơn giản này hữu ích khi mã chạy như một phần của công việc batch lớn hơn:

```java
System.out.println("Process completed Successfully");
```

## Các vấn đề thường gặp và giải pháp
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` có đường dẫn không đúng hoặc tên tệp bị sai chính tả. | Kiểm tra chuỗi thư mục và đảm bảo tệp `.mpp` tồn tại ở vị trí đã chỉ định. |
| **NullPointerException on `project.get(...)`** | Tệp dự án không chứa thông tin tiền tệ (hiếm) hoặc khóa thuộc tính sai. | Sử dụng `project.contains(Prj.CURRENCY_CODE)` để kiểm tra tồn tại trước khi đọc. |
| **LicenseException** | Chạy mà không có giấy phép Aspose.Tasks hợp lệ trong môi trường sản xuất. | Áp dụng tệp giấy phép bằng cách sử dụng `License license = new License(); license.setLicense("Aspose.Tasks.lic");` trước khi tạo đối tượng `Project`. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks có tương thích với tất cả các phiên bản của Microsoft Project không?**  
A: Aspose.Tasks hỗ trợ các tệp .mpp được tạo bởi Microsoft Project 2003‑2021, bao gồm cả các định dạng cũ và mới nhất.

**Q: Tôi có thể sửa đổi các thuộc tính tiền tệ bằng Aspose.Tasks không?**  
A: Có, bạn có thể đọc và ghi các cài đặt tiền tệ. Sử dụng `project.set(Prj.CURRENCY_CODE, "EUR");` rồi lưu dự án.

**Q: Aspose.Tasks có phù hợp cho mục đích thương mại không?**  
A: Hoàn toàn. Đây là thư viện thương mại; bạn có thể mua giấy phép [here](https://purchase.aspose.com/buy).

**Q: Aspose.Tasks có cung cấp bản dùng thử miễn phí không?**  
A: Có, bản dùng thử đầy đủ chức năng có sẵn tại [here](https://releases.aspose.com/).

**Q: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ cho Aspose.Tasks ở đâu?**  
A: Diễn đàn chính thức của Aspose.Tasks là nơi tốt nhất để được hỗ trợ – truy cập [here](https://forum.aspose.com/c/tasks/15).

## FAQ bổ sung (AI‑Optimized)

**Q: Làm thế nào để tôi lập trình trích xuất chỉ ký hiệu tiền tệ trong Java?**  
A: Gọi `project.get(Prj.CURRENCY_SYMBOL)` và ép kiểu kết quả thành `String`. Điều này trả về ký hiệu chính xác được sử dụng trong tệp dự án.

**Q: Tôi có thể đọc các thuộc tính tiền tệ từ tệp .mpp được bảo vệ bằng mật khẩu không?**  
A: Có. Tải tệp bằng overload thích hợp của constructor `Project` chấp nhận mật khẩu, sau đó đọc các thuộc tính như đã trình bày.

**Q: Hiệu năng như thế nào khi xử lý nhiều tệp dự án?**  
A: Aspose.Tasks hoạt động trong‑process và thường đọc một tệp .mpp tiêu chuẩn trong vài mili giây. Đối với các thao tác bulk, hãy cân nhắc tái sử dụng cùng một instance `Project` nếu có thể.

## Kết luận
Bạn đã học cách **read currency properties java** và **extract currency symbol java** từ tệp MS Project bằng Aspose.Tasks cho Java. Khả năng này cho phép bạn tích hợp siêu dữ liệu tiền tệ vào các báo cáo tùy chỉnh, phân tích tài chính, hoặc quy trình tích hợp mà không cần dựa vào Microsoft Project. Hãy tự do thử nghiệm việc sửa đổi các thuộc tính hoặc kết hợp dữ liệu này với các thuộc tính dự án khác để xây dựng các giải pháp phong phú hơn.

---

**Cập nhật lần cuối:** 2026-02-07  
**Kiểm tra với:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}