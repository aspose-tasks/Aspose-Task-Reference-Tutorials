---
date: 2026-01-10
description: Tìm hiểu cách thay đổi đường viền và tạo dữ liệu theo thời gian cho các
  phân công tài nguyên bằng Aspose.Tasks cho Java, cải thiện hiệu quả quản lý dự án.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách thay đổi Contour trong Aspose.Tasks cho dữ liệu theo thời gian
url: /vi/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thay Đổi Contour trong Aspose.Tasks cho Dữ Liệu Theo Thời Gian

## Introduction
Trong hướng dẫn này, bạn sẽ khám phá **cách thay đổi contour** cho một phân công tài nguyên và tạo dữ liệu theo thời gian bằng Aspose.Tasks cho Java. Dữ liệu theo thời gian hiển thị sự phân bố công việc trên dòng thời gian của dự án, cho phép bạn tinh chỉnh lịch trình, cân bằng khối lượng công việc và đưa ra các quyết định dựa trên dữ liệu.

## Quick Answers
- **Contour là gì?** Contour công việc xác định cách nỗ lực được phân bổ trong suốt thời gian thực hiện một nhiệm vụ (ví dụ: Flat, Turtle, Bell).  
- **Tại sao phải thay đổi contour?** Để phản ánh các mẫu công việc thực tế như việc tập trung nỗ lực ở đầu hoặc cuối giai đoạn.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho Java (bất kỳ phiên bản gần đây nào).  
- **Có cần giấy phép không?** Có, cần một giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.  
- **Có thể xem kết quả trong console không?** Mẫu sẽ in ra ngày bắt đầu và giá trị cho mỗi đoạn dữ liệu theo thời gian.

## What is “how to change contour”?
Thay đổi contour có nghĩa là cập nhật thuộc tính `WORK_CONTOUR` của một `ResourceAssignment`. Aspose.Tasks hỗ trợ một số contour được định nghĩa trước (Flat, Turtle, Bell, v.v.) ảnh hưởng đến cách công việc được phân bổ theo thời gian.

## Why use Aspose.Tasks to generate timephased data?
- **Báo cáo chính xác:** Xuất phân bố công việc chi tiết cho các công cụ báo cáo.  
- **Lập kế hoạch kịch bản:** Kiểm tra các contour khác nhau mà không thay đổi lịch trình gốc.  
- **Tự động hoá:** Tích hợp vào các pipeline CI để tự động xác thực tình trạng dự án.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có các yêu cầu sau:
1. Java Development Kit (JDK): Đảm bảo rằng bạn đã cài đặt JDK trên hệ thống. Bạn có thể tải và cài đặt JDK từ [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java Library: Bạn cần có thư viện Aspose.Tasks cho Java. Bạn có thể tải xuống từ [website](https://releases.aspose.com/tasks/java/).

## Import Packages
Đầu tiên, hãy nhập các gói cần thiết để làm việc với Aspose.Tasks:
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
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Bước 2: Lấy Task và Phân công Tài nguyên
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Cách Thay Đổi Contour – Flat (Mặc định)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Contour – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Contour – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Contour – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Contour – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Contour – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Contour – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Contour – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Các Vấn Đề Thường Gặp & Mẹo
- **Contour không cập nhật?** Đảm bảo bạn gọi `firstRA.set(Asn.WORK_CONTOUR, …)` *trước* khi lấy dữ liệu theo thời gian.
- **Giá trị không mong đợi?** Kiểm tra xem ngày bắt đầu và kết thúc của task đã được đặt đúng trong tệp MPP nguồn.
- **Mẹo hiệu năng:** Tái sử dụng cùng một đối tượng `Project` khi lặp qua nhiều contour để tránh việc I/O tệp không cần thiết.

## Câu Hỏi Thường Gặp
### Tôi có thể sử dụng Aspose.Tasks với các thư viện Java khác không?
Có, Aspose.Tasks có thể được tích hợp với các thư viện Java khác để nâng cao khả năng quản lý dự án.

### Aspose.Tasks có phù hợp cho các dự án doanh nghiệp quy mô lớn không?
Chắc chắn, Aspose.Tasks được thiết kế để xử lý các dự án ở mọi quy mô, bao gồm cả các sáng kiến doanh nghiệp quy mô lớn.

### Aspose.Tasks có hỗ trợ các định dạng tệp dự án khác nhau không?
Có, Aspose.Tasks hỗ trợ đa dạng các định dạng, chẳng hạn như MPP, XML và MPX.

### Tôi có thể tùy chỉnh contour công việc theo yêu cầu dự án của mình không?
Có, bạn có thể định nghĩa các contour công việc tùy chỉnh để phù hợp với nhu cầu lập lịch cụ thể.

### Có diễn đàn cộng đồng nào mà tôi có thể nhận hỗ trợ về Aspose.Tasks không?
Có, bạn có thể truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và thảo luận.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}