---
date: 2026-04-24
description: Tìm hiểu cách sử dụng Aspose.Tasks Java để nhập file XML Primavera vào
  MS Project, giúp trao đổi dữ liệu liền mạch và cải thiện quản lý dự án.
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Đọc dự án từ Primavera trong Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Đọc XML Primavera vào MS Project
url: /vi/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc MS Project từ Primavera bằng Aspose.Tasks cho Java

## Giới thiệu
Trong thế giới quản lý dự án nhanh chóng ngày nay, bạn thường cần chuyển lịch trình giữa Primavera P6 và Microsoft Project mà không mất bất kỳ chi tiết nào. Hướng dẫn này cho thấy **cách đọc Primavera XML** và nhập chúng vào MS Project bằng **aspose tasks java**. Khi kết thúc hướng dẫn, bạn sẽ có thể lấy các thuộc tính nhiệm vụ đặc thù của Primavera vào một ứng dụng Java, cung cấp cho bạn nguồn dữ liệu duy nhất cho việc phân tích, báo cáo hoặc tự động hoá thêm.

## Câu trả lời nhanh
- **Aspose.Tasks cho Java làm gì?** Nó đọc và ghi nhiều định dạng tệp dự án, bao gồm Primavera XML và Microsoft Project (MPP).  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép là bắt buộc cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Cần Java 8 hoặc cao hơn.  
- **Tôi có thể nhập các định dạng khác ngoài Primavera XML không?** Có, aspose tasks java cũng hỗ trợ MPP, XML và nhiều định dạng khác.  
- **Phương pháp này có phù hợp cho các dự án doanh nghiệp lớn không?** Chắc chắn—Aspose.Tasks được thiết kế cho các kịch bản hiệu suất cao, cấp doanh nghiệp.

## aspose tasks java – Đọc Primavera XML
Đọc Primavera XML có nghĩa là phân tích xuất XML từ Oracle Primavera P6 để lấy dữ liệu lịch trình dự án—các nhiệm vụ, thời lượng, nguồn lực và các thuộc tính đặc thù của Primavera—để có thể được các công cụ khác như Microsoft Project sử dụng.

## Tại sao nên sử dụng Aspose.Tasks cho Java để đọc Primavera XML?
- **Độ chính xác đầy đủ:** Tất cả các thuộc tính đặc thù của Primavera được giữ nguyên.  
- **Không phụ thuộc bên ngoài:** Thư viện Java thuần, không cần cài đặt Primavera hay MS Project.  
- **Mở rộng:** Xử lý các dự án lớn với hàng ngàn nhiệm vụ một cách hiệu quả.  
- **Đa nền tảng:** Hoạt động trên Windows, Linux và macOS.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có những thứ sau:
1. **Java Development Kit (JDK)** – Đã cài đặt Java 8 hoặc mới hơn.  
2. **Aspose.Tasks cho Java** – Tải xuống từ [here](https://releases.aspose.com/tasks/java/).  
3. Một tệp Primavera XML (ví dụ, `PrimaveraProject.xml`) mà bạn muốn đọc.

## Cách đọc tệp dự án java với Aspose.Tasks?
Dưới đây là hướng dẫn từng bước giúp bạn thực hiện toàn bộ quy trình.

### Nhập gói
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Bước 1: Thiết lập Thư mục Dữ liệu
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối nơi tệp Primavera XML của bạn nằm.
```java
String dataDir = "Your Data Directory";
```

### Bước 2: Đọc Dự án từ Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
Cập nhật `"PrimaveraProject.xml"` với tên tệp thực tế của bản xuất Primavera của bạn.

### Bước 3: Duyệt qua các Nhiệm vụ và Lấy Thuộc tính Đặc thù của Primavera
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
Vòng lặp này in ra chi tiết đặc thù của Primavera cho mỗi nhiệm vụ, chẳng hạn như ID Hoạt động, chuỗi WBS, loại thời lượng, phân tích chi phí, và nhiều hơn nữa.

## Các vấn đề thường gặp và giải pháp
- **Lỗi tệp không tìm thấy:** Kiểm tra rằng `dataDir` kết thúc bằng dấu phân tách đường dẫn (`/` hoặc `\\`) và tên tệp XML là chính xác.  
- **Thiếu thuộc tính Primavera:** Đảm bảo XML được xuất với tất cả các trường bắt buộc; các phiên bản Primavera cũ hơn có thể bỏ qua một số thuộc tính.  
- **Hiệu năng trên tệp lớn:** Xem xét tăng kích thước heap của JVM (`-Xmx2g` hoặc cao hơn) cho các dự án có hàng chục ngàn nhiệm vụ.

## Câu hỏi thường gặp
### H: Tôi có thể sửa đổi các thuộc tính đặc thù của Primavera cho nhiệm vụ bằng Aspose.Tasks cho Java không?
Đ: Có, Aspose.Tasks cho Java cung cấp các API để sửa đổi các thuộc tính đặc thù của Primavera cho nhiệm vụ khi cần.

### H: Aspose.Tasks cho Java có hỗ trợ đọc các định dạng tệp dự án khác không?
Đ: Có, Aspose.Tasks cho Java hỗ trợ đọc nhiều định dạng tệp dự án bao gồm MPP, XML và Primavera XML.

### H: Aspose.Tasks cho Java có phù hợp cho các ứng dụng quản lý dự án cấp doanh nghiệp không?
Đ: Chắc chắn, Aspose.Tasks cho Java cung cấp các tính năng mạnh mẽ và khả năng mở rộng, làm cho nó phù hợp cho các ứng dụng quản lý dự án cấp doanh nghiệp.

### H: Tôi có thể trích xuất thông tin nguồn lực từ dự án Primavera bằng Aspose.Tasks cho Java không?
Đ: Có, Aspose.Tasks cho Java cho phép bạn trích xuất thông tin nguồn lực cùng với chi tiết nhiệm vụ từ các dự án Primavera.

### H: Tôi có thể tìm hỗ trợ hoặc tài liệu bổ sung cho Aspose.Tasks cho Java ở đâu?
Đ: Bạn có thể tìm tài liệu đầy đủ và truy cập diễn đàn hỗ trợ trên trang [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/).

## Kết luận
Bạn đã học được **cách đọc primavera xml** và lấy thông tin chi tiết của nhiệm vụ vào một ứng dụng Java bằng **aspose tasks java**. Khả năng này nối liền khoảng cách giữa Primavera và Microsoft Project, cung cấp cho bạn khả năng quan sát toàn diện trên các nền tảng và tăng hiệu quả quản lý dự án tổng thể.

---

**Cập nhật lần cuối:** 2026-04-24  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}