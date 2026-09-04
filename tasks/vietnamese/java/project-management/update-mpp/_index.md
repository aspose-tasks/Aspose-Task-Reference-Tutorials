---
date: 2026-06-25
description: Tìm hiểu cách thêm nhiệm vụ và cập nhật các tệp MPP bằng Aspose.Tasks
  for Java, một thư viện quản lý dự án java cho phép bạn tạo các tệp Microsoft Project
  và lưu dự án dưới dạng MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Cách Thêm Nhiệm Vụ và Cập Nhật Tệp MPP trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách Thêm Nhiệm Vụ và Cập Nhật Tệp MPP trong Aspose.Tasks
url: /vi/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Nhiệm Vụ và Cập Nhật Tệp MPP trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách thêm nhiệm vụ** vào một tệp Microsoft Project (MPP) hiện có và sau đó lưu lịch trình đã cập nhật bằng Aspose.Tasks cho Java, một **thư viện quản lý dự án java** hàng đầu. Dù bạn đang xây dựng một bộ lập lịch tùy chỉnh, tự động hoá các cập nhật hàng loạt, hay tích hợp dữ liệu dự án vào một hệ thống lớn hơn, hướng dẫn chi tiết dưới đây sẽ chỉ cho bạn cách tải dự án, chèn một nhiệm vụ mới, đặt ngày cho nó và lưu kết quả dưới dạng tài liệu MPP mới.

## Câu trả lời nhanh
- **“cách thêm nhiệm vụ” có nghĩa là gì trong ngữ cảnh này?** Nó có nghĩa là tạo một mục công việc mới một cách lập trình bên trong một tệp MPP hiện có.  
- **Thư viện nào thực hiện thao tác này?** Aspose.Tasks cho Java, một thư viện quản lý dự án java mạnh mẽ.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể lưu kết quả dưới dạng MPP không?** Có—sử dụng `project.save(..., SaveFileFormat.Mpp)` để **lưu dự án dưới dạng mpp**.  
- **Yêu cầu phiên bản Java nào?** Java 8 hoặc mới hơn.

## “cách thêm nhiệm vụ” trong tệp MPP là gì?
Thêm một nhiệm vụ có nghĩa là chèn một mục công việc mới vào cấu trúc dự án, xác định ngày bắt đầu/kết thúc, và ghi lại thay đổi trở lại tệp MPP. Aspose.Tasks trừu tượng hoá các chi tiết định dạng tệp cấp thấp, cho phép bạn tập trung vào logic nghiệp vụ trong khi tự động xử lý các phân công tài nguyên, lịch làm việc và tính toán phụ thuộc. Nó cũng cập nhật bất kỳ phân công liên quan nào và tính lại lịch trình dự án để duy trì tính nhất quán giữa các nhiệm vụ phụ thuộc.

## Tại sao nên dùng Aspose.Tasks cho Java?
- **Tương thích đầy đủ**: Hỗ trợ 100% các tính năng của Microsoft Project 2007‑2021 (hơn 150 loại nhiệm vụ và 200 trường tài nguyên).  
- **Không phụ thuộc**: Không cần COM, Office, hay thư viện gốc—API Java thuần chạy ở bất kỳ môi trường JRE nào.  
- **Bộ tính năng phong phú**: Bao gồm liên kết nhiệm vụ, phân bổ tài nguyên, trường tùy chỉnh và báo cáo tích hợp.  
- **Hiệu năng cao**: Xử lý dự án lên tới 10.000 nhiệm vụ với dung lượng RAM dưới 200 MB, lý tưởng cho tự động hoá phía máy chủ.

