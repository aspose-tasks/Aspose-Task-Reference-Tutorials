---
date: 2025-12-23
description: Tìm hiểu cách cập nhật các tệp MS Project và lên lịch lại công việc chưa
  hoàn thành bằng Aspose.Tasks cho Java. Ngoài ra, xem cách lưu tệp XML của MS Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cập nhật MS Project và lên lịch lại công việc với Aspose.Tasks
url: /vi/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cập nhật MS Project và Lên lịch lại công việc với Aspose.Tasks

## Giới thiệu
Microsoft Project là một công cụ quản lý dự án được sử dụng rộng rãi giúp các nhóm lập kế hoạch, theo dõi và giao công việc đúng thời hạn. Khi lịch trình thay đổi, bạn thường cần **cập nhật MS Project** file một cách lập trình—đánh dấu công việc đã hoàn thành, di chuyển các nhiệm vụ còn lại, và giữ cho baseline dự án chính xác. Aspose.Tasks for Java cung cấp API sạch, an toàn kiểu để thực hiện điều này mà không cần mở giao diện GUI. Trong tutorial này bạn sẽ thấy cách cập nhật dự án, đánh dấu công việc đã hoàn thành đến một ngày cụ thể, và sau đó **cách lên lịch lại MS Project** công việc còn tồn tại.

## Câu trả lời nhanh
- **Cập nhật MS Project** có nghĩa là gì? Nó đánh dấu các nhiệm vụ là đã hoàn thành đến một ngày cho trước và ghi lại các thay đổi vào file.  
- **Tôi có thể tự động lên lịch lại công việc còn lại không?** Có — sử dụng `rescheduleUncompletedWorkToStartAfter` để đẩy các nhiệm vụ chưa hoàn thành lên phía trước.  
- **Định dạng file nào được lưu?** Các ví dụ lưu dự án dưới dạng XML (`SaveFileFormat.Xml`).  
- **Tôi có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Yêu cầu phiên bản Java nào?** JDK 8 trở lên.

## “update MS Project” là gì trong mã?
Cập nhật một dự án có nghĩa là thay đổi các ngày, thời lượng hoặc tỷ lệ hoàn thành của nhiệm vụ một cách lập trình và lưu lại các thay đổi đó. Aspose.Tasks cung cấp các phương thức như `updateProjectWorkAsComplete` để áp dụng các thay đổi dựa trên một `Date` tham chiếu mà bạn cung cấp.

## Tại sao sử dụng Aspose.Tasks for Java để cập nhật MS Project?
- **Không phụ thuộc giao diện UI** – tự động hoá các thay đổi hàng loạt trên nhiều file.  
- **Độ trung thực cao** – thư viện giữ nguyên tất cả dữ liệu gốc của Project (nguồn lực, lịch, trường tùy chỉnh).  
- **Đa nền tảng** – chạy cùng một mã trên Windows, Linux hoặc macOS.  
- **Lưu XML MS Project** – bạn có thể xuất dự án đã cập nhật sang định dạng XML được hỗ trợ rộng rãi cho các công cụ downstream.

## Yêu cầu trước
1. Java Development Kit (JDK) đã được cài đặt.  
2. Thư viện Aspose.Tasks for Java – tải về từ [here](https://releases.aspose.com/tasks/java/).  
3. Kiến thức cơ bản về cú pháp Java và các khái niệm hướng đối tượng.

## Nhập các gói
Đầu tiên, nhập các lớp Aspose.Tasks cần thiết và các tiện ích Java:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Bước 1: Thiết lập Dự án
Tạo một thể hiện `Project` mới, định nghĩa một vài nhiệm vụ mẫu, đặt thời lượng cho chúng và thiết lập các phụ thuộc. Sau đó lưu trạng thái ban đầu để bạn có thể thấy hiệu ứng trước‑và‑sau.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Bước 2: Cập nhật công việc dự án
Đánh dấu công việc là đã hoàn thành đến một ngày cắt cụ thể. Đây là phần cốt lõi của **cập nhật MS Project** — API sẽ tự động điều chỉnh tiến độ và ngày của các nhiệm vụ.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Bước 3: Lên lịch lại công việc chưa hoàn thành
Sau khi đánh dấu công việc đã hoàn thành, bạn thường cần đẩy các nhiệm vụ còn lại lên phía trước. Lệnh sau di chuyển bất kỳ công việc chưa hoàn thành nào để bắt đầu sau cùng ngày cắt, thực chất là **cách lên lịch lại MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| Các nhiệm vụ không hiển thị ngày cập nhật | Dự án đã được lưu ở định dạng khác (ví dụ: `.mpp`) | Sử dụng `SaveFileFormat.Xml` để giữ cấu trúc XML nguyên vẹn. |
| `updateProjectWorkAsComplete` dường như không thực hiện gì | Ngày tham chiếu sớm hơn ngày bắt đầu dự án | Đảm bảo ngày `Calendar` nằm trong thời gian dự án. |
| Các nhiệm vụ đã lên lịch lại bị chồng lên nhau | Không áp dụng lịch hoặc cân bằng tài nguyên | Áp dụng lịch `Project` hoặc sử dụng `Task.setStart` thủ công sau khi lên lịch lại. |

## Câu hỏi thường gặp (Mở rộng)

**Q: Aspose.Tasks for Java có thể xử lý cấu trúc dự án phức tạp không?**  
A: Có, Aspose.Tasks for Java cung cấp các API mạnh mẽ để quản lý nhiệm vụ, phụ thuộc, nguồn lực và các yếu tố dự án khác một cách hiệu quả.

**Q: Có phiên bản dùng thử cho Aspose.Tasks for Java không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

**Q: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Tasks for Java?**  
A: Bạn có thể truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để được trợ giúp hoặc đặt câu hỏi.

**Q: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks for Java không?**  
A: Có, giấy phép tạm thời có sẵn để mua [here](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks for Java ở đâu?**  
A: Bạn có thể tham khảo tài liệu [here](https://reference.aspose.com/tasks/java/) để có hướng dẫn toàn diện và tham chiếu API.

## Kết luận
Trong tutorial này chúng ta đã đi qua quy trình **cập nhật MS Project** file, đánh dấu công việc đã hoàn thành, và sau đó **cách lên lịch lại MS Project** các nhiệm vụ còn chưa hoàn thành. Bằng cách lưu dự án dưới dạng XML, bạn duy trì khả năng tương thích với các công cụ khác và giữ một dấu vết audit rõ ràng của các thay đổi. Hãy sử dụng các mẫu này để tự động hoá việc điều chỉnh lịch trình trong các danh mục lớn, tích hợp với pipeline CI, hoặc xây dựng bảng điều khiển báo cáo tùy chỉnh.

---

**Cập nhật lần cuối:** 2025-12-23  
**Được kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}