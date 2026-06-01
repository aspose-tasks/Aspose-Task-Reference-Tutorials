---
date: 2026-01-13
description: Tìm hiểu cách tạo thuộc tính tùy chỉnh, tải tệp Microsoft Project, đặt
  giá trị số trong Java và lưu dự án dưới dạng XML bằng Aspose.Tasks cho Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách tạo thuộc tính tùy chỉnh trong MS Project bằng Aspose.Tasks
url: /vi/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Thuộc Tính Tùy Chỉnh trong MS Project bằng Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, **bạn sẽ khám phá cách tạo thuộc tính tùy chỉnh** cho tài nguyên trong tệp Microsoft Project bằng Aspose.Tasks cho Java. Chúng ta sẽ thực hiện các bước tải tệp Microsoft Project, định nghĩa một thuộc tính số mới, gán giá trị, và cuối cùng lưu dự án dưới dạng XML. Khi hoàn thành, bạn sẽ có một ví dụ thực tế, dễ hiểu để áp dụng cho các giải pháp quản lý dự án của mình.

## Câu trả lời nhanh
- **“Thuộc tính tùy chỉnh” là gì?**  
  Một trường do người dùng định nghĩa để lưu trữ thông tin bổ sung (ví dụ: Tuổi, Trình độ kỹ năng) cho tài nguyên hoặc công việc.  
- **Thư viện nào thực hiện việc này?**  
  Aspose.Tasks cho Java cung cấp API linh hoạt để tạo và quản lý thuộc tính tùy chỉnh.  
- **Có cần giấy phép không?**  
  Giấy phép tạm thời miễn phí đủ cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Có thể đặt giá trị số không?**  
  Có – sử dụng `setNumericValue` cùng với `BigDecimal` (ví dụ: `30.5345`).  
- **Dự án được lưu như thế nào?**  
  Tệp đã chỉnh sửa có thể được lưu dưới dạng XML bằng `SaveFileFormat.Xml`.

## Thuộc tính tùy chỉnh là gì?
Một **thuộc tính tùy chỉnh** (còn gọi là thuộc tính mở rộng) là một cột bổ sung mà bạn có thể thêm vào tài nguyên hoặc công việc trong Microsoft Project. Nó cho phép bạn ghi lại dữ liệu không có trong các trường mặc định, chẳng hạn như tuổi nhân viên, mức chứng chỉ, hoặc bất kỳ chỉ số kinh doanh nào khác.

