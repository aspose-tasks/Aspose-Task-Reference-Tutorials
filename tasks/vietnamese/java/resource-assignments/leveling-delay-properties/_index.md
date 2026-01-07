---
date: 2026-01-07
description: Tìm hiểu cách thêm nguồn lực vào dự án và xử lý các thuộc tính độ trễ
  cân bằng cho các phân công nguồn lực bằng Aspose.Tasks cho Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Thêm Tài Nguyên Vào Dự Án và Xử Lý Thuộc Tính Độ Trễ Cân Bằng Trong Aspose.Tasks
url: /vi/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Tài Nguyên Vào Dự Án và Xử Lý Thuộc Tính Độ Trễ Cân Bằng trong Aspose.Tasks

## Introduction
Trong hướng dẫn này, bạn sẽ học **cách thêm tài nguyên vào dự án** đồng thời quản lý các thuộc tính độ trễ cân bằng cho các phân công tài nguyên bằng Aspose.Tasks cho Java. Dù bạn đang xây dựng một công cụ lập lịch hay tự động cập nhật dự án, việc nắm vững các bước này giúp bạn giữ dữ liệu dự án chính xác mà không cần cài đặt Microsoft Project.

## Quick Answers
- **“add resource to project” có nghĩa là gì?** Nó tạo một mục tài nguyên mới có thể được gán cho các công việc.  
- **Tôi có thể đặt độ trễ cân bằng sau khi gán không?** Có, bằng cách sử dụng các trường `Asn.DELAY` hoặc `Asn.LEVELING_DELAY`.  
- **Tôi có cần giấy phép để chạy đoạn mã này không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép trả phí cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc mới hơn.  
- **Điều này có tương thích với tất cả các định dạng tệp MS Project không?** Aspose.Tasks hỗ trợ .MPP, .XML, .XER và nhiều định dạng khác.

## What is “add resource to project” in Aspose.Tasks?
Thêm tài nguyên vào dự án có nghĩa là tạo một đối tượng `Resource` bên trong mô hình `Project`. Đối tượng này sau đó có thể được liên kết với các công việc thông qua `ResourceAssignment`, cho phép bạn theo dõi công việc, chi phí và cài đặt cân bằng.

## Why handle leveling delay properties?
Độ trễ cân bằng giúp bộ lập lịch phân bố công việc khi tài nguyên bị quá tải. Bằng cách đặt độ trễ, bạn yêu cầu công cụ hoãn thời gian bắt đầu của một phân công, tránh xung đột và giữ cho dự án thực tế hơn.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã chuẩn bị các điều kiện sau:
1. **Java Development Kit (JDK):** Đảm bảo rằng bạn đã cài đặt Java JDK trên hệ thống. Bạn có thể tải và cài đặt từ [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. **Thư viện Aspose.Tasks cho Java:** Tải thư viện Aspose.Tasks cho Java từ [download page](https://releases.aspose.com/tasks/java/).

## Import Packages
Đầu tiên, nhập các gói cần thiết vào dự án Java của bạn để sử dụng các chức năng của Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Create a Project Object
Khởi tạo một đối tượng `Project`, đối tượng này sẽ là container cho tất cả các công việc, tài nguyên và phân công:
```java
Project prj = new Project();
```

## Step 2: Create a Task
Thêm một công việc vào dự án. Điều này minh họa **cách thêm công việc** một cách lập trình:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Step 3: Set Task Start Date and Duration
Xác định ngày bắt đầu và thời lượng của công việc:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Step 4: Add a Resource
Bây giờ chúng ta **add resource to project** bằng cách tạo một mục `Resource` mới:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Step 5: Create a Resource Assignment
Liên kết công việc và tài nguyên vừa thêm lại với nhau:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Step 6: Set Leveling Delay
Cấu hình độ trễ cân bằng cho phân công. Đặt giá trị bằng 0 có nghĩa là không có độ trễ bổ sung, nhưng bạn có thể điều chỉnh giá trị tùy nhu cầu:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Step 7: Display Results
In ra các thuộc tính quan trọng để xác nhận mọi thứ đã được thiết lập đúng:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Common Pitfalls & Tips
- **Pitfall:** Quên đặt ngày bắt đầu của công việc có thể khiến phân công mặc định bắt đầu từ ngày đầu dự án.  
- **Tip:** Sử dụng `prj.getDuration(value, TimeUnitType.Day)` để kiểm soát độ chi tiết của độ trễ.  
- **Tip:** Sau khi thêm nhiều tài nguyên, gọi `prj.updateResourceAssignments()` để cho bộ lập lịch tính lại cân bằng.

## Conclusion
Bằng cách thực hiện các bước trên, bạn đã biết **cách thêm tài nguyên vào dự án**, gán nó cho một công việc và quản lý các thuộc tính độ trễ cân bằng bằng Aspose.Tasks cho Java. Kiến thức này cho phép bạn xây dựng các giải pháp tự động hoá dự án mạnh mẽ, đồng bộ với các hạn chế thực tế của tài nguyên.

## FAQ's
### Q: Tôi có thể sử dụng Aspose.Tasks cùng với các thư viện Java khác không?

A: Có, Aspose.Tasks có thể được tích hợp với các thư viện Java khác để nâng cao khả năng quản lý dự án.

### Q: Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?

A: Có, Aspose.Tasks hỗ trợ nhiều phiên bản tệp Microsoft Project, đảm bảo tính tương thích trên các môi trường khác nhau.

### Q: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Tasks ở đâu?

A: Bạn có thể tìm hỗ trợ và tài nguyên trên [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?

A: Có, bạn có thể lấy bản dùng thử miễn phí của Aspose.Tasks từ [releases page](https://releases.aspose.com/).

### Q: Làm thế nào để tôi nhận được giấy phép tạm thời cho Aspose.Tasks?

A: Bạn có thể yêu cầu giấy phép tạm thời từ [temporary license page](https://purchase.aspose.com/temporary-license/) để đánh giá.

## Additional Frequently Asked Questions

**Q: Điều gì sẽ xảy ra nếu tôi đặt độ trễ cân bằng khác 0?**  
A: Bộ lập lịch sẽ hoãn thời gian bắt đầu của phân công theo khoảng thời gian đã chỉ định, giúp giải quyết tình trạng quá tải.

**Q: Tôi có thể lấy lại độ trễ cân bằng sau khi lưu dự án không?**  
A: Có, bạn có thể mở lại tệp dự án và đọc thuộc tính `Asn.DELAY` từ phân công.

**Q: Có cách nào để áp dụng độ trễ cân bằng cho tất cả các phân công cùng một lúc không?**  
A: Bạn có thể duyệt qua `prj.getResourceAssignments()` và đặt độ trễ cho mỗi phân công trong một vòng lặp.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}