---
date: 2026-03-29
description: Tìm hiểu cách lên lịch lại công việc chưa hoàn thành, cập nhật công việc
  dự án và lưu các tệp MS Project dưới dạng XML bằng Aspose.Tasks cho Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lên lịch lại công việc chưa hoàn thành và cập nhật tệp MS Project bằng Aspose.Tasks
url: /vi/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt lại lịch công việc chưa hoàn thành và Cập nhật tệp MS Project với Aspose.Tasks

## Giới thiệu
Microsoft Project là một công cụ quản lý dự án được sử dụng rộng rãi, giúp các nhóm lên kế hoạch nhiệm vụ, phân bổ nguồn lực và theo dõi thời gian. Aspose.Tasks cho Java cung cấp cho nhà phát triển một API phong phú để thao tác các tệp Microsoft Project một cách lập trình. Trong hướng dẫn này, bạn sẽ học cách **cập nhật công việc dự án**, **đặt lại lịch công việc chưa hoàn thành**, và **lưu tệp MS Project** ở định dạng XML bằng Aspose.Tasks cho Java.

## Câu trả lời nhanh
- **“Reschedule uncompleted work” có nghĩa là gì?** Nó di chuyển bất kỳ công việc nhiệm vụ còn lại nào để bắt đầu sau một ngày được chọn, giữ nguyên các phần đã hoàn thành.  
- **Phương thức nào đánh dấu công việc là hoàn thành?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Làm thế nào để lưu các thay đổi?** Sử dụng `project.save(<path>, SaveFileFormat.Xml)`.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Có, cần một giấy phép Aspose.Tasks hợp lệ để sử dụng thương mại.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 và các phiên bản sau đều được hỗ trợ đầy đủ.

## “Reschedule uncompleted work” là gì?
Đặt lại lịch công việc chưa hoàn thành điều chỉnh ngày bắt đầu của tất cả các nhiệm vụ chưa kết thúc, đẩy chúng bắt đầu sau một ngày cắt cụ thể. Điều này hữu ích khi lịch trình dự án thay đổi do trì hoãn hoặc thay đổi phạm vi.

## Tại sao nên sử dụng Aspose.Tasks để cập nhật công việc dự án và đặt lại lịch nhiệm vụ?
- **Kiểm soát chi tiết:** Đặt trực tiếp tỷ lệ hoàn thành công việc và ngày tháng.  
- **Không cần giao diện người dùng:** Tự động hoá cập nhật hàng loạt trên nhiều tệp dự án.  
- **Đa nền tảng:** Hoạt động trên bất kỳ hệ thống nào chạy Java.  
- **Bảo toàn tính toàn vẹn dữ liệu:** Tất cả các phụ thuộc, ràng buộc và nguồn lực vẫn nhất quán.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có những thứ sau:
1. Java Development Kit (JDK) được cài đặt trên hệ thống của bạn.  
2. Thư viện Aspose.Tasks cho Java. Bạn có thể tải xuống từ [here](https://releases.aspose.com/tasks/java/).  
3. Hiểu biết cơ bản về ngôn ngữ lập trình Java.

## Nhập gói
Đầu tiên, nhập các gói cần thiết trong mã Java của bạn:
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

## Bước 1: Thiết lập dự án
Khởi tạo một đối tượng `Project` mới, định nghĩa các nhiệm vụ, đặt thời lượng và thiết lập các phụ thuộc. Điều này tạo ra dự án cơ sở mà chúng ta sẽ cập nhật và đặt lại lịch sau này.
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
Đánh dấu công việc là hoàn thành đến một ngày cụ thể. Bước này trình bày thao tác **cập nhật công việc dự án**, thường là hành động đầu tiên trước khi đặt lại lịch.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Bước 3: Đặt lại lịch công việc chưa hoàn thành
Bây giờ chúng ta di chuyển bất kỳ công việc còn lại (chưa hoàn thành) sao cho chúng bắt đầu sau cùng ngày cắt. Đây là chức năng cốt lõi của **đặt lại lịch công việc chưa hoàn thành**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Kết luận
Trong hướng dẫn này, chúng ta đã đề cập cách **cập nhật công việc dự án**, **đặt lại lịch công việc chưa hoàn thành**, và **lưu tệp MS Project** dưới dạng XML bằng Aspose.Tasks cho Java. Những khả năng này rất cần thiết khi lịch trình dự án cần được điều chỉnh dựa trên tiến độ thực tế hoặc ưu tiên kinh doanh thay đổi.

## Câu hỏi thường gặp
### H: Aspose.Tasks cho Java có thể xử lý cấu trúc dự án phức tạp không?
A: Có, Aspose.Tasks cho Java cung cấp các API mạnh mẽ để quản lý nhiệm vụ, phụ thuộc, nguồn lực và các yếu tố dự án khác một cách hiệu quả.  
### H: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?
A: Có, bạn có thể nhận bản dùng thử miễn phí từ [here](https://releases.aspose.com/).  
### H: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java?
A: Bạn có thể truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để được hỗ trợ hoặc đặt câu hỏi.  
### H: Tôi có thể mua giấy phép tạm thời cho Aspose.Tasks cho Java không?
A: Có, giấy phép tạm thời có thể mua tại [here](https://purchase.aspose.com/temporary-license/).  
### H: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks cho Java ở đâu?
A: Bạn có thể tham khảo tài liệu tại [here](https://reference.aspose.com/tasks/java/) cho các hướng dẫn toàn diện và tham chiếu API.

## Các câu hỏi thường gặp bổ sung

**H: Làm sao tôi đảm bảo tệp đã lưu tương thích với các phiên bản Microsoft Project cũ hơn?**  
A: Lưu dự án bằng `SaveFileFormat.Xml`; XML được hỗ trợ rộng rãi trên các phiên bản Project.

**H: Tôi có thể đặt lại lịch chỉ một phần nhiệm vụ thay vì toàn bộ dự án không?**  
A: Có, bạn có thể lặp qua các nhiệm vụ cụ thể và gọi `task.setStart(date)` sau khi tính toán ngày bắt đầu mới.

**H: Điều gì xảy ra với việc phân bổ nguồn lực khi tôi đặt lại lịch công việc chưa hoàn thành?**  
A: Các phân công nguồn lực sẽ tự động được chuyển để phù hợp với ngày bắt đầu mới của nhiệm vụ, bảo toàn logic phân bổ.

**H: Có thể hoàn tác thao tác đặt lại lịch bằng chương trình không?**  
A: Bạn có thể tải lại tệp dự án gốc (hoặc bản sao lưu) để hoàn tác mọi thay đổi.

**H: Aspose.Tasks có hỗ trợ lưu sang các định dạng khác như .mpp không?**  
A: Chắc chắn. Sử dụng `SaveFileFormat.MPP` để lưu ở định dạng gốc Microsoft Project.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}