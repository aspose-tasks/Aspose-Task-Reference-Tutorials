---
date: 2025-12-09
description: Tìm hiểu cách đặt thư mục dữ liệu và cấu hình chế độ xem biểu đồ Gantt
  trong Aspose.Tasks bằng Java. Hướng dẫn này cũng chỉ ra cách tùy chỉnh các trường
  bảng và cấu hình dự án Java biểu đồ Gantt từng bước.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Đặt thư mục dữ liệu cho chế độ xem biểu đồ Gantt trong Aspose.Tasks
url: /vi/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Thư Mục Dữ Liệu cho Giao Diện Biểu Đồ Gantt trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách đặt thư mục dữ liệu** và cấu hình Gantt MS Project Chart View trong các dự án Aspose.Tasks bằng Java. Aspose.Tasks là một API Java mạnh mẽ cho phép bạn thao tác các tệp Microsoft Project một cách lập trình. Khi hoàn thành, bạn sẽ có thể **tùy chỉnh các trường bảng**, điều chỉnh thư mục dữ liệu và hiển thị dự án của mình chính xác như mong muốn.

## Trả lời nhanh
- **Bước đầu tiên là gì?** Đặt đường dẫn thư mục dữ liệu nơi các tệp dự án của bạn nằm.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho Java (tải về từ trang chính thức).  
- **Có thể thêm thuộc tính tùy chỉnh không?** Có – bạn có thể định nghĩa các thuộc tính mở rộng và hiển thị chúng trong biểu đồ Gantt.  
- **Cần giấy phép để thử nghiệm không?** Một giấy phép tạm thời có sẵn cho mục đích đánh giá.  
- **IDE nào phù hợp nhất?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, NetBeans) đều hoạt động.

## “đặt thư mục dữ liệu” là gì và tại sao lại quan trọng?
Việc đặt thư mục dữ liệu cho Aspose.Tasks chỉ định nơi đọc và ghi các tệp dự án. Nếu đường dẫn không đúng, API sẽ không tìm thấy các tệp `.mpp`, gây ra lỗi FileNotFound. Định nghĩa thư mục này ngay từ đầu giúp quy trình làm việc sau này sạch sẽ và có thể lặp lại.

## Tại sao cần tùy chỉnh các trường bảng trong biểu đồ Gantt?
Các trường bảng tùy chỉnh cho phép bạn hiển thị thêm thông tin—như thuộc tính tùy chỉnh, dữ liệu nguồn lực, hoặc ghi chú dự án—trực tiếp trong giao diện Gantt. Điều này làm cho biểu đồ trở nên thông tin hơn đối với các bên liên quan và giảm nhu cầu chuyển đổi giữa nhiều báo cáo.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – bất kỳ phiên bản mới nào (8+).  
2. **Thư viện Aspose.Tasks** – tải về từ [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo Java nào bạn ưa thích.

## Nhập các gói
Đầu tiên, nhập namespace của Aspose.Tasks để bạn có thể làm việc với các lớp của nó:

```java
import com.aspose.tasks.*;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập Thư mục Dữ liệu
Xác định thư mục chứa các tệp dự án của bạn. Đây là bước **đặt thư mục dữ liệu** mà hướng dẫn tập trung vào.

```java
String dataDir = "Your Data Directory";
```

Thay `"Your Data Directory"` bằng đường dẫn tuyệt đối tới thư mục chứa `project.mpp`.

### Bước 2: Tải Tệp Dự Án
Tạo một thể hiện `Project` bằng cách tải một tệp Microsoft Project hiện có.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Bước 3: Thêm Hoạt Động Mới
Chèn một nhiệm vụ (hoạt động) mới vào gốc của dự án.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Bước 4: Định Nghĩa Thuộc Tính Tùy Chỉnh
Tạo một định nghĩa thuộc tính tùy chỉnh mà bạn có thể gắn vào các nhiệm vụ sau này.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Bước 5: Thêm Thuộc Tính Tùy Chỉnh vào Nhiệm Vụ
Gán thuộc tính vừa định nghĩa cho nhiệm vụ bạn đã tạo.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Bước 6: Tùy Chỉnh Bảng – **customize table fields**
Thêm thuộc tính tùy chỉnh làm cột trong bảng biểu đồ Gantt, chỉ định độ rộng, tiêu đề và căn chỉnh.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Bước 7: Lưu Dự Án
Ghi lại các thay đổi vào một tệp mới có thể mở trong Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **FileNotFoundException** khi tải dự án | Đường dẫn **đặt thư mục dữ liệu** không đúng hoặc thiếu dấu gạch chéo cuối. | Kiểm tra `dataDir` trỏ đúng tới thư mục và bao gồm ký tự phân tách phù hợp (`/` hoặc `\\`). |
| Thuộc tính tùy chỉnh không hiển thị trong giao diện Gantt | Trường bảng được thêm ở vị trí sai hoặc độ rộng cột quá nhỏ. | Đảm bảo `table.getTableFields().add(3, attrField);` sử dụng chỉ mục hợp lệ và điều chỉnh `setWidth` nếu cần. |
| LicenseException khi lưu | Không có giấy phép hợp lệ được áp dụng cho môi trường sản xuất. | Áp dụng giấy phép tạm thời hoặc vĩnh viễn trước khi gọi `project.save()`. |

## Câu hỏi thường gặp

**H: Tôi có thể dùng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
Đ: Có, Aspose.Tasks hỗ trợ nhiều ngôn ngữ lập trình bao gồm .NET, Java và C++.

**H: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

**H: Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?**  
Đ: Bạn có thể tìm hỗ trợ và đặt câu hỏi trên [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**H: Làm thế nào để mua giấy phép cho Aspose.Tasks?**  
Đ: Bạn có thể mua giấy phép tại [here](https://purchase.aspose.com/buy).

**H: Tôi có cần giấy phép tạm thời cho mục đích thử nghiệm không?**  
Đ: Có, bạn có thể lấy giấy phép tạm thời từ [here](https://purchase.aspose.com/temporary-license/).

## Kết luận
Bạn đã học cách **đặt thư mục dữ liệu**, thêm hoạt động mới, định nghĩa và gắn thuộc tính tùy chỉnh, và **tùy chỉnh các trường bảng** trong giao diện biểu đồ Gantt bằng Aspose.Tasks cho Java. Những bước này cho phép bạn kiểm soát hoàn toàn cách dữ liệu dự án được hiển thị, làm cho biểu đồ Gantt của bạn trở nên thông tin hơn và phù hợp với nhu cầu của các bên liên quan.

---

**Cập nhật lần cuối:** 2025-12-09  
**Đã kiểm tra với:** Aspose.Tasks Java 24.12 (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}