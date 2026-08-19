---
date: 2026-02-28
description: Học cách sử dụng Aspose.Tasks cho Java để quản lý dữ liệu thời gian của
  nhiệm vụ, tải xuống thư viện, dùng thử miễn phí và tối ưu hoá việc theo dõi dự án.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách sử dụng Aspose.Tasks để quản lý dữ liệu theo thời gian của công việc (Java)
url: /vi/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng Aspose.Tasks cho Dữ liệu thời gian công việc của Task

## Introduction
Nếu bạn đang tìm cách **sử dụng Aspose** để kiểm soát chặt chẽ lịch trình dự án của mình, bạn đã đến đúng nơi. Việc theo dõi chính xác dữ liệu thời gian công việc của task là nền tảng của quản lý dự án thành công, và Aspose.Tasks for Java cung cấp cho bạn các công cụ cần thiết để tự động hoá quá trình này. Trong hướng dẫn này chúng tôi sẽ đi qua một ví dụ hoàn chỉnh, từ đầu đến cuối, cho thấy cách sử dụng Aspose.Tasks để tạo dự án, gán tài nguyên, đặt baseline, và cuối cùng truy xuất và hiển thị dữ liệu thời gian.

## Quick Answers
- **Dữ liệu “timephased” có nghĩa là gì?** Đó là dữ liệu được chia nhỏ theo các khoảng thời gian (ngày, tuần, tháng) thể hiện công việc, chi phí hoặc công việc còn lại trong suốt thời gian dự án.  
- **Thư viện nào cung cấp khả năng này?** Aspose.Tasks for Java.  
- **Tôi có cần giấy phép để chạy mẫu không?** Bản dùng thử miễn phí đủ cho phát triển; một giấy phép là bắt buộc cho môi trường sản xuất.  
- **Phiên bản Java yêu cầu là gì?** Java 8 hoặc cao hơn.  
- **Tôi có thể xuất kết quả ra Excel không?** Có – bạn có thể duyệt qua collection `TimephasedData` và ghi giá trị ra bất kỳ định dạng nào bạn cần.

## What is Task Timephased Data?
Dữ liệu thời gian công việc của Task đại diện cho lượng công việc (hoặc chi phí) được lên kế hoạch cho một task trong mỗi khoảng thời gian của lịch dự án. Nó cho phép bạn nhìn thấy cách công việc được phân bổ, phát hiện quá tải và so sánh tiến độ dự kiến với thực tế.

## Why Use Aspose.Tasks to Manage Timephased Data?
- **Kiểm soát đầy đủ** – tạo, sửa đổi và truy vấn thông tin thời gian công việc một cách lập trình mà không cần mở Microsoft Project.  
- **Đa nền tảng** – hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **Không phụ thuộc COM** – lý tưởng cho tự động hoá phía máy chủ.  
- **API phong phú** – hỗ trợ baseline, work contour và các trường tùy chỉnh ngay từ đầu.

## Prerequisites
Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn có:

- **Môi trường phát triển Java** – JDK 8+ đã được cài đặt và `JAVA_HOME` được cấu hình.  
- **Thư viện Aspose.Tasks for Java** – Tải xuống và đưa thư viện Aspose.Tasks vào dự án của bạn. Bạn có thể tìm thư viện [tại đây](https://releases.aspose.com/tasks/java/).  
- **Thư mục tài liệu** – Một thư mục trên máy của bạn nơi tệp dự án mẫu (`project.xml`) sẽ được đọc và ghi.

## Import Packages
Trong dự án Java của bạn, nhập các lớp Aspose.Tasks cần thiết:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Giải thích:* Chúng ta tạo một thể hiện `Project`, khởi tạo một `Calendar` với ngày bắt đầu mong muốn, và gán nó cho thuộc tính `START_DATE` của dự án.

## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Giải thích:* Một task mới có tên **Task** được thêm dưới task gốc. Chúng ta cũng tạo một tài nguyên có tên **Rsc** và đặt mức phí chuẩn và làm thêm giờ cho nó.

## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Giải thích:* Task được lên lịch với thời lượng **6 ngày**.

## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Giải thích:* Tài nguyên đã định nghĩa trước đó được liên kết với task thông qua một `ResourceAssignment`.

## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Giải thích:* Chúng ta đặt ngày dừng và ngày tiếp tục của assignment (sử dụng giá trị placeholder) và áp dụng work contour **Back‑Loaded**, làm cho nhiều công việc hơn được chuyển về cuối kỳ assignment.

## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Giải thích:* Ghi lại baseline cho phép bạn so sánh giá trị dự kiến với thực tế sau này.

## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Giải thích:* Task được đánh dấu là **hoàn thành 50 %**, điều này sẽ ảnh hưởng đến tính toán công việc còn lại.

## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Giải thích:* Lệnh này lấy **công việc còn lại** cho assignment, được chia theo các khoảng thời gian của dự án.

## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Giải thích:* Chúng ta chỉ in ra số lượng mục timephased và giá trị của mục đầu tiên. Trong thực tế, bạn sẽ duyệt danh sách và xuất dữ liệu ra báo cáo hoặc giao diện người dùng.

## Common Issues and Solutions
- **NullPointerException khi gọi `getTimephasedData`** – Đảm bảo các ngày `START` và `FINISH` của assignment được đặt trước khi gọi phương thức.  
- **Work contour không đúng** – Kiểm tra rằng `WorkContourType` bạn chọn phù hợp với chiến lược lập lịch; `BackLoaded` chỉ là một trong nhiều tùy chọn.  
- **Baseline không phản ánh thay đổi** – Hãy nhớ gọi `project.setBaseline` *sau* khi bạn đã định nghĩa các task, tài nguyên và assignment.

## Frequently Asked Questions
### Hỏi: Tôi có thể sử dụng Aspose.Tasks for Java trong bất kỳ dự án Java nào không?
A: Có, Aspose.Tasks for Java tương thích với bất kỳ dự án nào dựa trên Java.

### Hỏi: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Tasks for Java ở đâu?
A: Truy cập [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) để được hỗ trợ và thảo luận.

### Hỏi: Có bản dùng thử miễn phí cho Aspose.Tasks for Java không?
A: Có, bạn có thể khám phá bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Hỏi: Làm sao tôi có thể nhận giấy phép tạm thời cho Aspose.Tasks for Java?
A: Bạn có thể lấy giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Hỏi: Tôi có thể mua Aspose.Tasks cho Java ở đâu?
A: Bạn có thể mua Aspose.Tasks for Java [tại đây](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2026-02-28  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}