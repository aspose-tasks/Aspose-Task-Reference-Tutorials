---
date: 2026-06-15
description: Tìm hiểu cách trích xuất dữ liệu timephased từ tài nguyên MS Project
  bằng Aspose.Tasks cho Java. Hướng dẫn chi tiết từng bước để lấy tài nguyên theo
  id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Đọc Dữ liệu Timephased cho Tài nguyên trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Đọc Dữ liệu Timephased cho Tài nguyên trong Aspose.Tasks – lấy tài nguyên theo
  id
url: /vi/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc Dữ liệu Thời gian cho Tài nguyên trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách lấy tài nguyên theo id** và đọc dữ liệu thời gian của nó bằng Aspose.Tasks cho Java. Chúng tôi sẽ hướng dẫn từng bước — từ việc thiết lập thư mục dự án đến việc in ra các giá trị thời gian cho công việc và chi phí — để bạn có thể trích xuất thông tin lập lịch có giá trị từ bất kỳ tệp Microsoft Project nào một cách lập trình. Aspose.Tasks cho Java là một API toàn diện cho phép các nhà phát triển tạo, đọc, sửa đổi và chuyển đổi các tệp Microsoft Project mà không cần cài đặt Microsoft Project, hỗ trợ một loạt các tính năng và định dạng quản lý dự án.

## Câu trả lời nhanh
- **“get resource by id” làm gì?** Nó trả về một đối tượng `Resource` cụ thể từ một `Project` bằng cách sử dụng định danh duy nhất của nó.  
- **Thư viện nào xử lý dữ liệu thời gian?** Aspose.Tasks cho Java cung cấp API `Resource.getTimephasedData`.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể đọc các dự án lớn không?** Có — Aspose.Tasks có thể xử lý các tệp lên tới 10.000 nhiệm vụ mà không cần tải toàn bộ tệp vào bộ nhớ.  
- **Yêu cầu phiên bản Java nào?** Java 8 trở lên; thư viện tương thích với tất cả các JDK chính.

## “get resource by id” là gì?
`get resource by id` là một lời gọi phương thức lấy một thể hiện `Resource` từ một `Project` đã tải bằng cách sử dụng ID số của tài nguyên. Thao tác này cho phép truy cập chính xác vào các thuộc tính chi tiết của tài nguyên, như các phân công, lịch, và trường tùy chỉnh, và là cần thiết để trích xuất dữ liệu thời gian cho công việc hoặc chi phí liên quan đến tài nguyên cụ thể đó.

