---
date: 2026-02-13
description: Tìm hiểu cách tạo hoạt động mới, thiết lập thư mục dữ liệu và lưu dự
  án dưới dạng MPP trong Aspose.Tasks Java. Hướng dẫn chi tiết này cũng bao gồm việc
  tùy chỉnh các trường bảng.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách tạo hoạt động mới & đặt thư mục dữ liệu Aspose.Tasks
url: /vi/java/project-configuration/configure-gantt-chart/
weight: 10
---

 to Task" etc.

Translate "Step 6: Customize Table – **customize table fields**" etc.

Translate "Step 7: Save Project" etc.

Translate "Common Issues and Solutions" table headings.

Translate issues.

Translate "Frequently Asked Questions" and Q&A.

Translate "Conclusion" etc.

Translate "Last Updated", "Tested With", "Author".

Make sure to keep markdown formatting.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Hoạt Động Mới & Đặt Thư Mục Dữ Liệu Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách đặt thư mục dữ liệu**, cách **tạo hoạt động mới**, và cách **lưu dự án dưới dạng MPP** đồng thời cấu hình chế độ xem Gantt MS Project Chart trong các dự án Aspose.Tasks bằng Java. Aspose.Tasks là một API Java mạnh mẽ cho phép bạn thao tác các tệp Microsoft Project một cách lập trình. Khi kết thúc hướng dẫn, bạn sẽ có thể **tùy chỉnh các trường bảng**, điều chỉnh thư mục dữ liệu, và trực quan hoá dự án của mình đúng như mong muốn.

## Câu trả lời nhanh
- **Bước đầu tiên là gì?** Đặt đường dẫn thư mục dữ liệu nơi các tệp dự án của bạn nằm.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho Java (có thể tải về từ trang chính thức).  
- **Tôi có thể thêm thuộc tính tùy chỉnh không?** Có – bạn có thể định nghĩa các thuộc tính mở rộng và hiển thị chúng trong biểu đồ Gantt.  
- **Có cần giấy phép để thử nghiệm không?** Một giấy phép tạm thời có sẵn cho mục đích đánh giá.  
- **IDE nào phù hợp nhất?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, NetBeans) đều hoạt động.

## “Đặt thư mục dữ liệu” là gì và tại sao lại quan trọng?
Việc đặt thư mục dữ liệu cho Aspose.Tasks chỉ định nơi đọc và ghi các tệp dự án. Nếu đường dẫn không đúng, API sẽ không thể tìm thấy các tệp `.mpp` của bạn, gây ra lỗi FileNotFound. Định nghĩa thư mục này ngay đầu mã giúp quy trình làm việc còn lại sạch sẽ và có thể lặp lại.

## Tại sao cần tùy chỉnh các trường bảng trong biểu đồ Gantt?
Các trường bảng tùy chỉnh cho phép bạn hiển thị thông tin bổ sung—như thuộc tính tùy chỉnh, dữ liệu nguồn lực, hoặc ghi chú dự án—trực tiếp trong chế độ xem Gantt. Điều này làm cho biểu đồ trở nên thông tin hơn đối với các bên liên quan và giảm nhu cầu chuyển đổi giữa nhiều báo cáo.

