---
date: 2025-12-05
description: Tìm hiểu cách xử lý các chữ số tiền tệ trong MS Project một cách hiệu
  quả bằng Aspose.Tasks cho Java. Hướng dẫn từng bước bao gồm việc xử lý tệp dự án
  Java và cách tải các tệp MPP.
language: vi
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Xử lý các chữ số tiền tệ trong MS Project bằng Aspose.Tasks
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xử lý chữ số tiền tệ trong MS Project với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn toàn diện này, bạn sẽ khám phá **cách làm việc với giá trị tiền tệ của ms project** bằng thư viện Aspose.Tasks cho Java. Dù bạn đang xây dựng một công cụ báo cáo, một tiện ích di chuyển dữ liệu, hay chỉ cần đọc cài đặt tiền tệ từ một **tệp dự án java**, hướng dẫn này sẽ dẫn bạn qua mọi bước — từ việc tải tệp *.mpp* đến việc trích xuất chữ số tiền tệ. Khi hoàn thành, bạn sẽ tự tin xử lý dữ liệu tiền tệ của ms project trong các ứng dụng của mình.

## Câu trả lời nhanh
- **Thư viện nào đọc file MS Project?** Aspose.Tasks for Java.  
- **Cần bao nhiêu dòng code để lấy chữ số tiền tệ?** Chỉ ba dòng ngắn gọn sau khi dự án được tải.  
- **Có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn (bất kỳ JDK nào chạy Aspose.Tasks).  
- **Tôi có thể lấy các thuộc tính khác của Project không?** Có – Aspose.Tasks cung cấp đầy đủ các trường của Project (ví dụ: ngày bắt đầu, tỷ lệ chi phí, v.v.).

## ms project currency là gì?
`ms project currency` đề cập đến độ chính xác số (số chữ số thập phân) mà Microsoft Project sử dụng khi hiển thị các giá trị tiền tệ. Nó được lưu trong tệp Project dưới dạng thuộc tính **CURRENCY_DIGITS** và quyết định liệu các khoản tiền hiển thị dưới dạng số nguyên, một chữ số thập phân, hai chữ số thập phân, v.v.

## Tại sao nên sử dụng Aspose.Tasks để xử lý ms project currency?
- **Không cần cài đặt Microsoft Project** – làm việc trực tiếp với các tệp *.mpp* trên bất kỳ nền tảng nào hỗ trợ Java.  
- **An toàn kiểu dữ liệu mạnh** – API trả về các giá trị có kiểu mạnh, giảm lỗi phân tích.  
- **Tối ưu hiệu năng** – tải các dự án lớn nhanh chóng và chỉ trích xuất các trường cần thiết.  
- **Đa nền tảng** – chạy trên Windows, Linux hoặc macOS mà không cần chỉnh sửa.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn bạn có những thứ sau:

1. **Môi trường phát triển Java** – JDK 8 hoặc mới hơn đã được cài đặt và cấu hình.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ trang chính thức: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Kiến thức cơ bản về Java** – bạn nên thoải mái tạo một dự án Java, thêm thư viện bên ngoài và chạy một phương thức `main`.

## Nhập các gói
Đầu tiên, nhập các lớp cần thiết.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Bước 1: Xác định thư mục dữ liệu
Xác định thư mục chứa **tệp dự án java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối hoặc tương đối nơi `project.mpp` nằm.

## Bước 2: Tải tệp MPP
Bây giờ chúng ta sẽ xem **cách tải tệp mpp** bằng Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Đảm bảo tên tệp khớp chính xác; nếu không, sẽ ném ra một `IOException`.

## Bước 3: Lấy chữ số tiền tệ
Khi dự án đã được tải, việc trích xuất chữ số **ms project currency** chỉ cần một dòng lệnh:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Lệnh này trả về một `Integer` biểu thị số chữ số thập phân (ví dụ, `2` cho cent). Giá trị được in ra console, nhưng bạn cũng có thể lưu vào biến để xử lý tiếp.

## Các vấn đề thường gặp & Mẹo
- **File không tìm thấy** – kiểm tra lại đường dẫn `dataDir` và đảm bảo tên tệp đúng, bao gồm phần mở rộng `.mpp`.  
- **Phiên bản tệp không được hỗ trợ** – Aspose.Tasks hỗ trợ các định dạng Project 2000‑2024; các tệp cũ hơn hoặc bị hỏng có thể cần chuyển đổi.  
- **Chưa đặt giấy phép** – trong quá trình phát triển bản dùng thử hoạt động, nhưng trong môi trường sản xuất bạn phải áp dụng giấy phép hợp lệ để tránh dấu nước đánh giá.

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể xử lý các thuộc tính khác của Project ngoài chữ số tiền tệ không?**  
A: Có, Aspose.Tasks cung cấp nhiều chức năng để thao tác các khía cạnh khác nhau của tệp Project, chẳng hạn như nhiệm vụ, nguồn lực và trường tùy chỉnh.

**Q: Aspose.Tasks có phù hợp cho các ứng dụng cấp doanh nghiệp không?**  
A: Chắc chắn, Aspose.Tasks được thiết kế để đáp ứng yêu cầu của các dự án cấp doanh nghiệp, cung cấp hiệu năng cao và khả năng mở rộng.

**Q: Aspose.Tasks có hỗ trợ phát triển đa nền tảng không?**  
A: Có, bạn có thể sử dụng Aspose.Tasks cho Java trên bất kỳ nền tảng nào hỗ trợ Java Runtime Environment (Windows, Linux, macOS).

**Q: Tôi có thể dùng thử trước khi mua không?**  
A: Có, bạn có thể tải phiên bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

**Q: Tôi có thể nhận hỗ trợ cho Aspose.Tasks ở đâu?**  
A: Bạn có thể tìm hỗ trợ trên [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2025-12-05  
**Kiểm tra với:** Aspose.Tasks for Java 24.11 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}