---
date: 2026-02-20
description: Tìm hiểu cách đặt ngày bắt đầu dự án và quản lý các biến thể dự án bằng
  Aspose.Tasks cho Java. Hướng dẫn này cũng chỉ cách đặt thời lượng công việc một
  cách hiệu quả.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Đặt ngày bắt đầu dự án & xử lý các độ lệch công việc Aspose.Tasks
url: /vi/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt ngày bắt đầu dự án & xử lý biến thể công việc Aspose.Tasks

## Giới thiệu
Trong lĩnh vực quản lý dự án, **đặt ngày bắt đầu dự án** là một trong những hành động đầu tiên bạn thực hiện để tạo nền tảng vững chắc cho lịch trình. Aspose.Tasks for Java làm cho bước này—và việc xử lý các biến thể công việc sau đó—trở nên đơn giản và đáng tin cậy. Trong hướng dẫn này, bạn sẽ học cách đặt ngày bắt đầu dự án, đặt thời lượng công việc, và quản lý các biến thể dự án một cách hiệu quả.

## Câu trả lời nhanh
- **Phương pháp chính để đặt ngày bắt đầu dự án là gì?** Sử dụng `project.set(Prj.START_DATE, …)` với một đối tượng `java.util.Calendar`.  
- **Lớp nào đại diện cho baseline để theo dõi biến thể?** `BaselineType.Baseline`.  
- **Tôi có thể điều chỉnh ngày bắt đầu và kết thúc công việc sau khi đã thiết lập baseline không?** Có, chỉ cần cập nhật `Tsk.START` và `Tsk.STOP`.  
- **Tôi có cần giấy phép cho việc phát triển không?** Một giấy phép tạm thời có sẵn để đánh giá.  
- **Phiên bản Aspose.Tasks nào hoạt động với đoạn mã này?** Phiên bản mới nhất của Aspose.Tasks for Java.

## **set project start date** là gì?
Đặt ngày bắt đầu dự án xác định ngày lịch mà từ đó tất cả các ngày công việc được tính toán. Nó ảnh hưởng đến các phép tính lịch trình, phân tích đường găng, và tạo baseline, do đó rất quan trọng cho việc quản lý biến thể chính xác.

## Tại sao cần đặt ngày bắt đầu dự án và quản lý biến thể?
- **Dự đoán được:** Thiết lập một baseline rõ ràng để so sánh tiến độ thực tế.  
- **Linh hoạt:** Cho phép bạn điều chỉnh ngày công việc riêng lẻ mà không làm mất kế hoạch gốc.  
- **Báo cáo:** Cung cấp các báo cáo biến thể rõ ràng, nêu bật việc trễ lịch hoặc hoàn thành sớm.  

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Môi trường phát triển Java – một JDK đã được cài đặt và IDE hoặc công cụ xây dựng sẵn sàng.  
- Thư viện Aspose.Tasks – tải thư viện **[tại đây](https://releases.aspose.com/tasks/java/)**.  

## Nhập khẩu các gói
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Bước 1: Thiết lập dự án
Tạo một thể hiện `Project` mới sẽ chứa tất cả các công việc và thông tin lịch trình.

```java
Project project = new Project();
```

## Bước 2: Thêm công việc
Thêm một công việc dưới task gốc. Đây sẽ là mục công việc mà chúng ta sẽ điều chỉnh sau này.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Bước 3: Đặt ngày bắt đầu và thời lượng
Xác định ngày bắt đầu của dự án và đặt thời lượng cho công việc. Điều này minh họa **set task duration** trong thực tế.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Bước 4: Thiết lập Baseline
Tạo một baseline để bạn có thể so sánh ngày kế hoạch với ngày thực tế—cần thiết cho **manage project variances**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Bước 5: Điều chỉnh ngày bắt đầu và kết thúc công việc
Sửa đổi ngày bắt đầu và kết thúc của công việc để mô phỏng một kịch bản biến thể.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Bạn có thể tự do điều chỉnh ngày và thời lượng để phù hợp với nhu cầu cụ thể của dự án.*

## Các vấn đề thường gặp & Mẹo
- **Baseline phải được thiết lập trước khi điều chỉnh ngày.** Nếu bạn thay đổi ngày trước, baseline sẽ ghi lại lịch trình đã thay đổi thay vì kế hoạch gốc.  
- **Các tháng trong Calendar bắt đầu từ 0.** Hãy nhớ rằng `Calendar.FEBRUARY` tương đương tháng 1, không phải 2.  
- **Đơn vị thời lượng:** `project.getDuration(2)` tạo một thời lượng hai ngày theo mặc định; hãy điều chỉnh đơn vị nếu bạn cần giờ hoặc tuần.

## Kết luận
Bằng cách nắm vững cách **đặt ngày bắt đầu dự án**, **đặt thời lượng công việc**, và **quản lý biến thể dự án**, bạn sẽ có toàn quyền kiểm soát lịch trình dự án của mình bằng Aspose.Tasks for Java. Các bước trên cung cấp nền tảng vững chắc mà bạn có thể mở rộng cho các kịch bản phức tạp hơn như dự án đa giai đoạn, phân bổ nguồn lực, và báo cáo tự động.

## Câu hỏi thường gặp
### Aspose.Tasks có phù hợp với mọi nhu cầu quản lý dự án không?
Aspose.Tasks là một công cụ đa năng, phù hợp với nhiều yêu cầu quản lý dự án, cung cấp tính linh hoạt và các tính năng mạnh mẽ.

### Tôi có thể tích hợp Aspose.Tasks vào dự án Java hiện có của mình không?
Có, bạn có thể dễ dàng tích hợp Aspose.Tasks vào dự án Java của mình bằng cách làm theo tài liệu được cung cấp **[tại đây](https://reference.aspose.com/tasks/java/)**.

### Có giấy phép tạm thời cho Aspose.Tasks không?
Có, bạn có thể nhận giấy phép tạm thời cho Aspose.Tasks **[tại đây](https://purchase.aspose.com/temporary-license/)**.

### Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?
Để được hỗ trợ và thảo luận, hãy truy cập diễn đàn Aspose.Tasks **[tại đây](https://forum.aspose.com/c/tasks/15)**.

### Tôi có thể tải Aspose.Tasks cho Java không?
Có, tải phiên bản mới nhất của Aspose.Tasks cho Java **[tại đây](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks latest Java release  
**Author:** Aspose