## Yêu cầu trước
1. **Môi trường phát triển Java** – JDK 8+ đã được cài đặt và cấu hình.  
2. **Aspose.Tasks cho Java** – Tải về từ [trang tải xuống](https://releases.aspose.com/tasks/java/).  
3. **Kiến thức Java cơ bản** – Hiểu về lớp, đối tượng và xử lý ngày tháng.  

## Nhập gói
Đầu tiên, nhập các lớp bạn sẽ cần. Điều này cho phép bạn truy cập vào việc thao tác dự án, thuộc tính nhiệm vụ và xử lý ngày tháng.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` đại diện cho một tệp Microsoft Project được tải vào bộ nhớ. `SaveFileFormat` liệt kê các định dạng bạn có thể lưu, chẳng hạn như MPP hoặc PDF. `Task` mô hình hoá một mục công việc cá nhân trong cấu trúc dự án. `Tsk` cung cấp các hằng số cho các trường nhiệm vụ được dùng khi đặt hoặc lấy giá trị. `Calendar` cung cấp các tiện ích ngày‑giờ để định nghĩa lịch trình.

## Bước 1: Xác định Thư mục Dữ liệu
```java
String dataDir = "Your Data Directory";
```  
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối nơi tệp MPP nguồn của bạn nằm.

## Bước 2: Đọc Dự án Hiện có
Lớp `Project` là đối tượng cốt lõi của Aspose.Tasks đại diện cho một tệp Microsoft Project trong bộ nhớ.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Constructor này tải **SampleMSP2010.mpp**, cung cấp cho bạn một mô hình đối tượng có thể thao tác đầy đủ.

## Bước 3: Tạo Nhiệm vụ Mới (cách thêm nhiệm vụ)
Lớp `Task` đại diện cho một mục công việc cá nhân trong cấu trúc dự án.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Dòng này **tạo nhiệm vụ trong mpp** bằng cách thêm một nút con có tên *Task1* vào nhiệm vụ gốc.

## Bước 4: Đặt Ngày Bắt Đầu và Kết Thúc
Lớp `Calendar` cung cấp các tiện ích ngày‑giờ; các tháng được đánh số bắt đầu từ 0 (ví dụ, `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Ở đây chúng ta định nghĩa lịch trình cho nhiệm vụ vừa được thêm. Điều chỉnh ngày tháng cho phù hợp với thời gian dự án của bạn.

## Bước 5: Lưu Dự án (lưu dự án dưới dạng mpp)
`SaveFileFormat.Mpp` chỉ cho Aspose.Tasks ghi tệp trở lại ở định dạng Microsoft Project gốc.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Dự án đã cập nhật, hiện chứa nhiệm vụ mới, được lưu dưới tên **AfterLinking.mpp**.

## Các vấn đề thường gặp và Giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Không tìm thấy tệp** | Kiểm tra `dataDir` có kết thúc bằng ký tự phân tách đường dẫn (`/` hoặc `\\`) và tên tệp đúng. |
| **Ngày không đúng** | Nhớ rằng các tháng trong `Calendar` bắt đầu từ 0; `Calendar.JULY` là đúng cho tháng Bảy. |
| **Lỗi giấy phép** | Cài đặt giấy phép Aspose.Tasks hợp lệ trước khi gọi bất kỳ API nào để tránh watermark đánh giá. |

## Câu hỏi thường gặp
**H: Làm sao để thêm nhiều nhiệm vụ cùng lúc?**  
Đ: Lặp qua một tập hợp tên nhiệm vụ và lặp lại khối “tạo nhiệm vụ” bên trong vòng lặp.

**H: Tôi có thể đặt trường tùy chỉnh cho nhiệm vụ mới không?**  
Đ: Có—sử dụng `task.set(Tsk.CUSTOM_FIELD_x, value)` trong đó *x* là chỉ số trường.

**H: Có thể sao chép một nhiệm vụ hiện có làm mẫu không?**  
Đ: Clone nhiệm vụ nguồn (`Task cloned = sourceTask.clone();`) rồi thêm nó vào parent mong muốn.

**H: Nếu tôi cần cập nhật một nhiệm vụ hiện có thay vì thêm mới thì sao?**  
Đ: Lấy nhiệm vụ theo ID (`Task existing = project.getRootTask().getChildren().getById(id);`) và sửa đổi các thuộc tính của nó.

**H: Aspose.Tasks có hỗ trợ lưu sang các định dạng khác như PDF hoặc PNG không?**  
Đ: Có—sử dụng `project.save("output.pdf", SaveFileFormat.Pdf);` hoặc `SaveFileFormat.Png` cho các biểu diễn hình ảnh.

---

**Cập nhật lần cuối:** 2026-06-25  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Cách Tạo Tệp MPP – Tạo & Lưu Dự Án Trống ở Định Dạng MPP với Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Cách Tạo Dự Án – Đặt Thuộc Tính Nhiệm Vụ Mới với Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Tạo Danh Sách Nhiệm Vụ Java – Baseline Dự Án MS bằng Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}