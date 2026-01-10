---
date: 2026-01-10
description: Tìm hiểu cách dừng việc gán, quản lý các gán tài nguyên và xem ví dụ
  về gán tài nguyên trong Aspose.Tasks cho Java thông qua hướng dẫn từng bước này.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Dừng Phân Công và Tiếp Tục Phân Công Tài Nguyên trong Aspose.Tasks
url: /vi/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Dừng Giao Nhiệm Vụ và Tiếp Tục Giao Nhiệm Vụ Tài Nguyên trong Aspose.Tasks

## Giới thiệu
Trong tutorial này, **bạn sẽ khám phá cách dừng giao nhiệm vụ** và sau đó tiếp tục nó bằng cách sử dụng Aspose.Tasks cho Java. Aspose.Tasks là một API Java mạnh mẽ cho phép bạn đọc các định dạng tệp dự án Java, thao tác dữ liệu Microsoft Project, và quản lý các giao nhiệm vụ tài nguyên mà không cần cài đặt Microsoft Project. Chúng tôi sẽ hướng dẫn từng bước, giải thích lý do mỗi dòng quan trọng, và cung cấp các mẹo thực tế bạn có thể áp dụng cho các dự án thực tế.

## Câu trả lời nhanh
- **“Dừng giao nhiệm vụ” có nghĩa là gì?** Nó đánh dấu một giao nhiệm vụ tài nguyên là tạm thời không hoạt động kể từ một ngày dừng cụ thể.  
- **Tôi có thể tiếp tục cùng một giao nhiệm vụ sau không?** Có, bằng cách đặt ngày tiếp tục cho cùng một giao nhiệm vụ.  
- **Có cần Microsoft Project để sử dụng API này không?** Không, Aspose.Tasks hoạt động độc lập với Microsoft Project.  
- **Phiên bản Java nào được yêu cầu?** Java 8 hoặc cao hơn được khuyến nghị.  
- **Tôi có thể tải thư viện ở đâu?** Từ trang tải xuống chính thức của Aspose.Tasks Java.

## “Dừng giao nhiệm vụ” là gì trong ngữ cảnh của Aspose.Tasks?
Dừng một giao nhiệm vụ cho trình lập lịch bỏ qua công việc được phân bổ cho tài nguyên sau **ngày dừng** cho đến **ngày tiếp tục** (nếu có). Điều này hữu ích cho việc xử lý kỳ nghỉ, thời gian ngừng hoạt động của thiết bị, hoặc bất kỳ khoảng thời gian nào mà tài nguyên không nên được coi là hoạt động.

## Tại sao nên sử dụng Aspose.Tasks để quản lý giao nhiệm vụ tài nguyên?
- **Không cần Microsoft Project** – làm việc trực tiếp với các tệp .mpp.  
- **Kiểm soát đầy đủ ngày tháng** – bạn có thể kiểm tra và điều chỉnh ngày dừng, ngày tiếp tục bằng mã.  
- **Đa nền tảng** – chạy trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **API phong phú** – cung cấp một *ví dụ về giao nhiệm vụ tài nguyên* mà bạn có thể mở rộng cho báo cáo tùy chỉnh.

