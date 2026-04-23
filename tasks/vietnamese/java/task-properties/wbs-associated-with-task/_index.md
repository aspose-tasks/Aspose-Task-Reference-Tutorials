---
date: 2026-03-03
description: Tìm hiểu cách đánh số lại WBS trong Aspose.Tasks cho Java, quản lý phân
  chia công việc và tùy chỉnh mã WBS một cách hiệu quả với các ví dụ từng bước.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Đánh số lại WBS trong Aspose.Tasks cho Java
url: /vi/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đánh Số Lại WBS trong Aspose.Tasks cho Java

## Introduction
Nếu bạn cần **cách đánh số lại WBS** trong một tệp Microsoft Project bằng Aspose.Tasks cho Java, bạn đang ở đúng nơi. Hướng dẫn này sẽ hướng dẫn bạn đọc các mã WBS hiện có, tùy chỉnh chúng, và sau đó đánh số lại cấu trúc để dự án của bạn luôn được tổ chức. Cho dù bạn đang dọn dẹp một lịch trình cũ hay xây dựng một lịch trình mới từ đầu, việc thành thạo các bước này sẽ giúp bạn **quản lý cấu trúc phân chia công việc** một cách tự tin.

## Quick Answers
- **Việc đánh số lại WBS làm gì?** Nó tính lại số thứ tự phân cấp của các nhiệm vụ để phản ánh bất kỳ thay đổi cấu trúc nào.  
- **Lớp nào thực hiện việc đánh số lại?** `Project.renumberWBSCode`.  
- **Tôi có cần giấy phép để chạy mã không?** Cần một giấy phép Aspose.Tasks hợp lệ cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể tùy chỉnh định dạng WBS không?** Có—sử dụng `Task.set(Tsk.WBS, "...")` để gán bất kỳ chuỗi nào bạn muốn.  
- **Các điều kiện tiên quyết chính là gì?** Java JDK, thư viện Aspose.Tasks cho Java, và một tệp dự án hợp lệ (.mpp).

## What is a Work Breakdown Structure (WBS)?
Cấu trúc Phân chia Công việc (Work Breakdown Structure - WBS) là một biểu diễn phân cấp các kết quả và nhiệm vụ của dự án. Mỗi nhiệm vụ nhận được một mã (ví dụ 1.2.3) phản ánh vị trí của nó trong phân cấp. Việc đánh số lại trở nên cần thiết khi các nhiệm vụ được thêm, xóa hoặc sắp xếp lại, đảm bảo các mã vẫn hợp lý và dễ đọc.

## Why manage work breakdown and customize WBS codes?
- **Rõ ràng:** Mã WBS rõ ràng giúp các bên liên quan dễ dàng tìm thấy nhiệm vụ.  
- **Báo cáo:** Nhiều công cụ báo cáo dựa vào việc đánh số nhất quán.  
- **Linh hoạt:** Mã tùy chỉnh cho phép bạn căn chỉnh cấu trúc dự án với các tiêu chuẩn nội bộ.  

## Prerequisites
Trước khi chúng ta đi sâu vào mã, hãy xác nhận bạn có những thứ sau:

- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Tasks cho Java đã được thêm vào dự án của bạn. Bạn có thể tải về từ [here](https://releases.aspose.com/tasks/java/).  

## Import Packages
Đảm bảo bạn nhập các gói cần thiết để khởi động dự án của mình:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Read WBS Codes
Đầu tiên, chúng ta sẽ đọc các mã WBS hiện có để bạn có thể thấy những gì đang làm việc.

### Step 1: Load the Project
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Step 2: Collect Tasks
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Step 3: Parse and Customize
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Đoạn mã trên in ra WBS và mức độ hiện tại của mỗi nhiệm vụ, sau đó minh họa **tùy chỉnh mã wbs** bằng cách gán một chuỗi mới.

## Renumber Task WBS Codes
Bây giờ chúng ta sẽ thực sự đánh số lại phân cấp WBS.

### Step 1: Load the Project (Renumber Example)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Step 2: Select All Tasks
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Step 3: Output Initial WBS Codes
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Step 4: Renumber WBS Codes
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Step 5: Output Updated WBS Codes
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Bằng cách làm theo các bước này, bạn sẽ hiệu quả **cách đánh số lại wbs** cho bất kỳ tập hợp nhiệm vụ nào trong tệp dự án của mình.

## Common Issues and Solutions
- **WBS không thay đổi sau lời gọi `set`:** Đảm bảo bạn đang làm việc với đúng đối tượng nhiệm vụ và dự án được lưu sau khi sửa đổi.  
- **`renumberWBSCode` ném ngoại lệ:** Kiểm tra danh sách ID có khớp với số lượng nhiệm vụ cấp cao nhất không; nếu không, phương thức không thể ánh xạ các số mới một cách chính xác.  
- **Giá trị WBS thiếu:** Một số nhiệm vụ có thể có WBS `null` nếu chúng được nhập từ tệp không định nghĩa. Hãy sử dụng giá trị dự phòng trước khi in.

## Frequently Asked Questions

**Q: Tôi có thể tìm tài liệu cho Aspose.Tasks cho Java ở đâu?**  
A: Tài liệu có sẵn [here](https://reference.aspose.com/tasks/java/).

**Q: Làm sao tôi có thể tải xuống Aspose.Tasks cho Java?**  
A: Bạn có thể tải về [here](https://releases.aspose.com/tasks/java/).

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí [here](https://releases.aspose.com/).

**Q: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?**  
A: Truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để được hỗ trợ.

**Q: Tôi có thể lấy giấy phép tạm thời cho Aspose.Tasks cho Java không?**  
A: Có, lấy giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể đổi tên định dạng WBS sau khi đánh số lại không?**  
A: Chắc chắn. Sau khi gọi `renumberWBSCode`, bạn có thể duyệt qua các nhiệm vụ và áp dụng `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` để phù hợp với quy ước đặt tên của bạn.

**Q: Việc đánh số lại có ảnh hưởng đến phụ thuộc của nhiệm vụ không?**  
A: Không. Phương thức chỉ cập nhật chuỗi WBS; các liên kết và ràng buộc nhiệm vụ vẫn không thay đổi.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}