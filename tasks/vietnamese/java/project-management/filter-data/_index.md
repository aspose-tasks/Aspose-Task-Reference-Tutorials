---
date: 2026-06-05
description: Tìm hiểu cách lọc tệp MPP bằng Aspose.Tasks cho Java, tùy chỉnh tiêu
  chí lọc và lọc các công việc theo ngày để tối ưu hoá quản lý dự án.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Cách lọc tệp MPP bằng Aspose.Tasks cho Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách lọc tệp MPP bằng Aspose.Tasks cho Java
url: /vi/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lọc tệp MPP bằng Aspose.Tasks cho Java

## Giới thiệu
Nếu bạn đang làm việc với các tệp Microsoft Project (*.mpp*) trong một ứng dụng Java, bạn thường cần **lọc tệp MPP** để cô lập các công việc, nguồn lực hoặc phân công quan trọng nhất. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn **cách lọc mpp** một cách lập trình bằng Aspose.Tasks cho Java, cho bạn thấy cách **tùy chỉnh tiêu chí lọc**, và trình bày một kịch bản thực tế “lọc công việc theo ngày”. Khi kết thúc, bạn sẽ có một đoạn mã sẵn sàng sử dụng mà có thể chèn vào bất kỳ dự án Java nào.

## Câu trả lời nhanh
- **What does “filter mpp” mean?** Ý nghĩa của “filter mpp” là gì? Nó có nghĩa là trích xuất một tập con dữ liệu dự án dựa trên các điều kiện đã định.  
- **Which library handles this?** Thư viện nào xử lý việc này? Aspose.Tasks cho Java cung cấp một API toàn diện để tạo và áp dụng bộ lọc.  
- **Do I need a license?** Tôi có cần giấy phép không? Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **Can I filter tasks, resources, and assignments?** Tôi có thể lọc công việc, nguồn lực và phân công không? Có – mỗi loại thực thể có bộ sưu tập bộ lọc riêng.  
- **Is Java 8 or higher required?** Có yêu cầu Java 8 hoặc cao hơn không? Aspose.Tasks hỗ trợ Java 8 và các phiên bản sau.

## “how to filter mpp” trong Java là gì?
`How to filter mpp` là quá trình sử dụng các đối tượng `Filter` của Aspose.Tasks để chọn chỉ những phần tử dự án đáp ứng các điều kiện cụ thể như ngày bắt đầu, chi phí hoặc trường tùy chỉnh. Tải một `Project`, lấy một `Filter`, và API sẽ trả về một tập hợp khớp với tiêu chí của bạn, cho phép báo cáo tập trung hoặc tích hợp downstream.

