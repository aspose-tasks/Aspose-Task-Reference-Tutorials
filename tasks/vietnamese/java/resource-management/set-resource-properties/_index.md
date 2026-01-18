---
date: 2026-01-18
description: Học cách đặt tỷ lệ chuẩn và các thuộc tính tài nguyên khác trong MS Project
  bằng Aspose.Tasks cho Java, bao gồm cách thêm tài nguyên vào MS Project và quản
  lý tài nguyên một cách hiệu quả.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Đặt Mức Giá Chuẩn cho Tài Nguyên trong Aspose.Tasks
url: /vi/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Mức Giá Chuẩn cho Tài Nguyên trong Aspose.Tasks

## Giới thiệu
Nếu bạn đang xây dựng các ứng dụng Java cần tương tác với các tệp Microsoft Project, **đặt mức giá chuẩn** cho một tài nguyên là một trong những nhiệm vụ phổ biến nhất. Trong hướng dẫn này, bạn sẽ học cách **đặt mức giá chuẩn** và các thuộc tính tài nguyên khác bằng Aspose.Tasks cho Java. Khi hoàn thành, bạn sẽ có thể tạo một đối tượng dự án, thêm một tài nguyên vào tệp MS Project và quản lý các tài nguyên MS Project một cách tự tin.

## Câu trả lời nhanh
- **Lớp chính để làm việc với tệp Project là gì?** `Project`
- **Phương thức nào thêm một tài nguyên mới?** `project.getResources().add()`
- **Làm thế nào để đặt mức giá chuẩn?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Có cần giấy phép cho môi trường sản xuất không?** Có, cần một giấy phép Aspose.Tasks hợp lệ.
- **Phiên bản Java nào được hỗ trợ?** Java 8+ (khuyến nghị sử dụng JDK mới nhất).

## “set standard rate” là gì?
Thao tác *set standard rate* gán một chi phí giờ mặc định cho một tài nguyên. Các nhà quản lý dự án sử dụng giá trị này để tính chi phí nhân công, tạo báo cáo chi phí và dự báo ngân sách.

## Tại sao nên đặt mức giá bằng Aspose.Tasks?
- **Không cần cài đặt Microsoft Project** – thao tác trực tiếp trên tệp từ Java.
- **Độ chính xác cao** – mọi trường tài nguyên, bao gồm giờ làm thêm và mức chi phí, đều được bảo toàn.
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS.
- **Thân thiện với tự động hoá** – lý tưởng cho xử lý hàng loạt hoặc tích hợp vào pipeline CI.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn đã có các thành phần sau:

### Cài đặt môi trường phát triển Java
1. Cài đặt JDK: Đảm bảo bạn đã cài đặt Java Development Kit (JDK) trên hệ thống. Bạn có thể tải về từ [trang web Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Cài đặt IDE: Chọn một Integrated Development Environment (IDE) như IntelliJ IDEA, Eclipse hoặc NetBeans và cài đặt trên máy của bạn.

### Cài đặt Aspose.Tasks cho Java
1. Tải Aspose.Tasks cho Java: Truy cập [trang tải xuống](https://releases.aspose.com/tasks/java/) và tải phiên bản mới nhất của Aspose.Tasks cho Java.
2. Tích hợp vào dự án: Thêm thư viện Aspose.Tasks cho Java vào dự án Java của bạn dưới dạng dependency.

## Nhập khẩu các gói
Để bắt đầu, bạn cần nhập các gói cần thiết từ Aspose.Tasks cho Java vào dự án. Bước này đảm bảo bạn có quyền truy cập vào các chức năng cần thiết.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Bước 1: Tạo Đối tượng Project
Việc tạo **đ tượng project** là bước đầu tiên cho bất kỳ thao tác nào với MS Project. Nó đại diện cho toàn bộ tệp dự án trong bộ nhớ.

```java
Project project = new Project();
```

## Bước 2: Thêm một Tài nguyên (add resource ms project)
Bây giờ chúng ta sẽ **thêm tài nguyên MS Project** bằng bộ sưu tập Resources. Tên tài nguyên có thể là bất kỳ gì phù hợp với lịch trình của bạn.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Bước 3: Đặt Thuộc tính Tài nguyên (how to set rates)
Ở đây chúng ta **đặt mức giá chuẩn** và cũng minh họa cách đặt mức giá làm thêm giờ. Các mức giá này được lưu dưới dạng giá trị `BigDecimal` để duy trì độ chính xác.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| `NullPointerException` khi gọi `set` | Tài nguyên không được thêm đúng cách. | Đảm bảo `project.getResources().add()` trả về một `Resource` không null. |
| Mức giá hiển thị là 0 trong tệp đã lưu | Sử dụng `int` thay vì `BigDecimal`. | Luôn dùng `BigDecimal.valueOf()` cho các giá trị tiền tệ. |
| Không tìm thấy giấy phép | Tệp giấy phép chưa được tải trước khi tạo `Project`. | Tải giấy phép (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) ở đầu chương trình. |

## Kết luận
Bằng cách thực hiện các bước trên, bạn đã học cách **tạo một đối tượng project**, **thêm tài nguyên MS Project**, và **đặt mức giá chuẩn** cùng các thuộc tính tài nguyên khác. Điều này cho phép bạn tự động hoá việc tính toán chi phí, tạo báo cáo tùy chỉnh và quản lý toàn bộ tài nguyên MS Project từ Java.

## Câu hỏi thường gặp
### Aspose.Tasks cho Java có thể xử lý các tệp MS Project phức tạp không?
Có, Aspose.Tasks cho Java có khả năng xử lý đa dạng các định dạng tệp MS Project, bao gồm cả những tệp phức tạp với cấu trúc nhiệm vụ sâu.

### Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Tasks cho Java từ [đây](https://releases.aspose.com/).

### Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho Java ở đâu?
Bạn có thể tìm kiếm trợ giúp và tham gia thảo luận liên quan đến Aspose.Tasks cho Java trên [diễn đàn hỗ trợ](https://forum.aspose.com/c/tasks/15).

### Làm sao để lấy giấy phép tạm thời cho Aspose.Tasks cho Java?
Bạn có thể lấy giấy phép tạm thời từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.

### Tôi có thể mua phiên bản có giấy phép của Aspose.Tasks cho Java ở đâu?
Bạn có thể mua phiên bản có giấy phép của Aspose.Tasks cho Java từ [trang mua hàng](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose