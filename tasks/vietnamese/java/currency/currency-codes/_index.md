---
date: 2025-12-09
description: Học cách đọc tệp MS Project và quản lý mã tiền tệ một cách hiệu quả bằng
  Aspose.Tasks cho Java. Tối ưu hoá các nhiệm vụ quản lý dự án của bạn một cách dễ
  dàng.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách đọc tệp MS Project và quản lý mã tiền tệ với Aspose.Tasks
url: /vi/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc tệp MS Project và quản lý mã tiền tệ với Aspose.Tasks

## Giới thiệu
Chào mừng! Trong hướng dẫn này, bạn sẽ khám phá **cách đọc dữ liệu tệp MS Project** và cụ thể là **quản lý mã tiền tệ** bằng API Aspose.Tasks cho Java. Dù bạn đang tạo báo cáo, hợp nhất các dự án đa tiền tệ, hay chỉ cần đảm bảo các ký hiệu tài chính hiển thị đúng, hướng dẫn này sẽ dẫn bạn qua từng bước — từ thiết lập môi trường đến việc lấy mã tiền tệ một cách lập trình. Khi hoàn thành, bạn sẽ tự tin đọc các tệp MS Project và trích xuất thông tin tiền tệ mà bạn cần.

## Câu trả lời nhanh
- **API làm gì?** Nó đọc các tệp MS Project và cung cấp các thuộc tính như mã tiền tệ.  
- **Ngôn ngữ nào được sử dụng?** Java, thông qua thư viện Aspose.Tasks cho Java.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể lấy mã trong một dòng không?** Có—`prj.get(Prj.CURRENCY_CODE)` trả về chuỗi mã tiền tệ.  
- **Có tương thích với mọi phiên bản Project không?** Aspose.Tasks hỗ trợ cả định dạng cũ (MPP) và mới (XML, XER).

## **read ms project file** là gì?
Đọc một tệp MS Project có nghĩa là mở một tài liệu dự án *.mpp* (hoặc các định dạng được hỗ trợ khác) một cách lập trình và truy cập vào các cấu trúc dữ liệu của nó — nhiệm vụ, nguồn lực, lịch, và các cài đặt tài chính — mà không cần tương tác thủ công với Microsoft Project.

## Tại sao sử dụng Aspose.Tasks để **đọc msproject**?
- **Hỗ trợ đầy đủ định dạng** – hoạt động với các tệp từ Project 98 đến các phiên bản Office mới nhất.  
- **Không cần cài COM hay Office** – thuần Java, lý tưởng cho tự động hoá phía máy chủ.  
- **API phong phú** – cung cấp truy cập trực tiếp tới các thuộc tính như `Prj.CURRENCY_CODE`, cho phép bạn **cách lấy thông tin tiền tệ** ngay lập tức.  
- **Hiệu năng** – phân tích nhẹ, lý tưởng cho xử lý hàng loạt nhiều dự án.

## Yêu cầu trước
Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có những thứ sau:

### Java Development Kit (JDK) đã được cài đặt
Đảm bảo máy của bạn có một JDK mới. Bạn có thể tải và cài đặt phiên bản JDK mới nhất từ [đây](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Thư viện Aspose.Tasks cho Java
Tải và thiết lập thư viện Aspose.Tasks cho Java. Tài liệu chi tiết và các binary mới nhất có sẵn [tại đây](https://reference.aspose.com/tasks/java/).

## Nhập các gói
Để bắt đầu, hãy nhập các gói cần thiết trong dự án Java của bạn:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập thư mục dữ liệu
Xác định thư mục chứa tệp *.mpp* của bạn. Điều chỉnh đường dẫn cho phù hợp với môi trường của bạn.
```java
String dataDir = "Your Data Directory";
```

### Bước 2: Tải tệp dự án
Tạo một thể hiện `Project` bằng cách tải tệp MS Project. Đây là điểm mà bạn **đọc msproject** dữ liệu vào bộ nhớ.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Bước 3: Lấy mã tiền tệ
Bây giờ dự án đã được tải, bạn có thể **cách lấy thông tin tiền tệ** chỉ bằng một lời gọi. Điều này minh họa cách sử dụng **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Kết quả sẽ là mã tiền tệ ISO ba chữ cái (ví dụ: `USD`, `EUR`, `GBP`) mà dự án được cấu hình để sử dụng.

### Bước 4: (Tùy chọn) Sử dụng mã tiền tệ
Bạn có thể muốn áp dụng mã đã lấy ở nơi khác — chẳng hạn như định dạng giá trị chi phí trong báo cáo tùy chỉnh hoặc truyền nó tới một API tài chính. Dưới đây là một minh họa nhanh (không cần khối mã bổ sung):
- Lưu mã vào một biến.  
- Sử dụng nó khi tạo chuỗi tiền tệ.  
- Truyền nó tới các dịch vụ hạ nguồn yêu cầu định danh tiền tệ.

## Vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **Kết quả null** | Tệp dự án không xác định tiền tệ (mặc định là rỗng). | Đặt tiền tệ trong Microsoft Project hoặc gán nó bằng `prj.set(Prj.CURRENCY_CODE, "USD");` trước khi đọc. |
| **Không tìm thấy tệp** | Đường dẫn `dataDir` không đúng. | Kiểm tra lại đường dẫn và đảm bảo tên tệp khớp chính xác, bao gồm cả phân biệt chữ hoa/thường. |
| **Phiên bản tệp không được hỗ trợ** | Tệp *.mpp* quá cũ hoặc bị hỏng. | Sử dụng phiên bản Aspose.Tasks mới nhất hoặc chuyển đổi tệp sang định dạng mới hơn trong Microsoft Project trước. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể xử lý cấu trúc dự án phức tạp không?**  
A: Có, API có thể đọc và thao tác các cây nhiệm vụ đa cấp, nhóm nguồn lực, và các trường tùy chỉnh mà không gặp vấn đề.

**Q: Aspose.Tasks có tương thích với các phiên bản tệp MS Project khác nhau không?**  
A: Hoàn toàn. Nó hỗ trợ MPP, XML, XER và các định dạng khác trên nhiều phiên bản Microsoft Project.

**Q: Aspose.Tasks có cung cấp tài liệu và hỗ trợ không?**  
A: Tài liệu chi tiết, ví dụ mã, và hỗ trợ chuyên dụng đều có trên trang web Aspose.

**Q: Tôi có thể thử Aspose.Tasks trước khi mua không?**  
A: Bản dùng thử miễn phí được cung cấp để bạn đánh giá tất cả các tính năng, bao gồm việc đọc mã tiền tệ.

**Q: Tôi có thể lấy giấy phép tạm thời cho Aspose.Tasks ở đâu?**  
A: Giấy phép tạm thời có thể được lấy từ [website](https://purchase.aspose.com/temporary-license/) cho việc đánh giá ngắn hạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2025-12-09  
**Kiểm thử với:** Aspose.Tasks for Java (latest version)  
**Tác giả:** Aspose