---
title: Quản lý thời lượng cơ bản của nhiệm vụ trong Aspose.Tasks
linktitle: Quản lý thời lượng cơ bản của nhiệm vụ trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách quản lý hiệu quả các đường cơ sở của nhiệm vụ trong MS Project bằng cách sử dụng Aspose.Tasks cho Java. Hướng dẫn này hướng dẫn bạn từng bước trong suốt quá trình.
weight: 12
url: /vi/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Quản lý thời lượng cơ bản của nhiệm vụ trong Aspose.Tasks

## Giới thiệu
Quản lý đường cơ sở nhiệm vụ trong MS Project là rất quan trọng để lập kế hoạch và theo dõi dự án. Trong hướng dẫn này, chúng ta sẽ khám phá cách quản lý hiệu quả thời lượng cơ sở của nhiệm vụ bằng cách sử dụng Aspose.Tasks cho Java.
## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:
1. Môi trường phát triển Java: Đảm bảo bạn đã cài đặt Bộ công cụ phát triển Java (JDK) trên hệ thống của mình.
2.  Thư viện Aspose.Tasks: Tải xuống và cài đặt thư viện Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết cho dự án Java của bạn:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Bước 1: Tạo một phiên bản dự án
Khởi tạo một phiên bản dự án mới bằng mã sau:
```java
Project project = new Project();
```
## Bước 2: Tạo đường cơ sở nhiệm vụ
Tạo một nhiệm vụ mới và đặt đường cơ sở của nó bằng mã sau:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Bước 3: Hiển thị thông tin cơ bản của nhiệm vụ
Truy xuất và hiển thị thông tin cơ bản của nhiệm vụ như thời lượng, ngày bắt đầu, ngày kết thúc, v.v.:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Bước 4: Kiểm tra Đường cơ sở tạm thời và Chi phí cố định
Kiểm tra xem đường cơ sở có phải là đường cơ sở tạm thời hay không và truy xuất mọi chi phí cố định liên quan đến nó:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Bước 5: In dữ liệu theo pha thời gian
In dữ liệu theo pha thời gian được liên kết với đường cơ sở của nhiệm vụ:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Bằng cách làm theo các bước này, bạn có thể quản lý hiệu quả thời lượng cơ bản của nhiệm vụ trong MS Project bằng cách sử dụng Aspose.Tasks for Java.

## Phần kết luận
Quản lý đường cơ sở nhiệm vụ là điều cần thiết để quản lý dự án, cho phép bạn theo dõi những sai lệch so với lịch trình đã lên kế hoạch. Với Aspose.Tasks dành cho Java, quy trình này trở nên hợp lý và hiệu quả, cho phép kiểm soát và phân phối dự án tốt hơn.
## Câu hỏi thường gặp
### Đường cơ sở nhiệm vụ trong MS Project là gì?
Đường cơ sở nhiệm vụ trong MS Project là ảnh chụp nhanh về lịch trình dự kiến ban đầu cho một nhiệm vụ, bao gồm ngày bắt đầu, ngày kết thúc và thời lượng.
### Tại sao việc quản lý đường cơ sở của nhiệm vụ lại quan trọng?
Quản lý đường cơ sở nhiệm vụ giúp so sánh lịch trình đã lên kế hoạch với tiến độ thực tế của dự án, tạo điều kiện thuận lợi cho việc theo dõi và ra quyết định tốt hơn.
### Tôi có thể sửa đổi đường cơ sở của nhiệm vụ sau khi nó được đặt không?
Có, bạn có thể sửa đổi đường cơ sở nhiệm vụ trong MS Project để phản ánh những thay đổi trong kế hoạch dự án. Tuy nhiên, điều cần thiết là phải ghi lại mọi sai lệch so với đường cơ sở ban đầu.
### Aspose.Tasks có hỗ trợ các chức năng quản lý dự án khác không?
Có, Aspose.Tasks cung cấp nhiều tính năng để quản lý dự án, bao gồm lập lịch tác vụ, phân bổ nguồn lực và tạo biểu đồ Gantt.
### Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?
 Bạn có thể tìm thấy sự hỗ trợ cho Aspose.Tasks trên[Diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15), nơi bạn có thể đặt câu hỏi và tương tác với những người dùng khác.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