## Yêu cầu trước
- Java Development Kit (JDK) đã được cài đặt trên hệ thống của bạn.  
- Thư viện Aspose.Tasks cho Java đã được tải xuống. Bạn có thể tải nó từ [here](https://releases.aspose.com/tasks/java/).  
- Kiến thức cơ bản về lập trình Java.  

## Nhập khẩu các gói
Đầu tiên, hãy nhập các gói cần thiết vào dự án Java của chúng ta:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Bước 1: Tải tệp dự án
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Ở đây chúng ta **đọc tệp dự án Java** định dạng (`.mpp`) và tạo một đối tượng `Project` cho phép chúng ta truy cập vào tất cả dữ liệu dự án, bao gồm cả các giao nhiệm vụ tài nguyên.

## Bước 2: Duyệt qua các giao nhiệm vụ tài nguyên
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Chúng ta đặt một **ngày tối thiểu** để lọc ra các ngày placeholder và sau đó lặp qua mỗi giao nhiệm vụ. Đây là mẫu *ví dụ về giao nhiệm vụ tài nguyên* điển hình được sử dụng khi bạn cần kiểm tra hoặc sửa đổi các giao nhiệm vụ.

## Bước 3: Kiểm tra ngày dừng và ngày tiếp tục
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

Trong khối này chúng ta **kiểm tra ngày dừng** và **kiểm tra ngày tiếp tục** cho mỗi giao nhiệm vụ. Nếu ngày đó trước `minDate` của chúng ta, chúng ta coi nó là chưa được đặt (`"NA"`); ngược lại chúng ta in ra ngày thực tế. Logic này rất quan trọng để **quản lý giao nhiệm vụ tài nguyên** một cách chính xác.

## Các vấn đề thường gặp và giải pháp
- **Ngày null** – `ra.get(Asn.STOP)` có thể trả về `null`. Bảo vệ bằng cách thêm kiểm tra null trước khi gọi `.before(minDate)`.  
- **Đường dẫn tệp không đúng** – Đảm bảo `dataDir` kết thúc bằng dấu phân tách đường dẫn (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Phiên bản không khớp** – Sử dụng phiên bản mới nhất của Aspose.Tasks cho Java để tránh thiếu các giá trị enum.  

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks mà không cần cài đặt Microsoft Project không?
Có, Aspose.Tasks cho phép bạn làm việc với các tệp Microsoft Project mà không cần cài đặt Microsoft Project trên hệ thống của mình.

### Tôi có thể tìm tài liệu chi tiết ở đâu?
Bạn có thể tìm tài liệu chi tiết [here](https://reference.aspose.com/tasks/java/).

### Có bản dùng thử miễn phí không?
Có, bạn có thể nhận bản dùng thử miễn phí [here](https://releases.aspose.com/).

### Làm sao tôi có thể nhận hỗ trợ nếu gặp vấn đề?
Bạn có thể nhận hỗ trợ từ cộng đồng [here](https://forum.aspose.com/c/tasks/15).

### Tôi có thể mua giấy phép tạm thời không?
Có, bạn có thể mua giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

## Câu hỏi thường gặp

**H: Làm thế nào để lập trình đặt ngày dừng cho một giao nhiệm vụ?**  
Đ: Sử dụng `ra.set(Asn.STOP, yourDateObject);` trong đó `yourDateObject` là một `java.util.Date`.

**H: Điều gì sẽ xảy ra nếu ngày tiếp tục sớm hơn ngày dừng?**  
Đ: API không ép buộc thứ tự thời gian; tuy nhiên, trình lập lịch sẽ coi giao nhiệm vụ là hoạt động chỉ sau ngày muộn hơn trong hai ngày, vì vậy bạn nên tự kiểm tra tính hợp lệ của các ngày.

**H: Tôi có thể lọc các giao nhiệm vụ chỉ có ngày dừng được đặt không?**  
Đ: Có, duyệt qua `prj.getResourceAssignments()` và kiểm tra `ra.get(Asn.STOP) != null`.

**H: Có thể xóa ngày dừng đã đặt không?**  
Đ: Đặt ngày dừng thành `null` bằng `ra.set(Asn.STOP, null);` và sau đó lưu dự án.

**H: Aspose.Tasks có hỗ trợ các trường liên quan đến ngày khác như start, finish, hoặc actual start không?**  
Đ: Chắc chắn. Enum `Asn` cung cấp các hằng số cho tất cả các trường giao nhiệm vụ, chẳng hạn như `Asn.START`, `Asn.FINISH`, v.v.

## Kết luận
Bằng cách thực hiện các bước trên, bạn đã biết **cách dừng giao nhiệm vụ**, kiểm tra các ngày dừng/tiếp tục, và tiếp tục giao nhiệm vụ khi cần. Khả năng này cho phép bạn **quản lý giao nhiệm vụ tài nguyên** một cách chính xác hơn, đặc biệt trong các tình huống như kỳ nghỉ của tài nguyên hoặc thời gian ngừng hoạt động của thiết bị. Hãy tự do mở rộng ví dụ để cập nhật ngày, tạo báo cáo, hoặc tích hợp với logic lập lịch của riêng bạn.

---

**Cập nhật lần cuối:** 2026-01-10  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}