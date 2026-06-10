---
date: 2026-06-10
description: Tìm hiểu cách đọc rate và cách ghi rate scale cho resource assignments
  bằng Aspose.Tasks cho Java. Hỗ trợ material resources, multiple formats và large
  projects.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Đọc và Ghi Rate Scale cho Resource Assignments trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách Đọc Rate Scale và Ghi Rate Scale cho Resource Assignments trong Aspose.Tasks
url: /vi/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đọc Tỷ Lệ và Ghi Tỷ Lệ cho Phân Công Tài Nguyên trong Aspose.Tasks

Trong hướng dẫn này, bạn sẽ khám phá **cách đọc tỷ lệ** cài đặt và điều chỉnh chúng cho các phân công tài nguyên bằng Aspose.Tasks cho Java. Cho dù bạn đang xây dựng một bộ lập lịch, một công cụ báo cáo, hoặc chỉ cần tự động hoá cập nhật dự án, việc thành thạo việc thao tác tỷ lệ cho phép bạn kiểm soát chi tiết tài nguyên vật liệu và công việc.

## Câu trả lời nhanh
`ResourceAssignment` liên kết một nhiệm vụ với một tài nguyên và chứa dữ liệu đặc thù của phân công.  
`Asn` chứa các hằng số cho các trường phân công, bao gồm `RATE_SCALE`.  
`RateScaleType` enum liệt kê các đơn vị thời gian khả dụng cho việc tỷ lệ.

- **Lớp chính để xử lý tỷ lệ là gì?** `ResourceAssignment` với thuộc tính `Asn.RATE_SCALE`.  
- **Enum nào định nghĩa các tùy chọn tỷ lệ?** `RateScaleType` (Day, Week, Month, etc.).  
- **Tôi có cần giấy phép để chạy mẫu không?** Giấy phép dùng thử miễn phí hoạt động cho việc kiểm tra; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi tỷ lệ sau khi lưu không?** Có – tải lại dự án và sửa đổi `Asn.RATE_SCALE` như minh họa.  
- **IDE hỗ trợ?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, NetBeans) đều có thể biên dịch mã.

## Cách đọc tỷ lệ cho phân công tài nguyên?
Tải dự án, xác định `ResourceAssignment` mong muốn, và gọi `getRateScale()` – phương thức này trả về một giá trị `RateScaleType` cho biết tỷ lệ được áp dụng theo ngày, tuần, tháng, hoặc đơn vị khác. Kết quả được trả về ngay lập tức và chỉ cần hai lời gọi API, rất thích hợp cho các script kiểm toán hoặc hiển thị giao diện người dùng.

## Cách ghi tỷ lệ cho phân công tài nguyên?
Tạo hoặc lấy một đối tượng `ResourceAssignment`, đặt thuộc tính `Asn.RATE_SCALE` của nó thành `RateScaleType` mong muốn (ví dụ, `RateScaleType.Week`), sau đó lưu dự án. Thay đổi thuộc tính duy nhất này tự động cập nhật các tính toán chi phí và được lưu lại trong mọi định dạng tệp được hỗ trợ. Sau khi đặt tỷ lệ, bạn cũng có thể cần điều chỉnh tỷ lệ chuẩn hoặc tỷ lệ làm thêm giờ của tài nguyên để phản ánh đơn vị thời gian mới, đảm bảo các tính toán chi phí vẫn chính xác.

## Tỷ lệ là gì?
Tỷ lệ xác định đơn vị thời gian (ngày, tuần, tháng, v.v.) mà tỷ lệ chi phí của tài nguyên được áp dụng. Điều chỉnh tỷ lệ cho phép bạn mô hình hoá tiêu thụ vật liệu hoặc nỗ lực lao động một cách chính xác. Ví dụ, đặt tỷ lệ thành Week có nghĩa là tỷ lệ chi phí được hiểu là chi phí mỗi tuần, và tổng chi phí cho một nhiệm vụ được tính dựa trên số tuần mà tài nguyên được phân công.

