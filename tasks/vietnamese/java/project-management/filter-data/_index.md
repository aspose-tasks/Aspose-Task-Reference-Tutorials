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

# Cách lọc tệp MPP bằng Aspose.Tasks cho Java

## Introduction
Nếu bạn đang làm việc với các tệp Microsoft Project (.mpp) trong một ứng dụng Java, bạn thường cần **lọc** các nhiệm vụ, nguồn lực hoặc phân công để tập trung vào dữ liệu thực sự quan trọng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn **cách lọc mpp** tệp một cách lập trình bằng Aspose.Tasks cho Java, và cho bạn thấy cách **tùy chỉnh tiêu chí lọc** để phù hợp với nhu cầu báo cáo đặc thù của dự án. Khi hoàn thành, bạn sẽ có một ví dụ rõ ràng, từng bước mà bạn có thể đưa thẳng vào cơ sở mã của mình.

## Quick Answers
- **What does “filter mpp” mean?** Nó đề cập đến việc trích xuất một tập con dữ liệu dự án dựa trên các điều kiện đã định.  
- **Which library handles this?** Aspose.Tasks cho Java cung cấp một API phong phú để tạo và áp dụng bộ lọc.  
- **Do I need a license?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Can I filter tasks, resources, and assignments?** Có – mỗi loại thực thể có bộ sưu tập bộ lọc riêng.  
- **Is Java 8 or higher required?** Aspose.Tasks hỗ trợ Java 8 và các phiên bản sau.

## What is “how to filter mpp” in Java?
Lọc một tệp MPP có nghĩa là sử dụng API Aspose.Tasks để xác định tiêu chí (như ngày bắt đầu nhiệm vụ, chi phí, hoặc trường tùy chỉnh) và sau đó chỉ lấy các mục đáp ứng các quy tắc đó. Điều này giúp bạn tạo báo cáo tập trung, tự động kiểm tra trạng thái, hoặc tích hợp dữ liệu dự án với các hệ thống khác.

