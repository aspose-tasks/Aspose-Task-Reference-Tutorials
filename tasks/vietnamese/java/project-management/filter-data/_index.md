---
date: 2025-12-25
description: Tìm hiểu cách lọc các tệp MPP bằng Aspose.Tasks cho Java và tùy chỉnh
  tiêu chí lọc để tối ưu hoá quy trình quản lý dự án của bạn.
linktitle: How to Filter MPP Files Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Cách lọc tệp MPP bằng Aspose.Tasks cho Java
url: /vi/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lọc MPP tệp bằng Aspose.Tasks cho Java

## Giới thiệu
Nếu bạn đang làm việc với các tệp Microsoft Project (.mpp) trong một ứng dụng Java, bạn thường cần **đọc** các nhiệm vụ, nguồn lực hoặc phân tích để trung gian tập tin vào dữ liệu thực sự quan trọng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn **cách lọc mpp** tệp cấu hình bằng Aspose.Tasks cho Java và cho bạn thấy cách **tùy chỉnh bộ lọc tiêu chuẩn** để phù hợp với yêu cầu báo cáo trả tiền của dự án. Khi hoàn thành, bạn sẽ có một ví dụ rõ ràng, từng bước mà bạn có thể đưa vào cơ sở mã của mình.

## Trả lời nhanh
- **“filter mpp” nghĩa là gì?** Nó đề cập đến việc trích xuất một dữ liệu dự phòng tập tin dựa trên các điều kiện đã được xác định.
- **Thư viện nào xử lý việc này?** Aspose.Tasks cho Java cung cấp một API phong phú để tạo và áp dụng bộ lọc.
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.
- **Tôi có thể lọc nhiệm vụ, tài nguyên và bài tập không?** Có – mỗi loại thực tế có bộ sưu tập bộ lọc riêng.
- **Có cần phải có Java 8 trở lên không?** Aspose.Tasks hỗ trợ Java 8 và các phiên bản sau.

## “Cách lọc mpp” trong Java là gì?
Lọc một tệp MPP có nghĩa là sử dụng API Aspose.Tasks để xác định tiêu chí chí (như ngày bắt đầu nhiệm vụ, chi phí hoặc tùy chỉnh trường) và sau đó chỉ lấy các quy tắc đáp ứng mục đó. Điều này giúp bạn tạo tập báo cáo, trạng thái tự động kiểm tra hoặc dự án hợp nhất dữ liệu với các hệ thống khác.

## Tại sao phải tùy chỉnh tiêu chí lọc?
Mỗi dự án đều có các mức ưu tiên riêng. Bằng cách **bộ lọc tiêu chuẩn**, bạn có thể thiết lập các nhiệm vụ có nguy cơ xảy ra rủi ro cao, các mục quá hạn hoặc nguồn năng lượng trong ngân sách, khiến cho dự án điều khiển bảng của bạn trở nên có hành động hơn và mã hóa của bạn tái sử dụng được.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Bộ công cụ phát triển Java (JDK)** – phiên bản 8 hoặc mới hơn.
2. **Aspose.Tasks for Java** – tải xuống từ [trang tải xuống](https://releases.aspose.com/tasks/java/).
3. **An IDE** – IntelliJ IDEA, Eclipse hoặc NetBeans đều hoạt động tốt.

## Nhập gói
Bắt đầu bằng cách nhập các lớp cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập Project
Đầu tiên, tạo một thể hiện `Project` trỏ tới tệp MPP bạn muốn làm việc với.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### Bước 2: Truy xuất bộ lọc
Aspose.Tasks lưu trữ các bộ lọc đã định nghĩa trước (ví dụ, “All Tasks”, “Critical Tasks”). Lấy bộ lọc bạn cần bằng chỉ mục hoặc tên.

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **Pro tip:** Sử dụng `project.getTaskFilters().getByName("My Custom Filter")` nếu bạn muốn một bộ lọc có tên.

### Bước 3: Truy cập tiêu chí lọc
Bây giờ bạn đã có đối tượng `Filter`, bạn có thể kiểm tra các hàng tiêu chí và phép toán logic (AND/OR) kết hợp chúng.

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### Bước 4: Truy xuất chi tiết tiêu chí
Mỗi hàng tiêu chí chứa một phép kiểm tra (ví dụ, “Equals”, “GreaterThan”) và trường mà nó áp dụng (ví dụ, “Start”, “Cost”).

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### Bước 5: Duyệt qua các hàng tiêu chí
Các bộ lọc phức tạp có thể có tiêu chí lồng nhau. Ở đây chúng tôi duyệt qua một nhóm tiêu chí cấp hai.

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### Bước 6: In thông tin tiêu chí
Cuối cùng, in ra chi tiết của mỗi tiêu chí lồng nhau để bạn có thể xác nhận logic của bộ lọc.

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **NullPointerException khi truy cập bộ lọc** | Đảm bảo thực hiện bảo vệ dự án trong bộ nhiệm vụ lọc; bạn có thể thêm bộ lọc bằng chương trình nếu cần. |
| **Trường tên sai** | Sử dụng enum `ItemType` (ví dụ: `ItemType.Task`) để tránh lỗi mô tả chính xác. |
| **Bộ lọc không trả về kết quả** | Xác định các kiểm tra toán tử và giá trị phù hợp với dữ liệu trong tệp MPP của bạn. |

## Câu hỏi thường gặp

**Q: Làm sao để tạo một bộ lọc mới hoàn toàn bằng chương trình?**
A: Sử dụng `project.getTaskFilters().add(new Filter("My Filter"))` và sau đó định nghĩa bộ sưu tập `FilterCriteria` của nó.

**Q: Tôi có thể áp dụng bộ lọc cho nguồn lực thay vì nhiệm vụ không?**
A: Có – sử dụng `project.getResourceFilters()` để làm việc với các bộ lọc dành riêng cho nguồn lực.

**Q: Có thể kết hợp nhiều bộ lọc với logic HOẶC không?**
A: Bạn có thể tạo một `FilterCriteria` cha với `Operation` được đặt là `OR` và bổ sung thêm các lẻ làm việc riêng lẻ tiêu chuẩn.

**Q: Aspose.Tasks có bộ lọc hỗ trợ trên các tùy chỉnh trường không?**
A: Chắc chắn. Các trường tùy chỉnh được xử lý giống như bất kỳ trường nào khác; tham chiếu chúng bằng enum giá trị `CustomField`.

**Q: Lọc ảnh hưởng nào có hiệu quả trên các tệp MPP lớn nhất?**
A: Lọc được thực hiện trong bộ nhớ và thường nhanh chóng, nhưng đối với các dự án cực lớn, cân nhắc tải chỉ các phần cần thiết bằng `ProjectReader`.

---

**Cập nhật lần cuối:** 2025-12-25
**Đã kiểm thử với:** Aspose.Tasks for Java 24.10
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}