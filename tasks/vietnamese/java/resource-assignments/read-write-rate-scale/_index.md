---
date: 2026-01-10
description: Học cách đọc tỷ lệ giá và quản lý việc phân công tài nguyên trong Aspose.Tasks
  cho Java. Định nghĩa tài nguyên vật liệu, cách thiết lập tỷ lệ và gán tài nguyên
  cho nhiệm vụ.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Đọc và Ghi Thang Tỷ Lệ cho Phân Công Nguồn Lực trong Aspose.Tasks
url: /vi/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đọc và Ghi Rate Scale cho Các Phân Công Tài Nguyên trong Aspose.Tasks

Trong hướng dẫn này, bạn sẽ khám phá **cách đọc** cài đặt rate scale và điều chỉnh chúng cho các phân công tài nguyên bằng Aspose.Tasks cho Java. Dù bạn đang xây dựng một bộ lập lịch, một công cụ báo cáo, hay chỉ cần tự động cập nhật dự án, việc thành thạo thao tác rate scale sẽ cho phép bạn kiểm soát chi tiết tài nguyên vật liệu và công việc.

## Trả Lời Nhanh
- **Lớp chính để xử lý rate là gì?** `ResourceAssignment` với thuộc tính `Asn.RATE_SCALE`.  
- **Enum nào định nghĩa các tùy chọn scale?** `RateScaleType` (Day, Week, Month, v.v.).  
- **Có cần giấy phép để chạy mẫu không?** Giấy phép dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần cho môi trường sản xuất.  
- **Có thể thay đổi scale sau khi lưu không?** Có – tải lại dự án và sửa `Asn.RATE_SCALE` như trong ví dụ.  
- **IDE nào được hỗ trợ?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, NetBeans) đều có thể biên dịch mã.

## Rate Scale là gì?
Rate scale xác định đơn vị thời gian (ngày, tuần, tháng, v.v.) mà tỷ lệ chi phí của tài nguyên được áp dụng. Điều chỉnh scale giúp bạn mô hình hoá việc tiêu thụ vật liệu hoặc nỗ lực lao động một cách chính xác.

## Tại sao cần đọc và ghi rate scale?
Đọc scale hiện tại giúp bạn kiểm tra các lịch trình đã có, trong khi ghi một scale mới cho phép bạn đồng bộ tài nguyên với chính sách thanh toán hoặc tiêu thụ của dự án. Điều này đặc biệt hữu ích khi **định nghĩa chi phí tài nguyên vật liệu** hoặc khi bạn cần **đặt scale** cho các lịch làm việc không chuẩn.

## Yêu Cầu Trước
Trước khi bắt đầu, hãy chắc chắn bạn đã chuẩn bị các yêu cầu sau:
1. **Môi trường phát triển Java** – JDK 8 trở lên đã được cài đặt.  
2. **Thư viện Aspose.Tasks cho Java** – Tải và cài đặt thư viện từ [đây](https://releases.aspose.com/tasks/java/).

## Nhập Gói
Đầu tiên, nhập các lớp cần thiết của Aspose.Tasks.

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

## Bước 1: Thiết lập dự án Java
Tạo một dự án Maven hoặc Gradle và thêm JAR Aspose.Tasks vào classpath. Bước này đảm bảo trình biên dịch có thể tìm thấy các lớp đã nhập.

## Bước 2: Tải tệp Dự Án
Tải tệp Microsoft Project hiện có mà bạn muốn làm việc.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Bước 3: Thêm một Task
Tạo một task mới mà sau này sẽ nhận các phân công tài nguyên.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Bước 4: Định Nghĩa Tài Nguyên
Ở đây chúng ta **định nghĩa tài nguyên vật liệu** và một tài nguyên công việc thông thường. Lưu ý việc sử dụng `ResourceType.Material` cho tài nguyên loại vật liệu.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Bước 5: Phân Công Tài Nguyên cho Task
Bây giờ chúng ta **phân công tài nguyên cho task** và chỉ định **cách đặt scale** bằng cách sử dụng `RateScaleType.Week`. Điều này minh họa cả việc đọc và ghi rate scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Bước 6: Lưu Dự Án
Ghi lại các thay đổi vào một tệp mới để sau này có thể xác minh rate scale đã được lưu.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Bước 7: Truy Xuất Phân Công Tài Nguyên
Tải lại dự án đã lưu và **đọc rate** scale để xác nhận rằng nó đã được ghi đúng.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Những Sai Lầm Thường Gặp & Mẹo
- **UID Không Khớp** – Khi truy xuất phân công bằng UID, hãy chắc chắn các giá trị UID khớp với những giá trị được gán trong quá trình tạo.  
- **Kiểu Tài Nguyên Sai** – Sử dụng `ResourceType.Material` cho tài nguyên công việc sẽ gây ra các tính toán rate không như mong đợi.  
- **Định Dạng Lưu** – Luôn lưu bằng `SaveFileFormat.Mpp` (hoặc một định dạng hỗ trợ khác) để giữ lại các trường tùy chỉnh như rate scale.

## Kết Luận
Quản lý và kiểm tra rate scale cho các phân công tài nguyên trong Aspose.Tasks cho Java trở nên đơn giản khi bạn nắm rõ các lớp và thuộc tính liên quan. Bằng cách làm theo hướng dẫn này, bạn có thể **đọc thông tin rate**, **định nghĩa đối tượng tài nguyên vật liệu**, **đặt scale**, và **phân công tài nguyên cho task** một cách tự tin.

## Câu Hỏi Thường Gặp

**H: Tôi có thể dùng Aspose.Tasks cho Java với bất kỳ IDE Java nào không?**  
Đ: Có, Aspose.Tasks cho Java tương thích với tất cả các IDE Java chính, bao gồm IntelliJ IDEA, Eclipse và NetBeans.

**H: Aspose.Tasks có hỗ trợ các định dạng tệp khác ngoài MPP không?**  
Đ: Có, Aspose.Tasks hỗ trợ nhiều định dạng tệp, bao gồm MPP, XML và HTML.

**H: Aspose.Tasks có phù hợp cho quản lý dự án cấp doanh nghiệp không?**  
Đ: Hoàn toàn, Aspose.Tasks cung cấp các tính năng toàn diện để quản lý dự án ở mọi quy mô, phù hợp cho môi trường doanh nghiệp.

**H: Tôi có thể tùy chỉnh phân công tài nguyên hơn nữa ngoài rate scale không?**  
Đ: Có, Aspose.Tasks cung cấp khả năng tùy chỉnh rộng rãi cho các phân công tài nguyên, bao gồm chi phí, công việc và điều chỉnh thời lượng.

**H: Có diễn đàn cộng đồng nào hỗ trợ Aspose.Tasks không?**  
Đ: Có, bạn có thể tìm kiếm hỗ trợ và giao lưu với người dùng khác trên diễn đàn Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2026-01-10  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}