---
title: Tính toán phần trăm tài nguyên dự án MS với Aspose.Tasks
linktitle: Thực hiện tính toán tỷ lệ phần trăm cho tài nguyên trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách tính tỷ lệ phần trăm tài nguyên MS Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước kèm theo các ví dụ về mã.
weight: 14
url: /vi/java/resource-management/percentage-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tính toán phần trăm tài nguyên dự án MS với Aspose.Tasks

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách thực hiện tính toán phần trăm cho tài nguyên MS Project bằng Aspose.Tasks cho Java. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình tận dụng Aspose.Tasks để thao tác và trích xuất dữ liệu tài nguyên từ các tệp Microsoft Project một cách hiệu quả. Aspose.Tasks là một API Java mạnh mẽ cung cấp các tính năng toàn diện để làm việc với các tài liệu Microsoft Project, cho phép các nhà phát triển tích hợp liền mạch các chức năng quản lý dự án vào các ứng dụng Java của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:
### Môi trường phát triển Java
 Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình. Bạn có thể tải xuống và cài đặt JDK từ[đây](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Thư viện Aspose.Tasks
Bạn cần tích hợp thư viện Aspose.Tasks vào dự án Java của mình. Nếu bạn chưa làm như vậy, bạn có thể tải xuống thư viện từ[đây](https://releases.aspose.com/tasks/java/) và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu[đây](https://reference.aspose.com/tasks/java/).

## Gói nhập khẩu
Trước khi bắt đầu viết mã, hãy nhập các gói cần thiết cho hướng dẫn này:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## Bước 1: Thiết lập đường dẫn tệp dự án
```java
String dataDir = "Your Data Directory";
```
 Thay thế`"Your Data Directory"` với đường dẫn đến tệp Microsoft Project của bạn.
## Bước 2: Tải dự án
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Mã này tải tệp Microsoft Project có tên "Software Development.mpp" nằm trong thư mục dữ liệu đã chỉ định.
## Bước 3: Lặp lại thông qua tài nguyên
```java
for (Resource res : prj.getResources()) {
```
Chúng tôi lặp qua từng tài nguyên trong dự án.
## Bước 4: Kiểm tra tên tài nguyên và phần trăm công việc hoàn thành
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Chúng tôi kiểm tra xem tên tài nguyên có rỗng hay không và sau đó in phần trăm công việc đã hoàn thành cho mỗi tài nguyên.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sử dụng Aspose.Tasks cho Java để thực hiện tính toán phần trăm cho tài nguyên MS Project một cách hiệu quả. Bằng cách làm theo các bước này, bạn có thể tích hợp liền mạch các chức năng quản lý dự án vào các ứng dụng Java của mình, cung cấp khả năng kiểm soát nâng cao và hiểu biết sâu sắc về việc sử dụng tài nguyên dự án.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks cho Java với các khung công tác Java khác không?
Có, Aspose.Tasks cho Java tương thích với nhiều khung Java khác nhau như Spring, Hibernate, v.v.
### Aspose.Tasks có hỗ trợ tất cả các phiên bản của tệp Microsoft Project không?
Aspose.Tasks cung cấp hỗ trợ cho tất cả các phiên bản của tệp Microsoft Project, bao gồm MPP, MPT, XML, v.v.
### Tôi có thể thao tác lịch trình dự án bằng Aspose.Tasks không?
Hoàn toàn có thể, Aspose.Tasks cung cấp các tính năng toàn diện để thao tác lịch trình dự án, bao gồm nhiệm vụ, tài nguyên, lịch, v.v.
### Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks không?
 Có, bạn có thể tìm sự trợ giúp và tương tác với những người dùng khác trên diễn đàn cộng đồng Aspose.Tasks[đây](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks có cung cấp giấy phép tạm thời cho mục đích đánh giá không?
 Có, bạn có thể xin giấy phép tạm thời để đánh giá từ[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