## Cách tạo hoạt động mới?
Tạo một hoạt động (task) mới là một trong những thao tác cốt lõi khi xây dựng hoặc cập nhật lịch trình dự án. Bằng cách thêm task một cách lập trình, bạn có thể tự động hoá việc tạo các kế hoạch dự án phức tạp, tích hợp dữ liệu từ các hệ thống khác, hoặc áp dụng các thay đổi hàng loạt mà không cần chỉnh sửa thủ công.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – bất kỳ phiên bản mới nào (8+).  
2. **Thư viện Aspose.Tasks** – tải về từ [đây](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo Java nào bạn ưa thích.

## Nhập các gói
Đầu tiên, nhập namespace Aspose.Tasks để bạn có thể làm việc với các lớp của nó:

```java
import com.aspose.tasks.*;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập Thư mục Dữ liệu
Xác định thư mục chứa các tệp dự án của bạn. Đây là bước **đặt thư mục dữ liệu** mà hướng dẫn tập trung vào.

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối tới thư mục nơi `project.mpp` được lưu.

### Bước 2: Tải Tệp Dự Án
Tạo một thể hiện `Project` bằng cách tải một tệp Microsoft Project hiện có.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Bước 3: Thêm Hoạt Động Mới
Chèn một task (hoạt động) mới vào gốc của dự án. Điều này minh họa **cách tạo hoạt động mới** một cách lập trình.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Bước 4: Định nghĩa Thuộc tính Tùy chỉnh
Tạo một định nghĩa thuộc tính tùy chỉnh mà bạn có thể gắn vào các task sau này.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Bước 5: Gắn Thuộc tính Tùy chỉnh vào Task
Gán thuộc tính vừa định nghĩa cho task bạn vừa tạo.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Bước 6: Tùy chỉnh Bảng – **customize table fields**
Thêm thuộc tính tùy chỉnh như một cột trong bảng biểu Gantt, chỉ định độ rộng, tiêu đề và căn chỉnh.

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
Ghi lại các thay đổi vào một tệp mới có thể mở trong Microsoft Project. Bước này **lưu dự án dưới dạng MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **FileNotFoundException** khi tải dự án | Đường dẫn **đặt thư mục dữ liệu** không đúng hoặc thiếu dấu gạch chéo cuối. | Kiểm tra `dataDir` trỏ đúng tới thư mục và bao gồm ký tự phân tách thích hợp (`/` hoặc `\\`). |
| Thuộc tính tùy chỉnh không hiển thị trong chế độ xem Gantt | Trường bảng được thêm ở vị trí sai hoặc độ rộng cột quá nhỏ. | Đảm bảo `table.getTableFields().add(3, attrField);` sử dụng chỉ mục hợp lệ và điều chỉnh `setWidth` cho phù hợp. |
| LicenseException khi lưu | Không có giấy phép hợp lệ được áp dụng cho môi trường sản xuất. | Áp dụng giấy phép tạm thời hoặc vĩnh viễn trước khi gọi `project.save()`. |

## Câu hỏi thường gặp

**H: Tôi có thể dùng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
Đ: Có, Aspose.Tasks hỗ trợ nhiều ngôn ngữ lập trình bao gồm .NET, Java và C++.

**H: Có bản dùng thử miễn phí cho Aspose.Tasks không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).

**H: Tôi có thể tìm hỗ trợ cho Aspose.Tasks ở đâu?**  
Đ: Bạn có thể tìm hỗ trợ và đặt câu hỏi trên [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**H: Làm sao để mua giấy phép cho Aspose.Tasks?**  
Đ: Bạn có thể mua giấy phép từ [đây](https://purchase.aspose.com/buy).

**H: Tôi có cần giấy phép tạm thời cho mục đích thử nghiệm không?**  
Đ: Có, bạn có thể lấy giấy phép tạm thời từ [đây](https://purchase.aspose.com/temporary-license/).

## Kết luận
Bạn đã học cách **đặt thư mục dữ liệu**, **tạo hoạt động mới**, định nghĩa và gắn thuộc tính tùy chỉnh, và **lưu dự án dưới dạng MPP** đồng thời **tùy chỉnh các trường bảng** trong chế độ xem biểu đồ Gantt bằng Aspose.Tasks cho Java. Những bước này cho phép bạn kiểm soát hoàn toàn cách dữ liệu dự án được hiển thị, làm cho biểu đồ Gantt của bạn trở nên thông tin hơn và phù hợp với nhu cầu của các bên liên quan.

---

**Cập nhật lần cuối:** 2026-02-13  
**Kiểm tra với:** Aspose.Tasks Java 24.12 (mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}