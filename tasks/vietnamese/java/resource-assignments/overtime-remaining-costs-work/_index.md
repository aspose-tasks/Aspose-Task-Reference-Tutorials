---
title: Giám sát thời gian làm thêm, chi phí còn lại và làm việc trong Aspose.Tasks
linktitle: Giám sát thời gian làm thêm, chi phí còn lại và làm việc trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách giám sát thời gian làm thêm, chi phí còn lại và làm việc trong các dự án Java bằng Aspose.Tasks. Các bước đơn giản để quản lý dự án hiệu quả.
weight: 18
url: /vi/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Giám sát thời gian làm thêm, chi phí còn lại và làm việc trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Tasks cho Java để theo dõi thời gian làm thêm, chi phí còn lại và làm việc trong một dự án. Điều này có thể là vô giá đối với người quản lý dự án và trưởng nhóm để đảm bảo các dự án đi đúng hướng và trong ngân sách.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Bộ công cụ phát triển Java (JDK): Aspose.Tasks dành cho Java yêu cầu Java SE 6 trở lên.
2.  Aspose.Tasks for Java Library: Tải xuống và cài đặt thư viện từ[đây](https://releases.aspose.com/tasks/java/).
3. Môi trường phát triển tích hợp (IDE): Bất kỳ IDE Java nào như Eclipse, IntelliJ IDEA hoặc NetBeans.

## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào tệp Java của bạn:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Bước 1: Thiết lập thư mục dữ liệu
Xác định thư mục chứa tệp dự án của bạn:
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn đến tệp dự án của bạn.
## Bước 2: Tải dự án
 Khởi tạo một`Project` đối tượng và tải tệp dự án:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Thay thế`"ResourceAssignmentOvertimes.mpp"` với tên của tập tin dự án của bạn.
## Bước 3: Lặp lại thông qua phân công tài nguyên
Lặp lại từng nhiệm vụ tài nguyên trong dự án:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Bước 4: In chi phí làm thêm giờ và công việc
Truy xuất và in chi phí làm thêm giờ cũng như công việc cho từng nhiệm vụ tài nguyên:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Bước 5: In chi phí còn lại và công việc
Truy xuất và in chi phí còn lại cũng như công việc cho từng nhiệm vụ tài nguyên:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Bước 6: In chi phí làm thêm giờ và công việc còn lại
Truy xuất và in chi phí làm thêm giờ còn lại và công việc cho từng nhiệm vụ tài nguyên:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Phần kết luận
Giám sát thời gian làm thêm, chi phí còn lại và công việc trong dự án là rất quan trọng để quản lý dự án thành công. Với Aspose.Tasks cho Java, bạn có thể dễ dàng truy cập và theo dõi thông tin này, đảm bảo các dự án của bạn luôn đúng tiến độ và trong ngân sách.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho Java với các thư viện Java khác không?
Có, Aspose.Tasks for Java tương thích với các thư viện và khung công tác Java khác.
### Aspose.Tasks có hỗ trợ các định dạng tệp dự án khác nhau không?
Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án khác nhau bao gồm MPP, XML, v.v.
### Có sẵn phiên bản dùng thử không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).
### Tôi có thể tìm hỗ trợ ở đâu nếu gặp vấn đề?
 Bạn có thể truy cập diễn đàn Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15) để hỗ trợ.
### Làm cách nào tôi có thể mua giấy phép cho Aspose.Tasks?
 Bạn có thể mua giấy phép từ[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