## Tại sao nên tạo thuộc tính tùy chỉnh trong MS Project?
- **Điều chỉnh dữ liệu dự án** cho phù hợp với nhu cầu của tổ chức.  
- **Kích hoạt báo cáo nâng cao** bằng cách lưu trữ các giá trị có thể truy vấn sau này.  
- **Duy trì tính nhất quán** giữa nhiều dự án bằng cách áp dụng cùng một định nghĩa thuộc tính một cách tự động.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Môi trường phát triển Java** – JDK 8 trở lên đã được cài đặt.  
2. **Aspose.Tasks cho Java** – Tải phiên bản mới nhất từ [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA, hoặc bất kỳ IDE nào hỗ trợ Java.  

## Hướng dẫn chi tiết

### Nhập gói
Đầu tiên, nhập các lớp Aspose.Tasks cần thiết. Những lớp này cung cấp chức năng cốt lõi để xử lý dự án, tài nguyên và thuộc tính mở rộng.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Bước 1: Xác định thư mục dữ liệu
Đặt thư mục chứa tệp dự án nguồn và nơi sẽ ghi ra kết quả.

```java
String dataDir = "Your Data Directory";
```

### Bước 2: Tải tệp Microsoft Project
Tạo một thể hiện `Project` bằng cách tải tệp hiện có. Đây là bước **load Microsoft project file** cho phép bạn truy cập toàn bộ nội dung của nó.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Bước 3: Định nghĩa thuộc tính tùy chỉnh
Chúng ta sẽ định nghĩa một thuộc tính số mới có tên **Age**. API sẽ kiểm tra xem định nghĩa đã tồn tại chưa; nếu chưa, nó sẽ tạo mới.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Bước 4: Đặt giá trị số trong Java
Tạo một thể hiện của thuộc tính cho một tài nguyên cụ thể và gán giá trị số bằng `setNumericValue`. Điều này minh họa **set numeric value java** trong thực tế.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Bước 5: Thêm tài nguyên và gắn thuộc tính tùy chỉnh
Thêm một tài nguyên mới có tên **R1** và gắn thuộc tính tùy chỉnh đã tạo ở bước trước vào nó.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Bước 6: Lưu dự án dưới dạng XML
Cuối cùng, lưu các thay đổi bằng cách lưu dự án. Đây là bước **save project as xml**, tạo ra một bản XML sạch sẽ của tệp đã cập nhật.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Bước 7: Hiển thị kết quả
In ra một thông báo xác nhận để bạn biết quá trình đã hoàn thành mà không có lỗi.

```java
System.out.println("Process completed Successfully");
```

Bằng cách thực hiện các bước trên, bạn đã **tạo thành công một thuộc tính tùy chỉnh**, tải tệp Microsoft Project, đặt giá trị số bằng Java, và lưu dự án dưới dạng XML.

## Những lỗi thường gặp & Mẹo
- **Xung đột ID thuộc tính:** Luôn kiểm tra `getById` trước khi tạo định nghĩa mới để tránh trùng lặp ID.  
- **Xử lý độ chính xác:** `BigDecimal` giữ nguyên độ chính xác thập phân; tránh dùng `float` hoặc `double` cho các giá trị cần độ chính xác cao.  
- **Đường dẫn tệp:** Sử dụng đường dẫn tuyệt đối hoặc cấu hình thư mục làm việc của IDE để tránh `FileNotFoundException`.  

## Câu hỏi thường gặp

**H: Có thể tạo thuộc tính tùy chỉnh cho công việc cũng như tài nguyên không?**  
Đ: Có – dùng `ExtendedAttributeTask` thay vì `ExtendedAttributeResource` khi định nghĩa thuộc tính.

**H: Có thể thêm nhiều thuộc tính tùy chỉnh cùng lúc không?**  
Đ: Chắc chắn. Tạo các đối tượng `ExtendedAttributeDefinition` riêng biệt cho mỗi thuộc tính và gắn chúng vào tài nguyên hoặc công việc mong muốn.

**H: Tôi có thể lưu dự án ở những định dạng nào?**  
Đ: Aspose.Tasks hỗ trợ XML, MPP và một số định dạng khác như PDF và HTML. Trong ví dụ này chúng ta dùng `SaveFileFormat.Xml`.

**H: Tôi có cần giấy phép Aspose.Tasks cho các bản build phát triển không?**  
Đ: Giấy phép tạm thời đủ cho việc đánh giá. Đối với triển khai sản xuất, cần giấy phép đầy đủ.

**H: Làm sao đọc lại giá trị thuộc tính tùy chỉnh sau này?**  
Đ: Dùng `resource.getExtendedAttributes()` để duyệt các thuộc tính đã gắn và lấy giá trị bằng `getNumericValue()` hoặc `getTextValue()`.

## Kết luận
Việc tạo **thuộc tính tùy chỉnh** trong Microsoft Project bằng Aspose.Tasks cho Java trở nên đơn giản khi bạn nắm rõ quy trình: tải dự án, định nghĩa thuộc tính, đặt giá trị, gắn vào tài nguyên, và lưu tệp. Cách tiếp cận này cho phép bạn mở rộng mô hình dữ liệu dự án một cách lập trình, hỗ trợ báo cáo phong phú hơn và tích hợp chặt chẽ hơn với quy trình kinh doanh của bạn.

---

**Cập nhật lần cuối:** 2026-01-13  
**Đã kiểm tra với:** Aspose.Tasks cho Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}