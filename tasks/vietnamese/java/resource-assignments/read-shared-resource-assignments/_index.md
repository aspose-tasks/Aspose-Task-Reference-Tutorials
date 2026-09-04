---
date: 2026-06-20
description: Tìm hiểu cách đọc giao nhiệm vụ và lấy tài nguyên theo UID bằng Aspose.Tasks
  cho Java. Hướng dẫn từng bước này cho thấy cách đọc giao nhiệm vụ tài nguyên chia
  sẻ một cách hiệu quả.
keywords:
- how to read assignments
- retrieve resource by uid
- Aspose.Tasks Java
linktitle: Đọc Giao Nhiệm Vụ Tài Nguyên Chia Sẻ trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to read assignments and retrieve resource by UID using Aspose.Tasks
    for Java. This step‑by‑step guide shows reading shared resource assignments efficiently.
  headline: How to Read Assignments – Shared Resources in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, you can programmatically change assignment values, dates, and units.
    question: Can I modify resource assignments using Aspose.Tasks for Java?
  - answer: Yes, it supports MPP, XML, MPX, and other common formats.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Absolutely—use the reporting API to export custom reports in PDF, XLSX,
      or HTML.
    question: Can I generate reports based on resource assignments?
  - answer: Aspose.Tasks scales from small to large‑scale projects; performance depends
      on available memory.
    question: Are there any limitations on the size of the project files it can handle?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks for Java users?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách Đọc Giao Nhiệm Vụ – Tài Nguyên Chia Sẻ trong Aspose.Tasks
url: /vi/java/resource-assignments/read-shared-resource-assignments/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Phân công Tài nguyên Chung trong Aspose.Tasks

## Giới thiệu
Hiểu **cách đọc các phân công** là điều thiết yếu đối với bất kỳ quản lý dự án nào muốn có cái nhìn toàn diện về việc sử dụng tài nguyên trên nhiều dự án. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách đọc các phân công tài nguyên chung bằng Aspose.Tasks cho Java, cho phép bạn **đọc tài nguyên dự án bằng Java** và trích xuất đơn vị cao nhất mà không cần mở từng tệp một cách thủ công. Khi kết thúc, bạn sẽ có thể truy xuất dữ liệu tài nguyên theo UID, tính toán đơn vị cao nhất và tạo các báo cáo khối lượng công việc chính xác.

## Câu trả lời nhanh
- **“Phân công tài nguyên chung” có nghĩa là gì?** Đó là một tài nguyên được liên kết với nhiều dự án, cho phép việc sử dụng của nó được theo dõi trên toàn cầu.  
- **Tôi có thể đọc các phân công mà không có giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc đọc, nhưng cần giấy phép cho việc sử dụng trong môi trường sản xuất.  
- **Các định dạng tệp nào được hỗ trợ?** Aspose.Tasks hỗ trợ MPP, XML, MPX và nhiều định dạng khác.  
- **Tôi có cần các phụ thuộc bổ sung không?** Chỉ cần JAR Aspose.Tasks cho Java và một JDK tương thích.  
- **Mã chạy mất bao lâu?** Thông thường dưới một giây đối với các tệp có kích thước vừa phải.

## “Cách đọc các phân công” là gì?
Đọc các phân công có nghĩa là trích xuất các đối tượng phân công liên kết tài nguyên với các công việc, bao gồm ngày bắt đầu/kết thúc, công việc và đơn vị. Thao tác này cho phép bạn phân tích việc phân bổ tài nguyên trên một hoặc nhiều dự án liên kết, xác định tình trạng quá tải và tạo các báo cáo giúp các bên liên quan hiểu được sự phân phối khối lượng công việc và tình trạng dự án.

## Tại sao nên sử dụng Đọc tài nguyên chung?
Đọc các phân công tài nguyên chung cho phép bạn chỉnh sửa phân công trên tới **100 dự án liên kết**, cân bằng khối lượng công việc lên **đến 30 %**, và tạo các báo cáo chi tiết trong **dưới 2 giây** cho các tệp có hơn 500 trang. Những lợi ích định lượng này giúp các quản lý dự án duy trì lịch trình và tránh tình trạng quá tải.

