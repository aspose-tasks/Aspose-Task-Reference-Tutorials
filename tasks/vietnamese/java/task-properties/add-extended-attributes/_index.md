---
date: 2026-01-25
description: Tìm hiểu cách thêm thuộc tính vào các nhiệm vụ bằng Aspose.Tasks cho
  Java, tùy chỉnh các tệp Microsoft Project với các thuộc tính mở rộng để kiểm soát
  dự án tốt hơn.
linktitle: Add Extended Attributes to Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Thêm Thuộc Tính – Thêm Thuộc Tính Mở Rộng cho Các Nhiệm Vụ trong Aspose.Tasks
url: /vi/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Thuộc Tính – Thêm Thuộc Tính Mở Rộng cho Các Nhiệm Vụ trong Aspose.Tasks

## Giới thiệu
Nâng cao khả năng quản lý dự án của bạn là rất quan trọng để theo dõi nhiệm vụ và quản lý nguồn lực hiệu quả. Trong hướng dẫn này, **bạn sẽ học cách thêm thuộc tính** vào các nhiệm vụ với Aspose.Tasks cho Java, giúp bạn linh hoạt tùy chỉnh các tệp Microsoft Project theo nhu cầu cụ thể của tổ chức. Chúng tôi sẽ hướng dẫn toàn bộ quy trình từng bước, từ thiết lập môi trường đến lưu tệp dự án đã cập nhật.

## Câu trả lời nhanh
- **Mục đích chính là gì?** Thêm các thuộc tính tùy chỉnh (mở rộng) vào các nhiệm vụ trong tệp Microsoft Project.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks cho Java.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; cần giấy phép thương mại cho môi trường sản xuất.  
- **Tôi có thể thêm giá trị tra cứu không?** Có – bạn có thể tạo các thuộc tính văn bản hoặc thời lượng với danh sách tra cứu được định trước.  
- **Các định dạng tệp nào được hỗ trợ khi lưu?** MPP, XML và các định dạng khác được Aspose.Tasks hỗ trợ.

