---
title: Đọc MS Project từ Primavera với Aspose.Tasks cho Java
linktitle: Đọc dự án từ Primavera trong Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Tìm hiểu cách đọc liền mạch các tệp MS Project từ Primavera XML bằng cách sử dụng Aspose.Tasks cho Java. Nâng cao hiệu quả quản lý dự án của bạn.
weight: 20
url: /vi/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc MS Project từ Primavera với Aspose.Tasks cho Java

## Giới thiệu
Trong quản lý dự án, khả năng tương tác giữa các nền tảng phần mềm khác nhau là rất quan trọng để có quy trình làm việc liền mạch. Aspose.Tasks for Java cung cấp chức năng mạnh mẽ để đọc các tệp Microsoft Project từ Primavera XML. Hướng dẫn này sẽ hướng dẫn bạn qua quá trình đọc các tệp MS Project từ Primavera bằng cách sử dụng Aspose.Tasks cho Java, cho phép bạn kiểm tra các thuộc tính dành riêng cho Primavera của nhiệm vụ một cách hiệu quả.
## Điều kiện tiên quyết
Trước khi tiếp tục, hãy đảm bảo bạn đã cài đặt và thiết lập các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Tasks cho Java: Tải xuống và cài đặt Aspose.Tasks cho Java từ[đây](https://releases.aspose.com/tasks/java/).

## Gói nhập khẩu
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Bước 1: Thiết lập thư mục dữ liệu
```java
String dataDir = "Your Data Directory";
```
 Đảm bảo thay thế`"Your Data Directory"` với đường dẫn thực tế đến thư mục dữ liệu của bạn.
## Bước 2: Đọc dự án từ Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Đảm bảo thay thế`"PrimaveraProject.xml"` bằng tên thật của tệp XML Primavera của bạn.
## Bước 3: Lặp lại các tác vụ và truy xuất các thuộc tính cụ thể của Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Mã này lặp qua từng tác vụ trong dự án, in các thuộc tính cụ thể của Primavera có liên quan.

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách đọc các tệp MS Project từ Primavera XML bằng cách sử dụng Aspose.Tasks cho Java. Chức năng này cho phép tích hợp và phân tích liền mạch dữ liệu dự án trên các nền tảng khác nhau, nâng cao hiệu quả quản lý dự án tổng thể.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể sửa đổi các thuộc tính của tác vụ dành riêng cho Primavera bằng Aspose.Tasks cho Java không?
Trả lời: Có, Aspose.Tasks cho Java cung cấp các API để sửa đổi các thuộc tính của nhiệm vụ dành riêng cho Primavera khi cần.
### Câu hỏi: Aspose.Tasks cho Java có hỗ trợ đọc các định dạng tệp dự án khác không?
Trả lời: Có, Aspose.Tasks for Java hỗ trợ đọc các định dạng tệp dự án khác nhau bao gồm MPP, XML và Primavera XML.
### Câu hỏi: Aspose.Tasks dành cho Java có phù hợp với các ứng dụng quản lý dự án cấp doanh nghiệp không?
Trả lời: Hoàn toàn có thể, Aspose.Tasks cho Java cung cấp các tính năng mạnh mẽ và khả năng mở rộng, khiến nó phù hợp với các ứng dụng quản lý dự án cấp doanh nghiệp.
### Câu hỏi: Tôi có thể trích xuất thông tin tài nguyên từ các dự án Primavera bằng Aspose.Tasks cho Java không?
Trả lời: Có, Aspose.Tasks cho Java cho phép bạn trích xuất thông tin tài nguyên cùng với chi tiết nhiệm vụ từ các dự án Primavera.
### Câu hỏi: Tôi có thể tìm tài liệu hoặc hỗ trợ bổ sung cho Aspose.Tasks cho Java ở đâu?
 Đáp: Bạn có thể tìm thấy tài liệu toàn diện và truy cập vào các diễn đàn để được hỗ trợ về[Aspose.Tasks cho tài liệu Java](https://reference.aspose.com/tasks/java/) trang.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
