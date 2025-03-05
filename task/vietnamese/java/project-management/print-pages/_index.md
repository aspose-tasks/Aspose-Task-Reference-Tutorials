---
title: In các trang để tách hình ảnh trong Aspose.Tasks
linktitle: In các trang để tách hình ảnh trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách in các trang để tách hình ảnh trong Aspose.Tasks cho Java. Cải thiện trực quan hóa dự án với hướng dẫn từng bước này.
type: docs
weight: 22
url: /vi/java/project-management/print-pages/
---
## Giới thiệu
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình in các trang để tách các hình ảnh bằng Aspose.Tasks cho Java. Chức năng này có thể đặc biệt hữu ích khi bạn cần trực quan hóa bố cục dự án hoặc các nhiệm vụ quan trọng một cách riêng biệt.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
1.  Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình. Bạn có thể tải nó xuống từ[đây](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java Library: Tải xuống và đưa thư viện Aspose.Tasks for Java vào dự án của bạn. Bạn có thể lấy nó từ[đây](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Đảm bảo nhập các gói cần thiết ở đầu tệp Java của bạn:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Bước 1: Tải dữ liệu dự án
Đầu tiên, tải dữ liệu dự án từ tệp MPP của bạn:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Bước 2: Đặt tùy chọn lưu ảnh
Xác định các tùy chọn để lưu hình ảnh, bao gồm ngày bắt đầu, ngày kết thúc, nhiệm vụ quan trọng, chú giải và đường lưới:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Bước 3: Tùy chỉnh đường lưới
Tùy chỉnh đường lưới cho hình ảnh, chỉ định loại, màu sắc và mẫu:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Bước 4: Lưu hình ảnh
Lưu bố cục dự án dưới dạng hình ảnh, cả dưới dạng một tệp và các tệp riêng biệt:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày cách in các trang để tách các hình ảnh bằng Aspose.Tasks cho Java. Bằng cách làm theo các bước được nêu ở trên, bạn có thể hình dung một cách hiệu quả bố cục dự án và các nhiệm vụ quan trọng theo yêu cầu của mình.
## Câu hỏi thường gặp
### Hỏi: Tôi có thể tùy chỉnh định dạng hình ảnh khi lưu bố cục dự án không?
 Trả lời: Có, Aspose.Tasks for Java hỗ trợ nhiều định dạng hình ảnh khác nhau như PNG, JPEG, BMP, v.v. Bạn có thể chỉ định định dạng mong muốn trong`ImageSaveOptions` lớp học.
### Câu hỏi: Aspose.Tasks dành cho Java có tương thích với các môi trường phát triển Java khác nhau không?
Trả lời: Có, Aspose.Tasks cho Java tương thích với hầu hết các môi trường phát triển Java, bao gồm Eclipse, IntelliJ IDEA và NetBeans.
### Câu hỏi: Tôi có thể tích hợp Aspose.Tasks cho Java vào dự án Maven hoặc Gradle của mình không?
Trả lời: Có, bạn có thể dễ dàng tích hợp Aspose.Tasks cho Java vào dự án Maven hoặc Gradle của mình bằng cách thêm phần phụ thuộc thích hợp vào`pom.xml` hoặc`build.gradle` tài liệu.
### Câu hỏi: Aspose.Tasks cho Java có hỗ trợ xuất dữ liệu dự án sang các định dạng khác ngoài hình ảnh không?
Trả lời: Có, Aspose.Tasks for Java hỗ trợ xuất dữ liệu dự án sang nhiều định dạng khác nhau như PDF, HTML, XLSX, v.v., mang lại sự linh hoạt trong việc hiển thị và báo cáo dữ liệu.
### Câu hỏi: Có hỗ trợ cộng đồng nào dành cho Aspose.Tasks dành cho Java không?
 Đáp: Có, bạn có thể tìm sự hỗ trợ của cộng đồng, đặt câu hỏi và tương tác với những người dùng khác trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).