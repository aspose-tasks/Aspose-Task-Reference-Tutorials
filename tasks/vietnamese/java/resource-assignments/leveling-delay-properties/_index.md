---
date: 2026-06-05
description: Tìm hiểu cách tạo phân công nguồn lực với Aspose.Tasks cho Java, thêm
  nguồn lực vào dự án và quản lý các thuộc tính độ trễ cân bằng.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Xử lý các thuộc tính độ trễ cân bằng cho phân công nguồn lực trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Tạo Phân công Nguồn lực với Aspose.Tasks cho Java
url: /vi/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Phân công Nguồn lực với Aspose.Tasks cho Java

Trong hướng dẫn toàn diện này, bạn sẽ học **how to create resource assignment aspotasks** bằng cách sử dụng thư viện Aspose.Tasks cho Java. Cho dù bạn đang xây dựng một công cụ lập lịch tùy chỉnh, tự động hoá việc cập nhật dự án hàng loạt, hoặc chỉ đơn giản cần thao tác các tệp Microsoft Project mà không cần ứng dụng desktop, việc nắm vững các bước này sẽ giúp bạn giữ dữ liệu dự án chính xác và hoàn toàn kiểm soát được.

## Câu trả lời nhanh
- **What does “add resource to project” mean?** Nó tạo một mục nguồn lực mới có thể được gán cho các nhiệm vụ sau này.  
- **Can I set a leveling delay after assignment?** Có, bằng cách sử dụng các trường `Asn.DELAY` hoặc `Asn.LEVELING_DELAY`.  
- **Do I need a license to run this code?** Bản dùng thử miễn phí hoạt động cho phát triển; cần giấy phép trả phí cho môi trường sản xuất.  
- **Which Java version is supported?** Java 8 hoặc mới hơn.  
- **Is this compatible with all MS Project file formats?** Aspose.Tasks hỗ trợ hơn 12 định dạng—bao gồm .MPP, .XML, .XER, .CSV, .PDF và nhiều hơn nữa.

## “add resource to project” là gì trong Aspose.Tasks?
Thêm một nguồn lực vào dự án có nghĩa là tạo một đối tượng `Resource` bên trong mô hình `Project`. Đối tượng này sau đó có thể được liên kết với các nhiệm vụ thông qua `ResourceAssignment`, cho phép bạn theo dõi công việc, chi phí và cài đặt cân bằng. Bằng cách chèn một nguồn lực, bạn cung cấp cho bộ lập lịch một đối tượng để phân bổ, và bạn có thể sau này truy vấn hoặc sửa đổi các thuộc tính của nó như khả dụng, mức giá và lịch làm việc.

## Tại sao cần xử lý các thuộc tính độ trễ cân bằng?
Độ trễ cân bằng yêu cầu bộ lập lịch hoãn lại thời gian bắt đầu của một phân công quá tải, phân phối công việc đồng đều hơn trên toàn biểu đồ thời gian. Bằng cách cấu hình độ trễ này, bạn tránh được các ngày bắt đầu không thực tế, giảm cảnh báo quá tải và tạo ra một lịch trình phản ánh các hạn chế thực tế của nguồn lực. Điều chỉnh độ trễ cũng cho phép bạn kiểm soát chi tiết mức độ chênh lệch mà công cụ có thể chèn, giúp bạn đáp ứng thời hạn dự án trong khi tôn trọng giới hạn nguồn lực.

