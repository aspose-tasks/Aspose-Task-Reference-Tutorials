---
date: 2025-12-07
description: Tìm hiểu cách lưu tệp dự án, viết và đọc công thức MS Project, và thêm
  công thức trường tùy chỉnh bằng Aspose.Tasks cho Java.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Lưu tệp dự án và viết công thức MS Project với Aspose.Tasks
url: /vi/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lưu Tệp Dự Án và Viết Công Thức MS Project với Aspose.Tasks

## Giới thiệu
Trong lĩnh vực quản lý dự án, việc xử lý dữ liệu hiệu quả là vô cùng quan trọng. Aspose.Tasks for Java là một giải pháp mạnh mẽ giúp thao tác và trích xuất dữ liệu từ các tệp Microsoft Project. Một tính năng mạnh mẽ mà nó cung cấp là khả năng viết và đọc công thức MS Project. **Bạn cũng sẽ học cách *save project file* sau khi áp dụng các công thức**, đảm bảo các thay đổi của bạn được lưu lại cho việc phân tích trong tương lai. Hướng dẫn này sẽ chỉ cho bạn cách tận dụng chức năng này để nâng cao các nhiệm vụ quản lý dự án của mình.

## Câu trả lời nhanh
- **“save project file” làm gì?** Nó ghi lại tất cả các thay đổi trong bộ nhớ trở lại tệp .mpp trên đĩa.  
- **Tôi có thể thêm công thức trường tùy chỉnh không?** Có – bạn có thể tạo một trường tùy chỉnh và gán công thức như “double task cost”.  
- **Có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **IDE nào hoạt động tốt nhất?** Bất kỳ IDE Java nào (IntelliJ IDEA, Eclipse, VS Code) đều có thể biên dịch mẫu.  
- **API có tương thích với phiên bản MS Project mới nhất không?** Aspose.Tasks hỗ trợ tất cả các định dạng .mpp gần đây.

## “save project file” là gì trong Aspose.Tasks?
Lưu tệp dự án có nghĩa là ghi lại trạng thái hiện tại của đối tượng `Project` — bao gồm các nhiệm vụ, nguồn lực và bất kỳ công thức tùy chỉnh nào — vào một tệp Microsoft Project thực tế (`.mpp`). Thao tác này là cần thiết sau khi bạn sửa đổi dữ liệu, chẳng hạn như thêm trường tùy chỉnh hoặc thay đổi chi phí nhiệm vụ.

## Tại sao thêm trường tùy chỉnh và tạo công thức trường tùy chỉnh?
Thêm trường tùy chỉnh cung cấp cho bạn một container linh hoạt cho thông tin bổ sung mà các trường mặc định không bao phủ. Bằng cách gắn một công thức — như một công thức **double task cost** — bạn tự động hoá các phép tính, giảm lỗi thủ công và giữ cho dữ liệu lịch trình luôn nhất quán.

## Yêu cầu trước
Trước khi bắt đầu hướng dẫn này, hãy đảm bảo bạn đã có các yêu cầu sau:

1. **Java Development Kit (JDK)** – Java 8 trở lên đã được cài đặt trên máy của bạn.  
2. **Aspose.Tasks for Java** – Tải về và cài đặt từ [here](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Chọn IDE ưa thích của bạn để phát triển Java (IntelliJ IDEA, Eclipse, VS Code, v.v.).  

## Nhập các gói
Để bắt đầu, nhập các gói cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Bước 1: Thiết lập Thư mục Dữ liệu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Xác định thư mục nơi lưu trữ các tệp MS Project của bạn. Đây là nơi bạn sẽ tải tệp nguồn và sau này **save project file**.

## Bước 2: Tải tệp Dự án
```java
Project project = new Project(dataDir + "project.mpp");
```
Tải tệp Microsoft Project hiện có vào một đối tượng `Project` để bạn có thể đọc hoặc sửa đổi nội dung của nó.

## Bước 3: Thêm Trường Tùy chỉnh và Tạo Công thức Trường Tùy chỉnh
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
Trong bước này chúng ta **add custom field** “Double Costs” và **create custom field formula** nhân `[Cost]` của nhiệm vụ lên 2, thực hiện **double task cost**. Phương thức `setFormula` nhúng phép tính trực tiếp vào tệp dự án.

## Bước 4: Thêm Nhiệm vụ và Đặt Chi phí
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Tạo một nhiệm vụ mới, sau đó gán chi phí cơ bản là `100`. Khi dự án được lưu, trường tùy chỉnh sẽ tự động hiển thị `200` nhờ công thức đã định nghĩa ở trên.

## Bước 5: Lưu Tệp Dự Án
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Cuối cùng, **save project file** với tất cả các thay đổi. Phương thức `save` ghi lại dự án đã cập nhật, bao gồm trường tùy chỉnh mới và các giá trị tính toán, vào `saved.mpp`.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **Công thức không được áp dụng** | Trường tùy chỉnh chưa được thêm vào bộ sưu tập `ExtendedAttributes` của dự án. | Đảm bảo thực hiện `project.getExtendedAttributes().add(attr);` trước khi lưu. |
| **Không tìm thấy tệp** | Đường dẫn `dataDir` không đúng. | Kiểm tra chuỗi thư mục kết thúc bằng ký tự phân tách đường dẫn (`/` hoặc `\\`). |
| **Chi phí hiển thị là 0** | Chi phí nhiệm vụ chưa được đặt trước khi lưu. | Gọi `task.set(Tsk.COST, ...)` trước `project.save`. |

## Câu hỏi thường gặp
**Q: Aspose.Tasks có tương thích với mọi phiên bản của MS Project không?**  
A: Có, Aspose.Tasks hỗ trợ một loạt các phiên bản MS Project, từ các định dạng .mpp cũ đến các bản phát hành mới nhất.

**Q: Tôi có thể tích hợp Aspose.Tasks vào dự án Java hiện có của mình không?**  
A: Chắc chắn. API được thiết kế để tích hợp liền mạch; chỉ cần thêm JAR Aspose.Tasks vào classpath của dự án.

**Q: Có bất kỳ hạn chế nào đối với các loại công thức tôi có thể tạo không?**  
A: Thư viện hỗ trợ hầu hết cú pháp công thức gốc của MS Project, bao gồm các phép toán, logic và các hàm tích hợp. Các hàm tùy chỉnh phức tạp có thể cần giải pháp thay thế.

**Q: Aspose.Tasks có hỗ trợ triển khai đa nền tảng không?**  
A: Có, thư viện chạy trên bất kỳ nền tảng nào hỗ trợ Java, bao gồm Windows, Linux và macOS.

**Q: Làm sao tôi có thể nhận hỗ trợ kỹ thuật cho Aspose.Tasks?**  
A: Truy cập [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để nhận trợ giúp cộng đồng, hoặc mở ticket hỗ trợ nếu bạn có giấy phép thương mại.

## Kết luận
Trong hướng dẫn này chúng ta đã tìm hiểu cách **save project file**, **add custom field**, và **create a custom field formula** để **double task cost** bằng Aspose.Tasks for Java. Bằng cách thực hiện các bước này, bạn có thể tự động hoá các phép tính, làm phong phú dữ liệu dự án và đảm bảo mọi thay đổi được lưu lại cho các báo cáo và phân tích trong tương lai.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}