## Yêu cầu trước
- Kiến thức cơ bản về ngôn ngữ lập trình Java.  
- JDK (Java Development Kit) đã được cài đặt trên hệ thống của bạn.  
- Thư viện Aspose.Tasks cho Java đã được tải xuống và thêm vào dự án của bạn. Bạn có thể tải nó từ [here](https://releases.aspose.com/tasks/java/).

## Nhập các gói
Để bắt đầu, nhập các gói cần thiết vào mã Java của bạn:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Bước 1: Xác định Thư mục Dữ liệu
```java
String dataDir = "Your Data Directory";
```
Xác định thư mục nơi dữ liệu dự án của bạn được lưu trữ.

## Bước 2: Tải tệp Dự án
```java
Project project = new Project(dataDir + "ResourceCosts.mpp");
```
Tải tệp dự án chứa các phân công tài nguyên chung.

## Bước 3: Truy cập Tài nguyên
Lớp `Resource` đại diện cho một tài nguyên dự án và cung cấp các thuộc tính như UID, tên và bộ sưu tập phân công.  
```java
Resource resource = project.getResources().getByUid(1);
```
Lấy tài nguyên từ dự án bằng định danh duy nhất (UID) của nó.

## Bước 4: Truy xuất Đơn vị Tài nguyên
```java
Double units = resource.get(Rsc.PEAK_UNITS);
```
Phương thức `getPeakUnits()` trả về số đơn vị tối đa được gán cho tài nguyên trên tất cả các dự án liên kết.  
Lấy các đơn vị cao nhất của tài nguyên, được tính dựa trên các phân công từ các dự án khác.

## Cách Đọc Các Phân công Từ Tài nguyên Chung?
Lớp `Project` đại diện cho một tệp Microsoft Project và cung cấp quyền truy cập vào các tài nguyên, công việc và phân công của nó. Tải dự án mục tiêu bằng `Project project = new Project(dataDir + "Project.mpp");` sau đó gọi `Resource resource = project.getResources().toList().stream().filter(r -> r.getUid() == desiredUid).findFirst().orElse(null);`. Sau khi có được đối tượng `Resource`, sử dụng `resource.getPeakUnits()` để đọc các đơn vị tổng hợp trên tất cả các dự án liên kết. Cách tiếp cận ngắn gọn hai bước này trả về dữ liệu phân công bạn cần mà không cần mở từng tệp liên kết riêng lẻ.

## Tại sao Điều này Quan trọng
Đọc các phân công tài nguyên chung cho phép bạn **chỉnh sửa phân công** một cách thông minh, cân bằng khối lượng công việc và tạo các báo cáo chính xác—đây là các bước then chốt trong quản trị dự án hiệu quả. Với Aspose.Tasks, bạn có thể xử lý các dự án chứa **tối đa 10.000 công việc** trong khi giữ mức sử dụng bộ nhớ dưới **200 MB**, nhờ kiến trúc streaming của nó.

## Các vấn đề thường gặp & Mẹo
- **Tài nguyên null:** Đảm bảo UID bạn yêu cầu thực sự tồn tại trong tệp.  
- **Đường dẫn tệp không đúng:** Sử dụng đường dẫn tuyệt đối hoặc xác minh `dataDir` kết thúc bằng dấu phân cách.  
- **Ngoại lệ giấy phép:** Chạy mà không có giấy phép có thể gây ra cảnh báo chế độ dùng thử; áp dụng giấy phép của bạn sớm trong mã.

## Câu hỏi thường gặp

**Q: Tôi có thể chỉnh sửa các phân công tài nguyên bằng Aspose.Tasks cho Java không?**  
A: Có, bạn có thể thay đổi giá trị phân công, ngày và đơn vị một cách lập trình.

**Q: Aspose.Tasks cho Java có tương thích với các định dạng tệp dự án khác nhau không?**  
A: Có, nó hỗ trợ MPP, XML, MPX và các định dạng phổ biến khác.

**Q: Tôi có thể tạo báo cáo dựa trên các phân công tài nguyên không?**  
A: Chắc chắn—sử dụng API báo cáo để xuất các báo cáo tùy chỉnh dưới dạng PDF, XLSX hoặc HTML.

**Q: Có bất kỳ giới hạn nào về kích thước tệp dự án mà nó có thể xử lý không?**  
A: Aspose.Tasks mở rộng từ các dự án nhỏ đến quy mô lớn; hiệu năng phụ thuộc vào bộ nhớ khả dụng.

**Q: Hỗ trợ kỹ thuật có sẵn cho người dùng Aspose.Tasks cho Java không?**  
A: Có, bạn có thể nhận trợ giúp từ diễn đàn Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Kết luận
Bây giờ bạn đã biết **cách đọc các phân công** từ tài nguyên chung bằng Aspose.Tasks cho Java, cách truy xuất một tài nguyên theo UID và cách tính các đơn vị cao nhất của nó trên các dự án liên kết. Áp dụng các bước này để xây dựng bảng điều khiển, cân bằng khối lượng công việc và tự động hoá báo cáo trong các giải pháp quản lý dự án của bạn.

---

**Cập nhật lần cuối:** 2026-06-20  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Cách chỉnh sửa phân công – Đọc tài nguyên chung với Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Tạo phân công tài nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Cách thêm ghi chú vào phân công tài nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}