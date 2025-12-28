---
date: 2025-12-28
description: Học cách thêm công việc và cập nhật tệp MPP bằng Aspose.Tasks cho Java,
  một thư viện quản lý dự án Java. Hãy làm theo hướng dẫn từng bước của chúng tôi
  để tạo công việc trong MPP và lưu dự án dưới dạng MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
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
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn **cách thêm nhiệm vụ** và cập nhật một tệp MPP bằng cách sử dụng Aspose.Tasks cho Java, một **thư viện quản lý dự án java** hàng đầu. Dù bạn đang xây dựng một bộ lập lịch tùy chỉnh hay cần sửa đổi các kế hoạch dự án hiện có một cách lập trình, hướng dẫn này sẽ dẫn bạn qua mọi bước—từ việc tải tệp đến lưu các thay đổi dưới dạng tài liệu MPP mới.

## Câu trả lời nhanh
- **“how to add task” có nghĩa là gì trong ngữ cảnh này?** Nó đề cập đến việc tạo một nhiệm vụ mới một cách lập trình bên trong một tệp Microsoft Project (MPP) hiện có.  
- **Thư viện nào thực hiện thao tác này?** Aspose.Tasks cho Java, một thư viện quản lý dự án java mạnh mẽ.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể lưu kết quả dưới dạng MPP không?** Có—sử dụng `project.save(..., SaveFileFormat.Mpp)` để **lưu dự án dưới dạng mpp**.  
- **Yêu cầu phiên bản Java nào?** Java 8 hoặc mới hơn.

## “how to add task” trong tệp MPP là gì?
Thêm một nhiệm vụ có nghĩa là chèn một mục công việc mới vào cấu trúc dự án, xác định ngày bắt đầu/kết thúc của nó, và lưu lại thay đổi vào tệp MPP. Aspose.Tasks trừu tượng hoá các chi tiết định dạng tệp cấp thấp, cho phép bạn tập trung vào logic nghiệp vụ.

## Tại sao nên sử dụng Aspose.Tasks cho Java?
- **Tương thích đầy đủ** với các tệp Microsoft Project 2007‑2021.  
- **Không cần cài đặt COM hoặc Office**—API Java thuần.  
- **Bộ tính năng phong phú**: liên kết nhiệm vụ, phân bổ nguồn lực, trường tùy chỉnh, và nhiều hơn nữa.  
- **Hiệu suất cao** cho các tệp dự án lớn, làm cho nó trở thành lựa chọn lý tưởng cho tự động hoá phía máy chủ.

## Yêu cầu trước
1. **Môi trường phát triển Java** – JDK 8+ đã được cài đặt và cấu hình.  
2. **Aspose.Tasks cho Java** – Tải về từ [trang tải xuống](https://releases.aspose.com/tasks/java/).  
3. **Kiến thức cơ bản về Java** – Quen thuộc với các lớp, đối tượng và xử lý ngày tháng.

## Nhập các gói
Đầu tiên, nhập các lớp bạn sẽ cần. Điều này cung cấp cho bạn quyền truy cập vào việc thao tác dự án, thuộc tính nhiệm vụ và xử lý ngày tháng.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Bước 1: Xác định Thư mục Dữ liệu
```java
String dataDir = "Your Data Directory";
```
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối nơi tệp MPP nguồn của bạn nằm.

## Bước 2: Đọc Dự án Hiện có
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
Constructor `Project` tải **SampleMSP2010.mpp**, cung cấp cho bạn một mô hình đối tượng có thể thao tác.

## Bước 3: Tạo Nhiệm vụ Mới (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Dòng này **tạo nhiệm vụ trong mpp** bằng cách thêm một nút con có tên *Task1* vào nhiệm vụ gốc.

## Bước 4: Đặt Ngày Bắt đầu và Kết thúc
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Ở đây chúng ta định nghĩa lịch trình cho nhiệm vụ mới được thêm. Điều chỉnh ngày tháng để phù hợp với thời gian dự án của bạn.

## Bước 5: Lưu Dự án (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
Dự án đã cập nhật, hiện chứa nhiệm vụ mới, được lưu lại dưới tên **AfterLinking.mpp**.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **File not found** | Kiểm tra `dataDir` kết thúc bằng dấu phân cách đường dẫn (`/` hoặc `\\`) và tên tệp là đúng. |
| **Incorrect dates** | Nhớ rằng các tháng trong `Calendar` được đánh số bắt đầu từ 0; `Calendar.JULY` là đúng cho tháng Bảy. |
| **License exception** | Cài đặt giấy phép Aspose.Tasks hợp lệ trước khi gọi bất kỳ API nào để tránh dấu nước đánh giá. |

## Câu hỏi thường gặp
### Q: Aspose.Tasks cho Java có thể xử lý cấu trúc dự án phức tạp không?
A: Có, Aspose.Tasks cho Java cung cấp các tính năng mạnh mẽ để xử lý cấu trúc dự án phức tạp một cách hiệu quả.  
### Q: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?
A: Có, bạn có thể tải bản dùng thử miễn phí từ [trang web](https://releases.aspose.com/).  
### Q: Aspose.Tasks cho Java có hỗ trợ các phiên bản khác nhau của tệp Microsoft Project không?
A: Chắc chắn, Aspose.Tasks cho Java hỗ trợ nhiều phiên bản tệp Microsoft Project, bao gồm các định dạng MPP, MPT và XML.  
### Q: Tôi có thể nhận giấy phép tạm thời cho Aspose.Tasks cho Java không?
A: Có, giấy phép tạm thời có sẵn cho mục đích thử nghiệm. Bạn có thể lấy chúng từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).  
### Q: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ về Aspose.Tasks cho Java ở đâu?
A: Bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ hoặc đặt câu hỏi.

## Câu hỏi thường gặp
**Q: Làm thế nào để thêm nhiều nhiệm vụ cùng một lúc?**  
A: Lặp qua một tập hợp các tên nhiệm vụ và lặp lại khối “create task” bên trong vòng lặp.

**Q: Tôi có thể đặt các trường tùy chỉnh cho nhiệm vụ mới không?**  
A: Có—sử dụng `task.set(Tsk.CUSTOM_FIELD_x, value)` trong đó *x* là chỉ số của trường.

**Q: Có thể sao chép một nhiệm vụ hiện có làm mẫu không?**  
A: Sao chép nhiệm vụ nguồn (`Task cloned = sourceTask.clone();`) rồi thêm nó vào cha mong muốn.

**Q: Nếu tôi cần cập nhật một nhiệm vụ hiện có thay vì thêm mới thì sao?**  
A: Lấy nhiệm vụ theo ID (`Task existing = project.getRootTask().getChildren().getById(id);`) và sửa đổi các thuộc tính của nó.

**Q: Aspose.Tasks có hỗ trợ lưu sang các định dạng khác như PDF hoặc PNG không?**  
A: Có—sử dụng `project.save("output.pdf", SaveFileFormat.Pdf);` hoặc `SaveFileFormat.Png` cho các biểu diễn hình ảnh.

**Cập nhật lần cuối:** 2025-12-28  
**Kiểm tra với:** Aspose.Tasks cho Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}