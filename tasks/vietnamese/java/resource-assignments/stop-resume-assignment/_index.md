---
title: Dừng và tiếp tục phân công tài nguyên trong Aspose.Tasks
linktitle: Dừng và tiếp tục phân công tài nguyên trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách quản lý việc gán tài nguyên một cách hiệu quả trong Aspose.Tasks cho Java với hướng dẫn từng bước này.
weight: 23
url: /vi/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dừng và tiếp tục phân công tài nguyên trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách dừng và tiếp tục các hoạt động gán tài nguyên bằng Aspose.Tasks cho Java. Aspose.Tasks là một API Java mạnh mẽ cho phép các nhà phát triển làm việc với các tệp Microsoft Project mà không cần cài đặt Microsoft Project trên hệ thống của họ. Chúng tôi sẽ chia quy trình thành các bước có thể quản lý được để bạn dễ dàng thực hiện.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Đã tải xuống Aspose.Tasks cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/tasks/java/).
- Hiểu biết cơ bản về lập trình Java.
## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết vào dự án Java của chúng tôi:
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
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
// Tải tập tin dự án
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 Trong bước này, chúng ta tải tệp dự án vào một`Project` đối tượng bằng đường dẫn tệp.
## Bước 2: Lặp lại thông qua phân công tài nguyên
```java
// Xác định ngày tối thiểu
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Lặp lại thông qua các bài tập tài nguyên
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Tại đây, chúng tôi xác định ngày tối thiểu và bắt đầu lặp lại qua từng lần phân công tài nguyên trong dự án.
## Bước 3: Kiểm tra ngày dừng và tiếp tục
```java
    // Kiểm tra ngày dừng
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Kiểm tra ngày sơ yếu lý lịch
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Trong bước này, chúng tôi kiểm tra xem ngày dừng và ngày tiếp tục của mỗi hoạt động phân công nguồn lực có trước ngày tối thiểu hay không. Nếu có, chúng tôi in "NA", nếu không, chúng tôi in ngày tương ứng.
## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách dừng và tiếp tục các hoạt động gán tài nguyên trong Aspose.Tasks cho Java. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng triển khai chức năng này trong các dự án Java của mình.

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks mà không cần cài đặt Microsoft Project không?
Có, Aspose.Tasks cho phép bạn làm việc với các tệp Microsoft Project mà không cần cài đặt Microsoft Project trên hệ thống của bạn.
### Tôi có thể tìm thêm tài liệu ở đâu?
 Bạn có thể tìm tài liệu chi tiết[đây](https://reference.aspose.com/tasks/java/).
### Có bản dùng thử miễn phí không?
 Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ nếu gặp bất kỳ vấn đề nào?
Bạn có thể nhận được sự hỗ trợ từ cộng đồng[đây](https://forum.aspose.com/c/tasks/15).
### Tôi có thể mua giấy phép tạm thời không?
 Có, bạn có thể mua giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
