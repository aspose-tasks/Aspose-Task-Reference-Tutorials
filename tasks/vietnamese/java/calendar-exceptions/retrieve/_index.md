---
date: 2026-01-31
description: Tìm hiểu cách lấy các ngoại lệ lịch từ MS Project bằng Aspose.Tasks cho
  Java và chuyển đổi thời gian UTC sang giờ địa phương. Hướng dẫn Aspose.Tasks cho
  Java này cung cấp các ví dụ mã từng bước.
linktitle: Convert UTC to Local – Calendar Exceptions with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Chuyển đổi UTC sang địa phương – Ngoại lệ lịch với Aspose.Tasks
url: /vi/java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lấy Ngoại Lệ Lịch Trình với Aspose.Tasks lấy các ngoại lệ lịch trình từ tệp Microsoft Project bằng thư viện Aspose.Tasks cho Java. Các ngoại lệ lịch trình đại diện cho các khoảng thời gian không làm việc như ngày lễ hoặc quy tắc giờ làm việc tùy chỉnh, và việc đọc chúng một cách lập trình là cần thiết cho việc cân bằng tài nguyên, báo cáo và logic lập lịch tùy chỉnh. Bằng cách truy cập các ngoại lệ này, bạn cũng có thể **chuyển đổi UTC sang giờ địa phương** để tính toán lịch trình chính xác. Chúng tôi sẽ hướng dẫn toàn bộ quy trình từng bước, để bạn có thể tích hợp khả năng này vào các ứng dụng Java của mình một cách tự tin.

## Câu trả lời nhanh
- **Bài hướng dẫn này đề cập đến gì?** Lấy các ngoại lệ lịch trình từ tệp MPP bằng Aspose.Tasks cho Java.  
- **Thời gian triển khai khoảng bao lâu?** Khoảng 10‑15 phút cho một cấu hình cơ bản.  
- **Yêu cầu trước?** JDK, Aspose.Tasks cho Java và một IDE (IntelliJ IDEA hoặc Eclipse).  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các phiên bản Project được hỗ trợ?** Tất cả các định dạng MS Project chính (MPP, MPT, XML).

## Aspose.Tasks java tutorial là gì án Java. Nó cung cấp các đoạn mã cụ thể, giải thích các thực tiễn tốt nhất và các kịch bản thực tế để các nhà phát triển có thể thao tác với tệp Project mà không cần lịch trình?
Hiểu các ngoại lệ lịch trình cho phép ngày lễ và lịch làm việc tùy chỉnh.
- Xây dựng các công cụ báo cáo tùy chỉnh làm nổi bật các ngày không làm việc.
- **Chuyển đổi UTC sang giờ địa phương** khi tổng hợp dụ: ERP, HR).

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn đã chuẩn bị các yêu cầu sau:

1. **Java Development Kit (JDK)** – Đảm bảo bạn đã cài đặt JDK 8 trở lên.  
2. **Aspose.Tasks cho Java** – Tải và cài đặt Aspose.Tasks cho Java từ [đây](https://releases.aspose.com/tasks/java/).  
3 Bạn có thể dùngJ IDEA hoặc Eclipse.

## Nhập khẩu các gói
Đầu tiên, bạn cần nhập các gói cần thiết để làm việc với Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Bước 1: Thiết lập Thư mục Dữ liệu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **Mẹo chuyên nghiệp:** Sử dụng đường dẫn tuyệt đối hoặc đường dẫn tương đối so với thư mục resources của dự án để2: Tải tệp MS Project
```java
Project project = new Project(dataDir + "project.mpp");
```

Dòng này khởi tạo một đối tượng `Project` mới bằng cách tải tệp MS Project được chỉ định bởi đường dẫn.

## Bước 3: Lấy Ngoại Lệ Lịch Trình
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

Ở đây, chúng ta lặp qua từng lịch trong dự án và sau đó lặp qua từng ngoại lệ lịch trong lịch đó. Chúng ta in ra phương bằng ngoại lệ lịch trình
Khi bạn lấy các giá trị `FromDate` và `ToDate`, chúng mặc định được biểu thị ở dạng UTC. Để làm việc với lịch địa phương, bạn có thể chuyển đổi chúng như sau (chỉ mang tính minh họa – mã chuyển đổi thực tế.time.ZoneId` để chỉ định múi giờ().atZone(targetZone dự án đa quốc gia.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| **Không có đầu ra nào được in** | Tệp dự án không chứa bất kỳ ngoại lệ lịch nào. | Kiểm tra lại lịch trong MS Project đã định nghĩa các ngoại lệ (ví dụ: ngày lễ). |
| **`NullPointerException`** | Đường dẫn `dataDir` không đúng hoặc tệp không tồn tại. | tồn tại. |
| **Múi giờ không khớp** | Ngày được hiển thị ở dạng UTC. | Sử dụng `calExc.getFromDate().toLocalDateTime()` để chuyển sang giờ địa phương nếu cần. |

## Câu hỏi thường gặp
### Aspose.Tasks có hỗ trợ các phiên bản tệp MS Project khác nhau không?
Có, Aspose.Tasks hỗ trợ nhiều phiên bản tệp MS Project, bao gồm các định dạng MPP, MPT và XML.

### Có bản từ [đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu cho Aspose.Tasks cho Java ở đâu?
Bạn có thể tham khảo tài liệu [tại đây](https://reference.aspose.com/tasks/java/).

### Làm sao để nhận hỗ trợ cho Aspose.Tasks?
Bạn có thể nhận hỗ trợ từ diễn đàn cộng đồng [tại đây](https://forum.aspose.com/c/tasks/15).

### Có tùy chọn giấy phép tạm thời cho Aspose.Tasks không?
Có, bạn có thể lấy giấy phép tạm thời từ [đây](https://purchase.aspose.com/temporary-license/).

**Câu hỏi & Trả lời bổ sung**

**Hỏi:** *Tôi có thể chỉnh sửa các ngoại lệ lịch sau khi đã lấy chúng không?*  
**Đáp:** Chắc chắn. Sử dụng `CalendarException.setFromDate()` và `setToDate()` để điều chỉnh ngày, sau đó lưu dự án bằng `project.save(...)`.

**Hỏi:** *Aspose.Tasks có giữ lại các trường tùy chỉnh trên lịch không?*  
**Đáp:** Có, tất cả các trường tùy chỉnh và thuộc tính mở rộng được giữ nguyên khi tải và lưu dự án.

**Hỏi:** *Làm sao tôi chuyển đổi các ngày UTC đã lấy được sang múi giờ địa phương của mình?*  
**Đáp:** Áp dụng các phương thức chuyển đổi `ZoneId` và `ZonedDateTime` của Java lên các đối tượng `Date địa phương của bạn.

## cách lấy các ngoại lệ lịch trình từ MS Project bằng Aspose.Tasks cho Java và cách ** chức năng này vào các ứng dụng Java của mình, cung cấp các tính năng lập lịch phong phú hơn và phân tích dự án chính xác hơn.

---

**Cập nhật lần cuối:** 2026-01-31  
**Kiểm tra với:** Aspose.Tasks cho Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}