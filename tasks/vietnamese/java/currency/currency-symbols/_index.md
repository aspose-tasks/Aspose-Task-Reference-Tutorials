---
date: 2025-12-05
description: Tìm hiểu cách trích xuất ký hiệu tiền tệ mpp và thay đổi ký hiệu tiền
  tệ java bằng Aspose.Tasks cho Java. Nhanh chóng lấy ký hiệu tiền tệ java cho quản
  lý dự án.
language: vi
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Trích xuất ký hiệu tiền tệ mpp bằng Aspose.Tasks cho Java
url: /java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất ký hiệu tiền tệ mpp bằng Aspose.Tasks cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **extract currency symbol mpp** từ một tệp Microsoft Project và khám phá cách **change currency symbol java** hoặc **retrieve currency symbol java** bằng thư viện Aspose.Tasks. Cho dù bạn đang xây dựng công cụ báo cáo, tích hợp dữ liệu Project vào hệ thống tài chính, hoặc chỉ cần hiển thị ký hiệu tiền tệ đúng trong UI, việc nắm vững nhiệm vụ nhỏ nhưng quan trọng này sẽ làm cho các ứng dụng Java của bạn mạnh mẽ hơn và thân thiện với người dùng.

## Câu trả lời nhanh
- **What does “extract currency symbol mpp” mean?** Nó có nghĩa là đọc ký hiệu tiền tệ được lưu trong tệp MPP (Microsoft Project).  
- **Which library handles this?** Aspose.Tasks for Java cung cấp một API đơn giản cho công việc này.  
- **Do I need a license?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **How long does it take?** Với đoạn mã dưới đây, bạn có thể lấy ký hiệu trong chưa đầy một phút.  
- **Can I also change the symbol?** Có – bạn có thể đặt giá trị mới bằng cùng thuộc tính `Prj.CURRENCY_SYMBOL`.

## “extract currency symbol mpp” là gì?
Microsoft Project lưu ký hiệu tiền tệ (ví dụ: $, €, £) trong phần đầu của tệp dự án. Thao tác **extract currency symbol mpp** đọc giá trị đó để bạn có thể hiển thị hoặc thao tác nó bằng chương trình.

## Tại sao change currency symbol java?
Các dự án thường trải qua nhiều khu vực. Khả năng **change currency symbol java** tại thời gian chạy cho phép bạn điều chỉnh báo cáo, hoá đơn hoặc bảng điều khiển cho thị trường địa phương mà không cần tạo lại toàn bộ tệp dự án.

## Các yêu cầu trước
1. **Java Development Kit (JDK)** – phiên bản 8 trở lên.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ [trang tải Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Một tệp **project.mpp** hợp lệ được đặt trong thư mục bạn có thể tham chiếu từ mã của mình.

## Nhập các gói
Đầu tiên, nhập các lớp chúng ta sẽ cần để làm việc với các tệp Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Bước 1: Định nghĩa Thư mục Dữ liệu
Cho ứng dụng biết tệp *.mpp* của bạn nằm ở đâu.

```java
String dataDir = "Your Data Directory";
```

> **Mẹo:** Sử dụng `System.getProperty("user.dir")` để xây dựng đường dẫn tuyệt đối hoạt động trên bất kỳ máy nào.

## Bước 2: Tải tệp MS Project
Tạo một đối tượng `Project` đại diện cho tệp MPP trong bộ nhớ.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Bước 3: Lấy (và tùy chọn thay đổi) Ký hiệu Tiền tệ
Bây giờ chúng ta **retrieve currency symbol java** bằng cách đọc thuộc tính `Prj.CURRENCY_SYMBOL`. Bạn cũng có thể **change currency symbol java** bằng cách gán một chuỗi mới cho cùng thuộc tính.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Lệnh `System.out.println` sẽ in ký hiệu (ví dụ, `$`) ra console, xác nhận việc trích xuất đã thành công.

## Các vấn đề thường gặp & cách khắc phục
| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | Đường dẫn tệp sai hoặc không tìm thấy tệp | Xác minh `dataDir` và tên tệp; sử dụng `new File(dataDir).exists()` để gỡ lỗi |
| Unexpected symbol (e.g., `?`) | Dự án được tạo với locale không chuẩn | Đảm bảo tệp MPP nguồn thực sự định nghĩa ký hiệu tiền tệ; bạn có thể đặt một ký hiệu bằng chương trình như đã trình bày ở trên |
| License error | Sử dụng bản dùng thử mà không có tệp giấy phép hợp lệ | Tải giấy phép của bạn bằng `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` trước khi tạo đối tượng `Project` |

## Câu hỏi thường gặp

**Q: Tôi có thể thao tác các thuộc tính dự án khác ngoài ký hiệu tiền tệ bằng Aspose.Tasks không?**  
A: Có, Aspose.Tasks cho phép bạn chỉnh sửa nhiệm vụ, nguồn lực, phân công, lịch, và nhiều thuộc tính dự án khác.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp MS Project khác nhau không?**  
A: Hoàn toàn. Nó hỗ trợ các định dạng MPP, MPT và XML từ Project 98 đến các phiên bản mới nhất.

**Q: Aspose.Tasks có cung cấp tài liệu và hỗ trợ cho nhà phát triển không?**  
A: Tài liệu API toàn diện, ví dụ mã, và diễn đàn hỗ trợ chuyên dụng có sẵn trên trang web Aspose.Tasks.

**Q: Tôi có thể dùng thử Aspose.Tasks trước khi mua không?**  
A: Có – bản dùng thử đầy đủ chức năng có thể tải xuống từ [trang web Aspose](https://purchase.aspose.com/buy).

**Q: Làm thế nào tôi có thể nhận giấy phép tạm thời cho Aspose.Tasks?**  
A: Giấy phép tạm thời được cung cấp trên [trang giấy phép tạm thời của Aspose](https://purchase.aspose.com/temporary-license/) để đánh giá.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}