---
date: 2026-02-18
description: Tìm hiểu cách đọc dữ liệu định nghĩa nhóm từ các tệp Microsoft Project
  bằng Aspose.Tasks cho Java. Hướng dẫn này cho thấy cách đọc chi tiết nhóm và trích
  xuất thông tin nhóm nhiệm vụ.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách đọc dữ liệu định nghĩa nhóm trong Aspose.Tasks
url: /vi/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Dữ liệu Định nghĩa Nhóm trong Aspose.Tasks

## Giới thiệu
Aspose.Tasks for Java là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác các tệp Microsoft Project một cách dễ dàng. Trong hướng dẫn này, **bạn sẽ học cách đọc định nghĩa nhóm** dữ liệu từ một tệp dự án từng bước, để bạn có thể trích xuất và làm việc với thông tin nhóm nhiệm vụ trong các ứng dụng Java của mình. Hiểu **cách đọc nhóm** chi tiết giúp bạn tự động hoá báo cáo, di chuyển cài đặt và xác thực cấu trúc dự án một cách lập trình.

## Câu trả lời nhanh
- **“Đọc định nghĩa nhóm” có nghĩa là gì?** Nó đề cập đến việc trích xuất định nghĩa của các nhóm nhiệm vụ (tên, tiêu chí, định dạng) từ một tệp Microsoft Project.  
- **Thư viện tôi cần là gì?** Aspose.Tasks for Java.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các IDE nào được hỗ trợ?** Bất kỳ IDE Java nào như IntelliJ IDEA hoặc Eclipse.  
- **Cần bao nhiêu mã?** Ít hơn 30 dòng Java để tải dự án và hiển thị chi tiết nhóm.

## Cách Đọc Dữ liệu Định nghĩa Nhóm
Dưới đây là một hướng dẫn ngắn gọn, từng bước cho thấy **cách đọc nhóm** thông tin từ tệp `.mpp`. Mỗi bước bao gồm một giải thích ngắn và đoạn mã chính xác bạn cần chạy.

## Định nghĩa đọc nhóm là gì?
Một *định nghĩa nhóm* trong Microsoft Project mô tả cách các nhiệm vụ được nhóm lại dựa trên tiêu chí (ví dụ: trạng thái, mức độ ưu tiên). Đọc định nghĩa này cho phép bạn kiểm tra logic nhóm, màu sắc, phông chữ và thứ tự sắp xếp được áp dụng trong tệp dự án một cách lập trình.

## Tại sao cần đọc dữ liệu định nghĩa nhóm?
- **Tự động hoá:** Tạo báo cáo tùy chỉnh phản ánh cách nhóm trong Project.  
- **Di chuyển:** Chuyển quy tắc nhóm sang dự án khác hoặc hệ thống quản lý dự án khác.  
- **Xác thực:** Đảm bảo các nhóm mong muốn tồn tại trước khi thực hiện cập nhật hàng loạt.  
- **Tùy chỉnh:** Áp dụng logic kinh doanh bổ sung dựa trên phông chữ hoặc màu sắc của nhóm.  
- **Hiểu biết:** Biết **cách đọc nhóm** giúp bạn khắc phục các bố cục nhiệm vụ không mong muốn.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn có:

1. **Java Development Kit (JDK)** – bất kỳ phiên bản mới nào (8 trở lên).  
2. **Aspose.Tasks for Java Library** – tải về từ [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo nào bạn thích.  

## Nhập các gói
Đầu tiên, nhập gói core của Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập Thư mục Dữ liệu của Bạn
Xác định thư mục chứa tệp `.mpp` bạn muốn kiểm tra.

```java
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối tới vị trí tệp dự án của bạn.

### Bước 2: Tải tệp Dự án
Tạo một thể hiện `Project` bằng cách chỉ tới tệp `.mpp` của bạn.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Bước 3: Lấy số lượng Nhóm Nhiệm vụ
In ra tổng số nhóm nhiệm vụ được định nghĩa trong dự án.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Bước 4: Lấy Thông tin Nhóm Nhiệm vụ Cụ thể
Lấy một nhóm cụ thể (chỉ mục 1 trong ví dụ này) và hiển thị tên cùng số lượng tiêu chí mà nó chứa.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Bước 5: Lấy Thông tin Tiêu chí Nhóm
Mỗi nhóm có thể có một hoặc nhiều tiêu chí. Đoạn mã dưới đây trích xuất các chi tiết như trường dùng để nhóm, chế độ nhóm, màu ô và mẫu.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Bước 6: Kiểm tra Nhóm Cha
Đôi khi một tiêu chí thuộc về một nhóm cha. Kiểm tra này xác nhận mối quan hệ.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Bước 7: Lấy Thông tin Phông chữ của Tiêu chí
Tiêu chí nhóm có thể có kiểu phông chữ tùy chỉnh. Đoạn mã sau in ra họ phông chữ, kích thước, kiểu và hướng sắp xếp.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **`NullPointerException` on `criterion.getParentGroup()`** | Tiêu chí có thể không có nhóm cha. | Thêm kiểm tra null trước khi so sánh. |
| **File not found** | Đường dẫn `dataDir` không đúng. | Sử dụng `Paths.get(dataDir, "project.mpp").toAbsolutePath()` để xác minh. |
| **License not set** | Thư viện Aspose chạy ở chế độ đánh giá và có thể giới hạn đầu ra. | Đăng ký giấy phép với `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks for Java để sửa đổi tệp dự án không?**  
A: Có, thư viện cung cấp khả năng đọc/ghi đầy đủ cho các tệp Microsoft Project.

**Q: Aspose.Tasks for Java có tương thích với mọi phiên bản tệp Microsoft Project không?**  
A: Nó hỗ trợ MPP, XML và các định dạng Project phổ biến khác trên nhiều phiên bản.

**Q: Làm sao để xử lý lỗi khi làm việc với Aspose.Tasks for Java?**  
A: Bao quanh các thao tác file bằng khối `try‑catch` và kiểm tra `TasksException` để có thông báo chi tiết.

**Q: Aspose.Tasks for Java có hỗ trợ xuất dữ liệu dự án sang các định dạng khác không?**  
A: Chắc chắn – bạn có thể xuất ra PDF, XLSX, CSV và nhiều định dạng khác bằng API xuất của thư viện.

**Q: Tôi có thể tìm tài nguyên và hỗ trợ bổ sung cho Aspose.Tasks for Java ở đâu?**  
A: Truy cập [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) để xem tài liệu API đầy đủ và [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ cộng đồng.

## Kết luận
Trong hướng dẫn này chúng ta đã đi qua **cách đọc nhóm** dữ liệu định nghĩa từ một tệp Microsoft Project bằng Aspose.Tasks for Java. Bằng cách thực hiện các bước trên, bạn có thể trích xuất tên nhóm, tiêu chí, định dạng và mối quan hệ nhóm‑cha, giúp bạn xây dựng báo cáo tùy chỉnh, di chuyển cài đặt hoặc tự động hoá logic xác thực trong các ứng dụng Java của mình.

---

**Cập nhật lần cuối:** 2026-02-18  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}