## Tại sao cần đọc và ghi tỷ lệ?
Đọc tỷ lệ hiện tại giúp bạn kiểm toán các lịch trình hiện có, trong khi ghi một tỷ lệ mới cho phép bạn đồng bộ tài nguyên với chính sách thanh toán hoặc tiêu thụ của dự án. Điều này đặc biệt hữu ích khi **định nghĩa chi phí tài nguyên vật liệu** hoặc khi bạn cần **đặt tỷ lệ** cho các lịch làm việc không chuẩn.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn có các yêu cầu sau:
1. **Môi trường phát triển Java** – JDK 8 trở lên đã được cài đặt.  
2. **Thư viện Aspose.Tasks cho Java** – Tải và cài đặt thư viện từ [đây](https://releases.aspose.com/tasks/java/).

## Nhập các gói
`ResourceAssignment` đại diện cho một liên kết giữa một nhiệm vụ và một tài nguyên, trong khi `RateScaleType` liệt kê các đơn vị thời gian khả dụng cho một tỷ lệ. Nhập các lớp Aspose.Tasks cần thiết trước khi bắt đầu viết mã.  

`Project` là đối tượng chính dùng để tải và lưu các tệp Microsoft Project.  
`Resource` định nghĩa một tài nguyên dự án như công việc hoặc vật liệu.  
`ResourceType` enum chỉ định tài nguyên là công việc hay vật liệu.  
`Task` đại diện cho một mục công việc trong lịch trình dự án.  
`SaveFileFormat` enum xác định định dạng đầu ra khi lưu dự án.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Bước 1: Thiết lập dự án Java của bạn
Tạo một dự án Maven hoặc Gradle và thêm JAR Aspose.Tasks vào classpath. Bước này đảm bảo trình biên dịch có thể tìm thấy các lớp đã nhập.

## Bước 2: Tải tệp dự án
Tải tệp Microsoft Project hiện có mà bạn muốn làm việc.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Bước 3: Thêm một nhiệm vụ
Tạo một nhiệm vụ mới sẽ nhận các phân công tài nguyên sau này.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Bước 4: Định nghĩa tài nguyên
Ở đây chúng tôi **định nghĩa tài nguyên vật liệu** và một tài nguyên công việc thường. Lưu ý việc sử dụng `ResourceType.Material` cho tài nguyên loại vật liệu.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Bước 5: Gán tài nguyên cho nhiệm vụ
Bây giờ chúng tôi **gán tài nguyên cho nhiệm vụ** và chỉ định **cách đặt tỷ lệ** bằng cách sử dụng `RateScaleType.Week`. Điều này minh họa cả việc đọc và ghi tỷ lệ.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Bước 6: Lưu dự án
Lưu các thay đổi vào một tệp mới để chúng tôi có thể kiểm tra lại tỷ lệ đã lưu sau này.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Bước 7: Khôi phục các phân công tài nguyên
Tải lại dự án đã lưu và **đọc tỷ lệ** để xác nhận nó đã được ghi đúng.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Những lỗi thường gặp & Mẹo
- **UID Mismatch** – Khi lấy các phân công theo UID, hãy đảm bảo các giá trị UID khớp với những giá trị đã được gán trong quá trình tạo.  
- **Incorrect Resource Type** – Sử dụng `ResourceType.Material` cho một tài nguyên công việc sẽ gây ra các tính toán tỷ lệ hoạt động không như mong đợi.  
- **Saving Format** – Luôn lưu bằng `SaveFileFormat.Mpp` (hoặc định dạng hỗ trợ khác) để giữ lại các trường tùy chỉnh như tỷ lệ.  
- **Large Projects** – Aspose.Tasks có thể xử lý các tệp có **hơn 500 trang** mà không cần tải toàn bộ tài liệu vào bộ nhớ, nhờ kiến trúc streaming.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java với bất kỳ IDE Java nào không?**  
A: Có, Aspose.Tasks cho Java tương thích với tất cả các IDE Java chính, bao gồm IntelliJ IDEA, Eclipse và NetBeans.

**Q: Aspose.Tasks có hỗ trợ các định dạng tệp khác ngoài MPP không?**  
A: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp, bao gồm MPP, XML và HTML.

**Q: Aspose.Tasks có phù hợp cho quản lý dự án cấp doanh nghiệp không?**  
A: Hoàn toàn, Aspose.Tasks cung cấp các tính năng toàn diện để quản lý dự án ở bất kỳ quy mô nào, phù hợp cho quản lý dự án cấp doanh nghiệp.

**Q: Tôi có thể tùy chỉnh phân công tài nguyên hơn nữa ngoài tỷ lệ không?**  
A: Có, Aspose.Tasks cung cấp khả năng mở rộng để tùy chỉnh các phân công tài nguyên, bao gồm chi phí, công việc và điều chỉnh thời lượng.

**Q: Có diễn đàn cộng đồng cho hỗ trợ Aspose.Tasks không?**  
A: Có, bạn có thể tìm kiếm hỗ trợ và tương tác với người dùng khác trên diễn đàn Aspose.Tasks [đây](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2026-06-10  
**Kiểm tra với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo Phân công Tài nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Cách sửa đổi Phân công – Đọc Tài nguyên Chia sẻ với Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Cách Thêm Ghi chú vào Phân công Tài nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}