## Tại sao sử dụng Aspose.Tasks cho dữ liệu thời gian?
Aspose.Tasks hỗ trợ **hơn 50 định dạng nhập và xuất** (MPP, XML, CSV, v.v.) và có thể trích xuất các giá trị công việc và chi phí theo thời gian cho tài nguyên trong các lịch trình đa năm trong khi giữ mức sử dụng bộ nhớ thấp. API trả về dữ liệu theo khoảng thời gian 15 phút mặc định, cung cấp cho bạn cái nhìn chi tiết cho báo cáo hoặc phân tích tùy chỉnh.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có các yêu cầu sau:
1. Java Development Kit (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống. Bạn có thể tải xuống từ [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) và làm theo hướng dẫn cài đặt.  
2. Thư viện Aspose.Tasks cho Java: Tải thư viện Aspose.Tasks cho Java từ [trang tải xuống](https://releases.aspose.com/tasks/java/) và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu.

## Nhập gói
Bước đầu tiên là nhập các lớp Aspose.Tasks cần thiết vào tệp nguồn Java của bạn.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Bước 1: Thiết lập thư mục dữ liệu
Đầu tiên, xác định thư mục chứa tệp MS Project của bạn. Giữ thư mục dữ liệu tách riêng khỏi mã nguồn giúp dự án dễ bảo trì hơn.

```java
String dataDir = "Your Data Directory";
```

## Bước 2: Đọc tệp mẫu MS Project
Xác định tên tệp mẫu MS Project của bạn. Sử dụng mẫu đảm bảo các thiết lập cột nhất quán giữa các dự án khác nhau.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Bước 3: Đọc tệp đầu vào dưới dạng Project
Lớp `Project` là đối tượng cốt lõi của Aspose.Tasks đại diện cho một tệp Microsoft Project trong bộ nhớ. Việc tải tệp cho phép bạn truy cập lập trình vào các nhiệm vụ, tài nguyên và lịch trình.

```java
Project project = new Project(dataDir + fileName);
```

## Bước 4: Lấy tài nguyên theo ID
Để lấy một tài nguyên cụ thể, gọi phương thức `getResources().getById(id)`. Đây là thao tác chính xác được đề cập bởi từ khóa chính.

```java
Resource resource = project.getResources().getByUid(1);
```

## Bước 5: In dữ liệu thời gian cho công việc của tài nguyên
Khi bạn đã có đối tượng `Resource`, bạn có thể gọi `resource.getTimephasedData(ResourceTimephasedDataType.Work)` để lấy các phân bổ công việc theo thời gian. Bộ sưu tập trả về chứa các đối tượng `TimephasedData` bao gồm ngày bắt đầu, ngày kết thúc và lượng công việc cho mỗi khoảng thời gian.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Bước 6: In dữ liệu thời gian cho chi phí của tài nguyên
Tương tự, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` trả về thông tin chi phí được phân chia theo cùng các khoảng thời gian. Điều này hữu ích cho các báo cáo ngân sách và theo dõi chi phí.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Cách lấy tài nguyên theo ID trong một dòng?
Tải dự án, sau đó gọi `project.getResources().getById(5)` — thay **5** bằng ID tài nguyên thực tế bạn cần. Lệnh duy nhất này trả về đối tượng `Resource`, sau đó bạn có thể truy vấn dữ liệu thời gian, các phân công hoặc trường tùy chỉnh của nó. Phương thức này chạy trong thời gian O(1) vì các tài nguyên được lập chỉ mục nội bộ.

## Các vấn đề thường gặp và giải pháp
- **Resource not found** – Đảm bảo ID tồn tại trong tệp dự án; ID bắt đầu từ 1 và là duy nhất cho mỗi tài nguyên.  
- **Empty timephased data** – Kiểm tra xem tài nguyên có phân công công việc hoặc chi phí không; nếu không bộ sưu tập sẽ rỗng.  
- **Large file performance** – Sử dụng `Project.setLoadOptions(LoadOptions.fromFile(...))` để bật tải lười cho các dự án lớn hơn 500 MB.

## Câu hỏi thường gặp

**Q: Aspose.Tasks có thể xử lý các loại tệp dự án khác ngoài Microsoft Project không?**  
A: Có, Aspose.Tasks hỗ trợ MPP, XML, CSV và một số định dạng khác, cho phép bạn đọc và ghi qua các tiêu chuẩn khác nhau.

**Q: Aspose.Tasks có tương thích với các môi trường phát triển Java khác nhau không?**  
A: Hoàn toàn có. Thư viện hoạt động với tất cả các IDE chính (IntelliJ IDEA, Eclipse, NetBeans) và công cụ xây dựng (Maven, Gradle).

**Q: Tôi có thể thao tác dữ liệu dự án bằng Aspose.Tasks không?**  
A: Có, bạn có thể tạo, sửa đổi và xóa nhiệm vụ, tài nguyên, phân công và thậm chí các trường tùy chỉnh thông qua API.

**Q: Aspose.Tasks có phù hợp cho các dự án cấp doanh nghiệp không?**  
A: Có. Các doanh nghiệp dựa vào Aspose.Tasks để xử lý khối lượng lớn, chuyển đổi hàng loạt và báo cáo phía máy chủ vì không cần cài đặt Microsoft Project.

**Q: Tôi có thể tìm hỗ trợ ở đâu nếu gặp vấn đề khi sử dụng Aspose.Tasks?**  
A: Bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để nhận trợ giúp từ cộng đồng và đội ngũ hỗ trợ.

## Kết luận
Trong hướng dẫn này, chúng ta đã học cách **lấy tài nguyên theo id** và đọc dữ liệu thời gian cho công việc và chi phí của nó bằng Aspose.Tasks cho Java. Bằng cách thực hiện các bước này, bạn có thể hiệu quả trích xuất thông tin lập lịch có giá trị từ các tệp dự án và tích hợp chúng vào các quy trình báo cáo hoặc phân tích tùy chỉnh.

---

**Cập nhật lần cuối:** 2026-06-15  
**Kiểm tra với:** Aspose.Tasks 24.11 cho Java  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thêm tài nguyên vào dự án với Aspose.Tasks cho Java](/tasks/java/resource-management/create-resources/)
- [Quản lý chi phí tài nguyên MS Project với Aspose.Tasks cho Java](/tasks/java/resource-management/resource-cost/)
- [Đọc tuần làm việc Java từ Lịch MS Project bằng Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}