## Tại sao nên tùy chỉnh tiêu chí lọc?
Tiêu chí lọc tùy chỉnh cho phép bạn nhắm mục tiêu các công việc có rủi ro cao, các mục quá hạn, hoặc các nguồn lực vượt ngân sách, biến một tệp dự án khổng lồ thành một góc nhìn ngắn gọn, có thể hành động. Aspose.Tasks hỗ trợ **hơn 50 loại bộ lọc được định nghĩa trước** và cho phép bạn xây dựng các bộ lọc tùy chỉnh không giới hạn, giảm thời gian lọc dữ liệu thủ công lên tới 70 %.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – version 8 hoặc mới hơn.  
2. **Aspose.Tasks for Java** – tải xuống từ [download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, hoặc NetBeans đều hoạt động tốt.  

## Nhập gói
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType`, và `Project` là các lớp cốt lõi được sử dụng để định nghĩa và áp dụng bộ lọc cho dữ liệu dự án.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập dự án
Đầu tiên, tạo một thể hiện `Project` trỏ tới tệp MPP bạn muốn phân tích, sau đó tải nó vào bộ nhớ. Bước duy nhất này chuẩn bị toàn bộ mô hình dự án cho việc lọc, xác thực và thao tác tiếp theo, cho phép bạn truy cập các công việc, nguồn lực và phân công thông qua API.

### Làm thế nào để thiết lập dự án để lọc tệp MPP?
Lớp `Project` tải và đại diện cho một tệp MPP trong bộ nhớ. Tạo một thể hiện `Project` trỏ tới tệp MPP bạn muốn phân tích, sau đó tải nó vào bộ nhớ. Bước duy nhất này chuẩn bị toàn bộ mô hình dự án cho việc lọc, xác thực và thao tác tiếp theo, cho phép bạn truy cập các công việc, nguồn lực và phân công thông qua API.

### Làm sao tôi có thể lấy và kiểm tra một bộ lọc?
Các đối tượng `Filter` bao gồm các định nghĩa bộ lọc được sử dụng để chọn các mục dự án. Aspose.Tasks lưu trữ các bộ lọc được định nghĩa trước như “All Tasks” hoặc “Critical Tasks”. Sử dụng `project.getTaskFilters().getByName("My Filter")` hoặc truy cập dựa trên chỉ mục để lấy một đối tượng `Filter`, sau đó kiểm tra bộ sưu tập `FilterCriteria` của nó để xem từng quy tắc và toán tử logic (AND/OR) kết hợp chúng, đảm bảo bộ lọc đáp ứng yêu cầu của bạn.

### Làm sao để lặp qua các hàng tiêu chí lồng nhau?
`FilterCriteriaGroup` đại diện cho một nhóm các tiêu chí lọc được kết hợp bằng một toán tử logic. Các bộ lọc có thể chứa các nhóm tiêu chí, mỗi nhóm có toán tử riêng. Lặp qua `filter.getCriteria().getRows()` và, đối với bất kỳ hàng nào là `FilterCriteriaGroup`, đệ quy vào các hàng con của nó. Việc duyệt này cho phép bạn hiểu đầy đủ logic bộ lọc phức tạp như “(Start < today AND Cost > 1000) OR Priority = High”, và điều chỉnh tiêu chí khi cần.

### Làm sao tôi in thông tin tiêu chí để gỡ lỗi?
Sau khi duyệt cây tiêu chí, xuất tên trường, toán tử kiểm tra và giá trị của mỗi hàng ra console. Lệnh dump đơn giản này giúp bạn xác minh rằng bộ lọc khớp với các quy tắc kinh doanh mong muốn trước khi áp dụng vào các dự án lớn, và giúp dễ dàng phát hiện các toán tử hoặc giá trị không đúng.

### Làm sao tôi tạo một bộ lọc mới hoàn toàn bằng chương trình?
Khởi tạo một `Filter` bằng `new Filter("My Filter")`, sau đó thêm nó vào bộ sưu tập bộ lọc công việc của dự án bằng `project.getTaskFilters().add(filter)`. Tiếp theo, điền bộ sưu tập `FilterCriteria` của nó với các hàng mong muốn, chỉ định tên trường, toán tử kiểm tra và giá trị để xác định chính xác các công việc sẽ được bao gồm khi bộ lọc được áp dụng.

### Tôi có thể áp dụng bộ lọc cho nguồn lực thay vì công việc không?
Bộ sưu tập `ResourceFilters` chứa các định nghĩa bộ lọc áp dụng cho nguồn lực. Có – sử dụng `project.getResourceFilters()` để làm việc với các bộ lọc riêng cho nguồn lực tương tự như bộ lọc công việc. Sau khi thêm hoặc lấy một bộ lọc, cấu hình `FilterCriteria` của nó giống như với công việc, sau đó áp dụng nó cho bộ sưu tập nguồn lực để nhận được tập hợp nguồn lực đã lọc.

### Có thể kết hợp nhiều bộ lọc với logic OR không?
Tạo một `FilterCriteriaGroup` cha với `Operation` được đặt là `OR`, sau đó thêm các đối tượng `FilterCriteria` riêng lẻ làm con. Nhóm này sẽ đánh giá mỗi tiêu chí con và trả về các mục thỏa mãn bất kỳ tiêu chí nào, cho phép bạn kết hợp nhiều bộ lọc đơn giản thành một lựa chọn rộng hơn.

### Aspose.Tasks có hỗ trợ lọc trên trường tùy chỉnh không?
`CustomField` enum cung cấp các định danh cho các trường tùy chỉnh được định nghĩa trong dự án. Chắc chắn. Tham chiếu các trường tùy chỉnh qua enum `CustomField`, và chúng hoạt động như bất kỳ trường tích hợp nào trong biểu thức bộ lọc. Bạn có thể đưa chúng vào các hàng `FilterCriteria`, sử dụng cùng các toán tử và giá trị, cho phép truy vấn mạnh mẽ trên dữ liệu do người dùng định nghĩa cùng với các thuộc tính dự án tiêu chuẩn.

### Lọc ảnh hưởng như thế nào đến hiệu suất trên các tệp MPP lớn?
Quá trình lọc chạy hoàn toàn trong bộ nhớ và thường xử lý một dự án 1.000 công việc trong dưới 200 ms. Đối với các tệp có hàng ngàn công việc, hãy cân nhắc chỉ tải các phần cần thiết bằng `ProjectReader` và áp dụng bộ lọc sau khi tải có chọn lọc, giúp giảm mức sử dụng bộ nhớ và duy trì thời gian phản hồi nhanh ngay cả trên các dự án rất lớn.

---

**Cập nhật lần cuối:** 2026-06-05  
**Được kiểm tra với:** Aspose.Tasks for Java 24.10  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Tải tệp MPP Java - Quản lý thuộc tính dự án với Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Đọc dữ liệu MS Project Online một cách dễ dàng](/tasks/java/project-data-reading/read-project-online/)
- [Đặt ngày bắt đầu dự án trong MS Project bằng Aspose.Tasks cho Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```