## Yêu cầu trước
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã có các yêu cầu sau:
- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Tasks cho Java đã được cài đặt. Bạn có thể tải xuống từ [website](https://releases.aspose.com/tasks/java/).  
- Một môi trường phát triển tích hợp Java (IDE) đã được cài đặt trên hệ thống của bạn.

## Nhập các gói
Trong dự án Java của bạn, nhập các gói cần thiết để truy cập các chức năng của Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```

Bây giờ, chúng ta sẽ phân tích từng ví dụ thành nhiều bước:

## Cách Thêm Thuộc Tính vào Nhiệm Vụ (Ví dụ Văn Bản Thuần)

### 1. Đặt Thư Mục Tài Liệu
Đầu tiên, xác định thư mục chứa tệp dự án nguồn của bạn:
```java
String dataDir = "Your Document Directory";
```

### 2. Tải Dự Án
Tạo một thể hiện `Project` trỏ tới tệp `.mpp` hiện có:
```java
Project project = new Project(dataDir + "project.mpp");
```

### 3. Định Nghĩa Thuộc Tính Mở Rộng Văn Bản Thuần
Tạo một định nghĩa thuộc tính loại **Text1** – sẽ lưu tên thành phố cho mỗi nhiệm vụ:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 4. Thêm Định Nghĩa vào Dự Án
Đăng ký định nghĩa mới vào bộ sưu tập các thuộc tính mở rộng của dự án:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 5. Tạo Nhiệm Vụ Mới
Thêm một nhiệm vụ con dưới nhiệm vụ gốc:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 6. Tạo Thực Thể Thuộc Tính Mở Rộng
Tạo một thực thể thuộc tính thực tế từ định nghĩa bạn đã tạo trước đó:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 7. Gán Giá Trị
Đặt giá trị cụ thể (ví dụ, thành phố “London”) cho thuộc tính mở rộng của nhiệm vụ này:
```java
taskExtendedAttributeText1.setTextValue("London");
```

### 8. Gắn Thuộc Tính vào Nhiệm Vụ
Thêm thuộc tính đã điền vào bộ sưu tập của nhiệm vụ:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

### 9. Lưu Dự Án Đã Cập Nhật
Cuối cùng, lưu các thay đổi vào một tệp mới để bạn có thể kiểm tra kết quả trong Microsoft Project:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Thêm Thuộc Tính Văn Bản với Tùy Chọn Tra Cứu
Để tạo một thuộc tính văn bản cung cấp danh sách giá trị được định trước (tra cứu), lặp lại các bước trên, nhưng thay thế `ExtendedAttributeTask.Text1` bằng `ExtendedAttributeTask.Text2` và điền bảng tra cứu bằng cách sử dụng `taskExtendedAttributeText2Definition.getLookupValues().add(...)`. Điều này cho phép người dùng chọn từ một tập hợp tùy chọn cố định khi chỉnh sửa nhiệm vụ.

## Thêm Thuộc Tính Thời Lượng với Tùy Chọn Tra Cứu
Tương tự, đối với thuộc tính dựa trên thời lượng, sử dụng `CustomFieldType.Duration` và `ExtendedAttributeTask.Duration2`. Điền các giá trị tra cứu với các khoảng thời gian cụ thể (ví dụ, “1 ngày”, “2 tuần”) để chuẩn hoá các mục thời lượng trong dự án của bạn.

## Tại Sao Nên Sử Dụng Thuộc Tính Mở Rộng?
- **Linh hoạt:** Lưu bất kỳ dữ liệu tùy chỉnh nào không được các trường mặc định của Project bao phủ.  
- **Chuẩn hoá:** Bảng tra cứu đảm bảo nhập dữ liệu nhất quán.  
- **Báo cáo:** Các trường tùy chỉnh có thể được đưa vào báo cáo và bộ lọc, cung cấp cho bạn những hiểu biết sâu hơn.

## Các Vấn Đề Thường Gặp & Khắc Phục
- **Đường dẫn không hợp lệ:** Đảm bảo `dataDir` kết thúc bằng dấu phân tách thư mục (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Ngoại lệ giấy phép:** Nếu không có giấy phép hợp lệ, thư viện sẽ chạy ở chế độ đánh giá và có thể thêm watermark.  
- **Tra cứu không hiển thị:** Sau khi định nghĩa các giá trị tra cứu, luôn thêm định nghĩa vào dự án trước khi tạo thuộc tính nhiệm vụ.

## Câu Hỏi Thường Gặp

### Hỏi: Tôi có thể sử dụng Aspose.Tasks cho Java cùng với các thư viện Java khác không?
Đ: Có, Aspose.Tasks cho Java có thể được tích hợp liền mạch vào các dự án Java của bạn và hoạt động tốt với các thư viện Java khác.

### Hỏi: Aspose.Tasks cho Java có phù hợp cho các ứng dụng quản lý dự án quy mô lớn không?
Đ: Chắc chắn, Aspose.Tasks cho Java được thiết kế để xử lý các dự án có kích thước khác nhau, bao gồm cả các ứng dụng quy mô lớn.

### Hỏi: Có những lưu ý nào về giấy phép khi sử dụng Aspose.Tasks cho Java trong dự án thương mại không?
Đ: Có, hãy chắc chắn xem xét thông tin giấy phép được cung cấp trên [trang web Aspose.Tasks](https://purchase.aspose.com/buy).

### Hỏi: Làm thế nào tôi có thể nhận hỗ trợ hoặc trợ giúp cho Aspose.Tasks cho Java?
Đ: Truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận hỗ trợ cộng đồng và thảo luận.

### Hỏi: Tôi có thể dùng thử Aspose.Tasks cho Java trước khi mua không?
Đ: Có, bạn có thể truy cập phiên bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Additional Q&A**

**Hỏi: Tôi có thể thêm nhiều thuộc tính mở rộng vào một nhiệm vụ duy nhất không?**  
**Đ: Có, chỉ cần tạo thêm các thực thể `ExtendedAttribute` và thêm mỗi thực thể vào bộ sưu tập `ExtendedAttributes` của nhiệm vụ.**

**Hỏi: Các giá trị tra cứu có hỗ trợ bản địa hoá không?**  
**Đ: Các giá trị tra cứu được lưu dưới dạng chuỗi thuần, vì vậy bạn có thể cung cấp văn bản đã bản địa hoá cho mỗi mục theo nhu cầu.**

## Kết Luận
Bằng cách làm theo hướng dẫn từng bước này, **bạn đã học cách thêm thuộc tính** vào các nhiệm vụ trong tệp Microsoft Project bằng Aspose.Tasks cho Java. Tùy chỉnh mạnh mẽ này cho phép bạn nắm bắt dữ liệu đặc thù của dự án, cải thiện báo cáo và duy trì tính nhất quán trong lịch trình của tổ chức.

---

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}