## Cách tạo resource assignment aspotasks?
Tải đối tượng `Project` của bạn, thêm một nhiệm vụ, tạo một nguồn lực, và sau đó liên kết chúng với một `ResourceAssignment`. Quy trình đầu‑cuối này cho phép bạn xây dựng một cấu trúc dự án đầy đủ một cách lập trình và ngay lập tức kiểm soát độ trễ cân bằng trên phân công. Quy trình này minh họa quy trình làm việc cốt lõi: khởi tạo dự án, định nghĩa nhiệm vụ, tạo nguồn lực, liên kết phân công, và cuối cùng áp dụng các tham số lập lịch như độ trễ cân bằng.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:
1. Java Development Kit (JDK): Đảm bảo rằng bạn đã cài đặt Java JDK trên hệ thống của mình. Bạn có thể tải xuống và cài đặt từ [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Thư viện Aspose.Tasks cho Java: Tải thư viện Aspose.Tasks cho Java từ [download page](https://releases.aspose.com/tasks/java/).

## Nhập khẩu các gói
Các import sau đây mang lại các lớp cốt lõi của Aspose.Tasks cần thiết cho việc thao tác dự án.  
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

## Cách tạo resource assignment aspotasks?
Tải đối tượng `Project` của bạn, thêm một nhiệm vụ, tạo một nguồn lực, và sau đó liên kết chúng với một `ResourceAssignment`. Quy trình đầu‑cuối này cho phép bạn xây dựng một cấu trúc dự án đầy đủ một cách lập trình và ngay lập tức kiểm soát độ trễ cân bằng trên phân công. Quy trình này minh họa quy trình làm việc cốt lõi: khởi tạo dự án, định nghĩa nhiệm vụ, tạo nguồn lực, liên kết phân công, và cuối cùng áp dụng các tham số lập lịch như độ trễ cân bằng.

## Bước 1: Tạo đối tượng Project
Lớp `Project` là container cấp cao nhất của Aspose.Tasks, đại diện cho toàn bộ tệp dự án trong bộ nhớ. Khi khởi tạo nó, bạn có một nền tảng trống để thêm các nhiệm vụ, nguồn lực và phân công.
```java
Project prj = new Project();
```

## Bước 2: Tạo một Task
Lớp `Task` đại diện cho một mục công việc duy nhất trong lịch trình. Thêm một task minh họa **how to add task** một cách lập trình và cung cấp mục tiêu cho việc phân công nguồn lực sắp tới.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Bước 3: Đặt ngày bắt đầu và thời lượng cho Task
Xác định thời điểm task bắt đầu và thời gian thực hiện. Ngày bắt đầu chính xác là cần thiết vì các phép tính cân bằng sử dụng chúng làm cơ sở cho bất kỳ độ trễ nào bạn chỉ định sau này.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Bước 4: Thêm một Resource
Bây giờ chúng ta **add resource to project** bằng cách tạo một mục `Resource` mới. Lớp `Resource` là đại diện cho một người, thiết bị hoặc vật liệu có thể được gán cho các task.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Bước 5: Tạo một Resource Assignment
`ResourceAssignment` liên kết một `Task` và một `Resource`. Sự liên kết này cho phép bạn ghi lại công việc, chi phí và chi tiết cân bằng cho một nguồn lực cụ thể trên một task cụ thể.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Bước 6: Đặt Leveling Delay
Cấu hình độ trễ cân bằng cho phân công. Đặt giá trị bằng không có nghĩa là không có độ trễ bổ sung, nhưng bạn có thể điều chỉnh giá trị tùy nhu cầu. Trường `Asn.DELAY` chứa độ trễ tính bằng phút; `Asn.LEVELING_DELAY` là một bí danh hoạt động tương tự.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Bước 7: Hiển thị Kết quả
In các thuộc tính quan trọng để xác minh rằng mọi thứ đã được thiết lập đúng. Bước này giúp bạn xác nhận rằng các giá trị nguồn lực, task và độ trễ là chính xác như mong đợi trước khi lưu tệp.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Những Cạm Bẫy Thường Gặp & Mẹo
- **Pitfall:** Quên đặt ngày bắt đầu của task có thể khiến phân công mặc định vào ngày bắt đầu dự án.  
- **Tip:** Sử dụng `prj.getDuration(value, TimeUnitType.Day)` để kiểm soát độ chi tiết của độ trễ.  
- **Tip:** Sau khi thêm nhiều nguồn lực, gọi `prj.updateResourceAssignments()` để cho bộ lập lịch tính lại cân bằng.  
- **Pro tip:** Đối với các dự án lớn (hơn 10.000 task) bật `prj.setAutoCalculate(false)` trước khi cập nhật hàng loạt, sau đó gọi `prj.calculate()` một lần ở cuối để cải thiện hiệu năng.

## Câu Hỏi Thường Gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các thư viện Java khác không?**  
A: Có, Aspose.Tasks tích hợp mượt mà với các thư viện như Jackson để xử lý JSON hoặc Apache POI cho các thao tác bảng tính bổ sung, cho phép bạn xây dựng các giải pháp quản lý dự án phong phú hơn.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp Microsoft Project khác nhau không?**  
A: Aspose.Tasks hỗ trợ hơn 12 định dạng tệp—bao gồm .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML và .MPP12—đảm bảo việc chỉnh sửa vòng tròn liền mạch trên mọi phiên bản Project chính.

**Q: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Tasks ở đâu?**  
A: Bạn có thể tìm hỗ trợ và thảo luận cộng đồng trên [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
A: Có, bản dùng thử đầy đủ chức năng có sẵn từ [releases page](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời để đánh giá?**  
A: Yêu cầu giấy phép tạm thời từ [temporary license page](https://purchase.aspose.com/temporary-license/) để chạy thư viện mà không bị hạn chế đánh giá.

---

**Cập nhật lần cuối:** 2026-06-05  
**Kiểm thử với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose

## Hướng Dẫn Liên Quan

- [Tạo Phân công Nguồn lực trong Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Quản lý Ngân sách Phân công Java bằng Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Cách Dừng Phân công và Tiếp tục Phân công Nguồn lực trong Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}