---
title: Tạo dữ liệu theo pha thời gian trong Aspose.Tasks
linktitle: Tạo dữ liệu theo pha thời gian cho các bài tập tài nguyên trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách tạo dữ liệu theo pha thời gian cho các nhiệm vụ tài nguyên bằng Aspose.Tasks cho Java. Nâng cao hiệu quả quản lý dự án với hướng dẫn toàn diện này.
type: docs
weight: 24
url: /vi/java/resource-assignments/timephased-data-generation/
---
## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình tạo dữ liệu theo pha thời gian cho các nhiệm vụ tài nguyên bằng cách sử dụng Aspose.Tasks cho Java. Dữ liệu theo pha thời gian cung cấp những hiểu biết có giá trị về cách phân bổ nguồn lực theo thời gian trong một dự án, giúp người quản lý dự án đưa ra quyết định sáng suốt.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo rằng bạn đã cài đặt JDK trên hệ thống của mình. Bạn có thể tải xuống và cài đặt JDK từ[đây](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java Library: Bạn cần có thư viện Aspose.Tasks for Java. Bạn có thể tải nó xuống từ[trang mạng](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Trước tiên, hãy nhập các gói cần thiết để làm việc với Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Bước 1: Đọc tệp MPP nguồn
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Data Directory";
// Đọc tệp MPP nguồn
Project project = new Project(dataDir + "project.mpp");
```
## Bước 2: Nhận nhiệm vụ và phân công nguồn lực
```java
// Nhận nhiệm vụ đầu tiên của Project
Task task = project.getRootTask().getChildren().getById(1);
// Nhận sự phân công tài nguyên đầu tiên của dự án
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Bước 3: Tạo dữ liệu theo pha thời gian với đường viền phẳng
```java
// Đường viền phẳng là đường viền mặc định
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Bước 4: Thay đổi đường viền thành Rùa
```java
// Thay đổi đường viền thành Rùa
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Bước 5: Thay đổi đường viền thành BackLoaded
```java
// Thay đổi đường viền thành BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Bước 6: Thay đổi đường viền thành FrontLoaded
```java
// Thay đổi đường viền thành FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Bước 7: Thay đổi đường viền thành chuông
```java
// Thay đổi đường viền thành Chuông
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Bước 8: Thay đổi đường viền thành EarlyPeak
```java
// Thay đổi đường viền thành EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Bước 9: Thay đổi đường viền thành LatePeak
```java
// Thay đổi đường viền thành LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Bước 10: Thay đổi đường viền thành DoublePeak
```java
// Thay đổi đường viền thành DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã đề cập đến cách tạo dữ liệu theo pha thời gian cho các nhiệm vụ tài nguyên bằng cách sử dụng Aspose.Tasks cho Java. Hiểu được các đường nét công việc khác nhau có thể giúp người quản lý dự án quản lý hiệu quả việc phân bổ nguồn lực và lập kế hoạch trong các dự án của họ.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Tasks với các thư viện Java khác không?
Có, Aspose.Tasks có thể được tích hợp với các thư viện Java khác để nâng cao khả năng quản lý dự án.
### Aspose.Tasks có phù hợp với các dự án doanh nghiệp quy mô lớn không?
Hoàn toàn có thể, Aspose.Tasks được thiết kế để xử lý các dự án thuộc mọi quy mô, bao gồm cả các dự án doanh nghiệp quy mô lớn.
### Aspose.Tasks có cung cấp hỗ trợ cho các định dạng tệp dự án khác nhau không?
Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án khác nhau, bao gồm MPP, XML và MPX.
### Tôi có thể tùy chỉnh đường nét công việc theo yêu cầu dự án của mình không?
Có, Aspose.Tasks cho phép người dùng xác định đường viền công việc tùy chỉnh để phù hợp với nhu cầu dự án cụ thể của họ.
### Có diễn đàn cộng đồng nào để tôi có thể nhận trợ giúp về Aspose.Tasks không?
 Có, bạn có thể ghé thăm[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và thảo luận.