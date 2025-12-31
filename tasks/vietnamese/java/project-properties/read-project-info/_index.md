---
date: 2025-12-31
description: Tìm hiểu cách đọc thông tin dự án, bao gồm lịch trình từ đầu, bằng cách
  sử dụng Aspose.Tasks cho Java. Khám phá cách trích xuất các thuộc tính dự án trong
  Java một cách nhanh chóng.
linktitle: Read Project Info with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách Đọc Thông Tin Dự Án Từ Microsoft Project Bằng Aspose.Tasks cho Java
url: /vi/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đọc Thông Tin Dự Án Từ Microsoft Project Bằng Aspose.Tasks cho Java

## Giới thiệu
Nếu bạn cần **cách đọc dự án** chi tiết như ngày bắt đầu, ngày kết thúc, hoặc cài đặt lịch làm việc trực tiếp từ tệp Microsoft Project, Aspose.Tasks cho Java cung cấp một cách tiếp cận sạch sẽ, dựa trên mã. Trong hướng dẫn này, bạn sẽ thấy **cách đọc dự án** metadata, hiểu **lịch trình dự án từ đầu** và học cách lấy các thuộc tính quan trọng khác—tất cả chỉ trong vài dòng mã Java.

## Trả lời nhanh
- **Aspose.Tasks cho Java làm gì?** Nó cho phép truy cập lập trình vào các tệp Microsoft Project (MPP, XML, v.v.) mà không cần cài đặt Microsoft Project.  
- **Thuộc tính nào cho biết lịch trình dựa trên ngày bắt đầu?** `Prj.SCHEDULE_FROM_START` – true nghĩa là lịch trình từ ngày bắt đầu, false nghĩa là từ ngày kết thúc.  
- **Tôi có thể trích xuất các thuộc tính dự án trong Java không?** Có, bạn có thể đọc ngày bắt đầu, ngày kết thúc, ngày hiện tại, ngày trạng thái và tên lịch.  
- **Có cần giấy phép cho việc phát triển không?** Giấy phép tạm thời miễn phí hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Yêu cầu phiên bản Java nào?** Java 8 hoặc cao hơn với JAR Aspose.Tasks nằm trong classpath.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Môi trường phát triển Java** – JDK 8 hoặc mới hơn đã được cài đặt và cấu hình.  
2. **Aspose.Tasks cho Java** – Tải thư viện mới nhất từ [website](https://releases.aspose.com/tasks/java/).  

## Nhập gói
Để tương tác với các tệp dự án, nhập namespace cốt lõi của Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Hướng dẫn từng bước

### Bước 1: Xác định thư mục dữ liệu
Đặt thư mục chứa tệp `.mpp` của bạn. Thay thế placeholder bằng đường dẫn thực tế trên máy của bạn.

```java
String dataDir = "Your Data Directory";
```

### Bước 2: Tải tệp dự án
Tạo một thể hiện `Project` bằng cách tải tệp Microsoft Project mà bạn muốn kiểm tra.

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### Bước 3: Xác định cơ sở lịch trình dự án
Kiểm tra xem lịch trình có được tính từ ngày bắt đầu dự án hay từ ngày kết thúc hay không. Đây là phần cốt lõi của **cách đọc dự án** thông tin lịch trình.

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **Mẹo:** `Prj.SCHEDULE_FROM_START` trả về một Boolean; `true` có nghĩa là *lịch trình dự án từ ngày bắt đầu*.

### Bước 4: Lấy thêm thông tin lịch trình dự án
Ngoài ngày bắt đầu/kết thúc, bạn thường cần ngày hiện tại, ngày trạng thái và lịch được liên kết với dự án. Điều này minh họa **đọc thuộc tính dự án java** trong thực tế.

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## Các vấn đề thường gặp & Giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| `NullPointerException` khi gọi `project.get(Prj.CALENDAR)` | Tệp dự án thiếu lịch mặc định. | Đảm bảo tệp MPP định nghĩa một lịch hoặc xử lý kiểm tra `null`. |
| Ngày được in ra là `null` | Tệp dự án bị hỏng hoặc thiếu trường ngày. | Xác thực tệp nguồn trong Microsoft Project trước khi xử lý. |
| Lỗi biên dịch: `cannot find symbol Prj` | JAR Aspose.Tasks chưa có trong classpath. | Thêm `aspose-tasks-xx.jar` vào đường dẫn xây dựng của dự án. |

## Câu hỏi thường gặp

### H: Tôi có thể sử dụng Aspose.Tasks cho Java với bất kỳ phiên bản tệp Microsoft Project nào không?
Đ: Có, Aspose.Tasks cho Java hỗ trợ nhiều phiên bản tệp Microsoft Project, bao gồm định dạng MPP và XML.

### H: Aspose.Tasks cho Java có tương thích với mọi môi trường phát triển Java không?
Đ: Aspose.Tasks cho Java tương thích với hầu hết các môi trường phát triển Java, đảm bảo tính linh hoạt trong việc tích hợp.

### H: Aspose.Tasks cho Java có hỗ trợ thao tác dữ liệu dự án ngoài việc chỉ đọc thông tin không?
Đ: Chắc chắn, Aspose.Tasks cho Java cung cấp các chức năng phong phú để thao tác dữ liệu dự án, bao gồm chỉnh sửa, lưu và xuất dữ liệu.

### H: Tôi có thể tự động trích xuất thông tin dự án bằng Aspose.Tasks cho Java không?
Đ: Có, Aspose.Tasks cho Java cho phép tự động hoá thông qua API toàn diện, giúp quy trình trích xuất và phân tích dữ liệu trở nên mượt mà.

### H: Có diễn đàn cộng đồng hoặc kênh hỗ trợ nào cho người dùng Aspose.Tasks cho Java không?
Đ: Có, bạn có thể tìm các tài nguyên hữu ích và tham gia cộng đồng tại [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### H: Làm sao để đọc thuộc tính dự án trong Java mà không tải toàn bộ cây nhiệm vụ?
Đ: Sử dụng phương thức `Project.get` với các giá trị enum `Prj` cần thiết; cách này chỉ lấy metadata được yêu cầu, giảm mức sử dụng bộ nhớ.

### H: Cách tốt nhất để xử lý các tệp MPP lớn khi trích xuất thuộc tính là gì?
Đ: Tải dự án ở chế độ *chỉ đọc* (`new Project(filePath, LoadOptions)`) và truy vấn chỉ những thuộc tính cần thiết để tránh tiêu thụ bộ nhớ cao.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn đã biết **cách đọc dự án** thông tin như nguồn gốc lịch trình, ngày tháng và chi tiết lịch sử dụng Aspose.Tasks cho Java. Việc tích hợp các đoạn mã này vào ứng dụng của bạn cho phép tự động hoá báo cáo, bảng điều khiển tùy chỉnh và đưa ra quyết định thông minh mà không cần thao tác thủ công với Microsoft Project.

---

**Cập nhật lần cuối:** 2025-12-31  
**Kiểm tra với:** Aspose.Tasks cho Java 24.10  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}