## Why customize filter criteria?
Mỗi dự án có các ưu tiên riêng. Bằng cách **tùy chỉnh tiêu chí lọc**, bạn có thể cô lập các nhiệm vụ có rủi ro cao, các mục quá hạn, hoặc các nguồn lực vượt ngân sách, làm cho bảng điều khiển dự án của bạn trở nên có hành động hơn và mã của bạn tái sử dụng được.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – phiên bản 8 hoặc mới hơn.  
2. **Aspose.Tasks for Java** – tải xuống từ [trang tải xuống](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse hoặc NetBeans đều hoạt động tốt.  

## Import Packages
Bắt đầu bằng cách nhập các lớp cần thiết vào dự án Java của bạn:

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Step‑by‑Step Guide

### Step 1: Set up the Project
Đầu tiên, tạo một thể hiện `Project` trỏ tới tệp MPP bạn muốn làm việc với.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### Step 2: Retrieve the Filter
Aspose.Tasks lưu trữ các bộ lọc đã định nghĩa trước (ví dụ, “All Tasks”, “Critical Tasks”). Lấy bộ lọc bạn cần bằng chỉ mục hoặc tên.

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **Pro tip:** Sử dụng `project.getTaskFilters().getByName("My Custom Filter")` nếu bạn muốn một bộ lọc có tên.

### Step 3: Access Filter Criteria
Bây giờ bạn đã có đối tượng `Filter`, bạn có thể kiểm tra các hàng tiêu chí và phép toán logic (AND/OR) kết hợp chúng.

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### Step 4: Retrieve Criteria Details
Mỗi hàng tiêu chí chứa một phép kiểm tra (ví dụ, “Equals”, “GreaterThan”) và trường mà nó áp dụng (ví dụ, “Start”, “Cost”).

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### Step 5: Iterate Through Criteria Rows
Các bộ lọc phức tạp có thể có tiêu chí lồng nhau. Ở đây chúng tôi duyệt qua một nhóm tiêu chí cấp hai.

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### Step 6: Print Criteria Information
Cuối cùng, in ra chi tiết của mỗi tiêu chí lồng nhau để bạn có thể xác nhận logic của bộ lọc.

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **NullPointerException khi truy cập bộ lọc** | Đảm bảo tệp dự án thực sự chứa bộ lọc nhiệm vụ; bạn có thể thêm bộ lọc bằng chương trình nếu cần. |
| **Tên trường không đúng** | Sử dụng enum `ItemType` (ví dụ, `ItemType.Task`) để tránh lỗi chính tả. |
| **Bộ lọc không trả về kết quả** | Xác minh các toán tử kiểm tra và giá trị khớp với dữ liệu trong tệp MPP của bạn. |

## FAQ's
### Q: Aspose.Tasks cho Java có tương thích với các phiên bản khác nhau của tệp Microsoft Project không?  
A: Có, Aspose.Tasks cho Java hỗ trợ nhiều phiên bản tệp Microsoft Project, đảm bảo tính tương thích và linh hoạt trong các nhiệm vụ quản lý dự án.

### Q: Tôi có thể tùy chỉnh tiêu chí lọc dựa trên yêu cầu cụ thể của dự án không?  
A: Chắc chắn! Aspose.Tasks cho Java cho phép bạn tùy chỉnh tiêu chí lọc theo nhu cầu riêng của dự án, cho phép thao tác và phân tích dữ liệu mục tiêu.

### Q: Aspose.Tasks cho Java có phù hợp cho cả dự án nhỏ và quy mô lớn không?  
A: Có, dù bạn đang quản lý một dự án quy mô nhỏ hay xử lý danh mục dự án lớn, Aspose.Tasks cho Java cung cấp khả năng mở rộng và hiệu năng cần thiết cho các kịch bản quản lý dự án đa dạng.

### Q: Aspose.Tasks cho Java có cung cấp tài liệu và tài nguyên hỗ trợ toàn diện không?  
A: Chắc chắn! Bạn có thể tham khảo [tài liệu](https://reference.aspose.com/tasks/java/) để có hướng dẫn chi tiết và tham chiếu API. Ngoài ra, bạn có thể tìm kiếm sự hỗ trợ từ diễn đàn cộng đồng Aspose.Tasks cho bất kỳ câu hỏi hoặc vấn đề nào.

### Q: Tôi có thể khám phá chức năng của Aspose.Tasks cho Java trước khi mua không?  
A: Tất nhiên! Bạn có thể dùng bản dùng thử miễn phí từ [trang web](https://releases.aspose.com/) để trải nghiệm các tính năng và khả năng của Aspose.Tasks cho Java.

## Frequently Asked Questions

**Q: Làm sao tạo bộ lọc mới hoàn toàn bằng chương trình?**  
A: Sử dụng `project.getTaskFilters().add(new Filter("My Filter"))` và sau đó định nghĩa bộ sưu tập `FilterCriteria` của nó.

**Q: Tôi có thể áp dụng bộ lọc cho nguồn lực thay vì nhiệm vụ không?**  
A: Có – sử dụng `project.getResourceFilters()` để làm việc với các bộ lọc riêng cho nguồn lực.

**Q: Có thể kết hợp nhiều bộ lọc với logic OR không?**  
A: Bạn có thể tạo một `FilterCriteria` cha với `Operation` được đặt là `OR` và thêm các tiêu chí riêng lẻ làm con.

**Q: Aspose.Tasks có hỗ trợ lọc trên các trường tùy chỉnh không?**  
A: Chắc chắn. Các trường tùy chỉnh được xử lý giống như bất kỳ trường nào khác; tham chiếu chúng bằng giá trị enum `CustomField`.

**Q: Lọc ảnh hưởng như thế nào đến hiệu năng trên các tệp MPP lớn?**  
A: Lọc được thực hiện trong bộ nhớ và thường nhanh, nhưng đối với các dự án cực lớn, hãy cân nhắc chỉ tải các phần cần thiết bằng `ProjectReader`.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}