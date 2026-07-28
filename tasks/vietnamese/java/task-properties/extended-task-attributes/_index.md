---
date: 2026-01-28
description: Tìm hiểu cách đọc các thuộc tính nhiệm vụ mở rộng bằng Aspose.Tasks cho
  Java và chuyển đổi loại trường tùy chỉnh một cách hiệu quả.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Đọc các thuộc tính nhiệm vụ mở rộng với Aspose.Tasks cho Java
url: /vi/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Thuộc Tính Nhiệm Vụ Mở Rộng với Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn toàn diện này, bạn sẽ khám phá cách **đọc các thuộc tính nhiệm vụ mở rộng** từ các tệp Microsoft Project bằng thư viện Aspose.Tasks cho Java. Dù bạn đang xây dựng công cụ báo cáo, đồng bộ dữ liệu, hay chỉ cần hiểu sâu hơn về các trường tùy chỉnh, việc thành thạo tính năng này sẽ cho phép bạn trích xuất mọi thông tin được lưu trữ trong một dự án. Chúng tôi sẽ hướng dẫn cách cài đặt cần thiết, chỉ cho bạn cách **chuyển đổi kiểu trường tùy chỉnh** khi xử lý thuộc tính, và cung cấp các mẹo thực tế để tránh những lỗi thường gặp.

## Câu trả lời nhanh
- **“Đọc thuộc tính nhiệm vụ mở rộng” có nghĩa là gì?** Nó đề cập đến việc trích xuất giá trị các trường tùy chỉnh vượt ra ngoài các thuộc tính mặc định của nhiệm vụ trong tệp Project.  
- **Lớp nào cung cấp quyền truy cập vào các thuộc tính này?** Lớp `ExtendedAttribute` trong Aspose.Tasks.  
- **Tôi có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi kiểu thuộc tính tại thời gian chạy không?** Có – sử dụng câu lệnh `switch` để **chuyển đổi kiểu trường tùy chỉnh** dựa trên `CustomFieldType`.  
- **Điều này có tương thích với Java 8 trở lên không?** Hoàn toàn, API hỗ trợ JDK 8+.

## Thuộc tính nhiệm vụ mở rộng là gì?
Các thuộc tính nhiệm vụ mở rộng là các trường do người dùng định nghĩa (văn bản, ngày, số, cờ, v.v.) bổ sung cho các thuộc tính tiêu chuẩn của nhiệm vụ trong Microsoft Project. Aspose.Tasks cung cấp chúng thông qua bộ sưu tập `ExtendedAttribute` gắn vào mỗi đối tượng `Task`, cho phép bạn đọc hoặc sửa đổi giá trị của chúng một cách lập trình.

## Tại sao cần đọc thuộc tính nhiệm vụ mở rộng?
- **Tầm nhìn toàn diện:** Nắm bắt dữ liệu tùy chỉnh mà các bên liên quan đã thêm vào lịch trình.  
- **Tự động hoá:** Điền vào bảng điều khiển, tạo báo cáo tùy chỉnh, hoặc di chuyển dữ liệu sang hệ thống khác mà không cần xuất thủ công.  
- **Linh hoạt:** Làm việc với bất kỳ kiểu trường tùy chỉnh nào—văn bản, ngày, thời lượng, chi phí, cờ—bằng cách xử lý từng trường hợp một cách thích hợp.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:
- Kiến thức cơ bản về lập trình Java.  
- Java Development Kit (JDK) đã được cài đặt trên máy tính.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.  

## Nhập gói
Bắt đầu bằng cách nhập các lớp cần thiết cho dự án Aspose.Tasks:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Bước 1: Truy cập Nhiệm vụ và Thuộc tính Mở rộng
Tải tệp Project và lặp qua mỗi nhiệm vụ để lấy các thuộc tính mở rộng của chúng:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Bước 2: Lấy ID Trường và GUID Giá trị
In ra các định danh nội bộ giúp bạn hiểu trường tùy chỉnh nào đang được xử lý:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Bước 3: Cách chuyển đổi kiểu trường tùy chỉnh khi đọc thuộc tính nhiệm vụ mở rộng
Sử dụng câu lệnh `switch` trên `CustomFieldType` để xử lý đúng mỗi kiểu dữ liệu có thể:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Lặp lại các bước này cho mỗi nhiệm vụ trong dự án của bạn để khám phá và thao tác mọi thuộc tính nhiệm vụ mở rộng.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Giá trị null được trả về** | Xác minh rằng trường tùy chỉnh thực sự đã được điền trong tệp .mpp nguồn. |
| **Kiểu hiển thị không đúng** | Đảm bảo bạn đang sử dụng `CustomFieldType` chính xác trong câu lệnh `switch`; kiểu không khớp sẽ gây ra giá trị mặc định. |
| **Hiệu năng chậm trên dự án lớn** | Xử lý nhiệm vụ theo lô hoặc lọc chỉ những nhiệm vụ cần thiết bằng cách sử dụng `project.getRootTask().getChildren().stream()` với các predicate phù hợp. |

## Câu hỏi thường gặp
### Tôi có thể sửa đổi thuộc tính nhiệm vụ mở rộng bằng lập trình không?
Có, bạn có thể sửa đổi các thuộc tính nhiệm vụ mở rộng bằng Aspose.Tasks cho Java. Tham khảo tài liệu để biết hướng dẫn chi tiết.

### Có phiên bản dùng thử không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Tôi có thể tìm hỗ trợ cho Aspose.Tasks cho Java ở đâu?
Để được hỗ trợ, hãy truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Làm sao để lấy giấy phép tạm thời?
Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể mua phiên bản đầy đủ của Aspose.Tasks cho Java ở đâu?
Bạn có thể mua phiên bản đầy đủ [tại đây](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2026-01-28  
**Đã kiểm tra với:** Aspose.Tasks Java API (phiên bản ổn định mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}