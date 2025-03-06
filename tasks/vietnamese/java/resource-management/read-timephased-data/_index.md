---
title: Đọc dữ liệu theo pha thời gian cho tài nguyên trong Aspose.Tasks
linktitle: Đọc dữ liệu theo pha thời gian cho tài nguyên trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách trích xuất dữ liệu theo pha thời gian từ tài nguyên MS Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước.
type: docs
weight: 15
url: /vi/java/resource-management/read-timephased-data/
---
## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình đọc dữ liệu theo pha thời gian cho tài nguyên MS Project bằng Aspose.Tasks cho Java. Thư viện này cung cấp các chức năng mạnh mẽ để quản lý các tệp Microsoft Project theo chương trình.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình. Bạn có thể tải nó xuống từ[trang mạng](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) và làm theo hướng dẫn cài đặt.
2.  Aspose.Tasks cho Thư viện Java: Tải xuống thư viện Aspose.Tasks cho Java từ[trang tải xuống](https://releases.aspose.com/tasks/java/) và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu.

## Gói nhập khẩu
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Bước 1: Thiết lập thư mục dữ liệu
Đầu tiên, xác định thư mục chứa tệp MS Project của bạn.
```java
String dataDir = "Your Data Directory";
```
## Bước 2: Đọc tệp mẫu dự án MS
Chỉ định tên của tệp mẫu MS Project của bạn.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Bước 3: Đọc tệp đầu vào dưới dạng dự án
Đọc tệp đầu vào bằng Aspose.Tasks và tải nó dưới dạng đối tượng Project.
```java
Project project = new Project(dataDir + fileName);
```
## Bước 4: Nhận tài nguyên theo ID
Truy xuất tài nguyên mong muốn từ dự án bằng mã định danh duy nhất (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Bước 5: In dữ liệu theo pha thời gian cho công việc tài nguyên
In dữ liệu theo pha thời gian cho công việc tài nguyên.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Bước 6: In dữ liệu theo pha thời gian cho chi phí tài nguyên
In dữ liệu theo pha thời gian cho chi phí tài nguyên.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách đọc dữ liệu theo pha thời gian cho tài nguyên MS Project bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước này, bạn có thể trích xuất thông tin có giá trị từ các tệp dự án của mình một cách hiệu quả theo chương trình.
## Câu hỏi thường gặp
### Aspose.Tasks có thể xử lý các loại tệp dự án khác ngoài Microsoft Project không?
Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp khác nhau, bao gồm MPP, XML và CSV.
### Aspose.Tasks có tương thích với các môi trường phát triển Java khác nhau không?
Có, Aspose.Tasks tương thích với tất cả các IDE và khung công tác Java chính.
### Tôi có thể thao tác dữ liệu dự án bằng Aspose.Tasks không?
Hoàn toàn có thể, Aspose.Tasks cung cấp các API mở rộng để tạo, sửa đổi và phân tích dữ liệu dự án.
### Aspose.Tasks có phù hợp với các dự án cấp doanh nghiệp không?
Có, Aspose.Tasks được sử dụng rộng rãi trong môi trường doanh nghiệp do độ tin cậy và khả năng mở rộng của nó.
### Tôi có thể tìm hỗ trợ ở đâu nếu gặp sự cố khi sử dụng Aspose.Tasks?
 Bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận được sự hỗ trợ từ cộng đồng và nhóm hỗ trợ.