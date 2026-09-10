---
date: 2026-09-09
description: Tìm hiểu cách xác định cross project tasks bằng Aspose.Tasks cho Java.
  Khám phá tích hợp liền mạch, quản lý hiệu quả và các ví dụ thực tế.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Xác định cross project tasks trong Aspose.Tasks
og_description: Xác định cross project tasks trong Aspose.Tasks cho Java. Tìm hiểu
  cách thiết lập thư mục tài liệu, truy xuất ID nhiệm vụ và quản lý các dự án liên
  kết một cách hiệu quả.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Xác định cross project tasks trong Aspose.Tasks – Hướng dẫn Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Xác định cross project tasks trong Aspose.Tasks
url: /vi/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xác định các nhiệm vụ xuyên dự án trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách xác định các nhiệm vụ xuyên dự án** với Aspose.Tasks cho Java. Cho dù bạn duy trì một danh mục các lịch trình phụ thuộc lẫn nhau hoặc cần kiểm tra các phụ thuộc bên ngoài, các bước dưới đây sẽ chỉ cho bạn cách tìm các nhiệm vụ tham chiếu tới các tệp dự án khác, lấy các định danh của chúng và làm việc với chúng một cách lập trình.

## Câu trả lời nhanh
- **“identify cross project tasks” có nghĩa là gì?** Nó có nghĩa là tìm các nhiệm vụ tham chiếu hoặc phụ thuộc vào các nhiệm vụ trong một tệp dự án khác.  
- **Phương thức nào in ID của nhiệm vụ?** Sử dụng `externalTask.get(Tsk.ID)` để in ID của nhiệm vụ.  
- **Làm thế nào để đặt thư mục tài liệu?** Gán đường dẫn thư mục vào một biến kiểu `String` (ví dụ, `dataDir`).  
- **Thuộc tính nào lấy một nhiệm vụ theo UID?** Gọi `getChildren().getByUid(yourUid)`.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Có, cần có giấy phép Aspose.Tasks hợp lệ cho các triển khai thương mại.

## “identify cross project tasks” là gì?
Việc xác định các nhiệm vụ xuyên dự án cho phép bạn theo dõi các mối quan hệ giữa các nhiệm vụ được phân bố trên nhiều tệp Microsoft Project. Bằng cách tìm các nhiệm vụ tham chiếu hoặc phụ thuộc vào các lịch trình bên ngoài, bạn có thể hiểu cách các công việc tương tác qua các ranh giới dự án, ngăn ngừa công việc trùng lặp và duy trì các thời gian biểu chính xác. Khả năng này rất quan trọng đối với các danh mục quy mô lớn, nơi các nhiệm vụ được chia sẻ hoặc phụ thuộc vào các lịch trình bên ngoài.

## Tại sao nên sử dụng Aspose.Tasks cho Java?
Aspose.Tasks cho Java hỗ trợ **hơn 50 định dạng nhập và xuất** (bao gồm MPP, MPX, XML và CSV) và có thể xử lý các dự án với **tối đa 10.000 nhiệm vụ** mà không cần tải toàn bộ tệp vào bộ nhớ. Thư viện hoạt động trên bất kỳ nền tảng nào tương thích với JVM, không yêu cầu cài đặt Microsoft Project và cung cấp quyền truy cập đầy đủ API tới ID, UID, ID bên ngoài và siêu dữ liệu liên kết.

## Yêu cầu trước
- Môi trường phát triển Java hoạt động (JDK 8 hoặc cao hơn).  
- Aspose.Tasks cho Java đã được cài đặt. Bạn có thể tải xuống **[đây](https://releases.aspose.com/tasks/java/)**.  
- Tệp giấy phép Aspose.Tasks hợp lệ nếu bạn dự định chạy mã trong môi trường sản xuất.

## Nhập các gói
Lớp `Project` đại diện cho một tệp Microsoft Project, `Task` đại diện cho một nhiệm vụ riêng lẻ, và `Tsk` cung cấp các hằng số trường nhiệm vụ.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Bước 1: đặt thư mục tài liệu
Chuỗi `dataDir` chứa đường dẫn tới thư mục chứa các tệp `.mpp` của bạn.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Bước 2: tải dự án bên ngoài
`Project externalProject` tải tệp dự án bên ngoài được chỉ định để kiểm tra.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Bước 3: lấy nhiệm vụ bên ngoài theo uid
`externalProject.getChildren().getByUid(uid)` lấy một nhiệm vụ từ bộ sưu tập nhiệm vụ của dự án bên ngoài bằng cách sử dụng định danh duy nhất của nó.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Bước 4: in ID nhiệm vụ (trường hợp sử dụng chính)
`externalTask.get(Tsk.ID)` trả về ID nội bộ được Aspose.Tasks gán cho nhiệm vụ đã cho.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Bước 5: in ID nhiệm vụ gốc (bên ngoài)
`externalTask.get(Tsk.ExternalID)` lấy ID gốc của nhiệm vụ như được định nghĩa trong tệp dự án nguồn.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Lặp lại các bước trên cho bất kỳ nhiệm vụ bổ sung nào bạn cần theo dõi qua các dự án.

## Các vấn đề thường gặp & mẹo
- **Lỗi đường dẫn** – Đảm bảo `dataDir` kết thúc bằng ký tự phân tách tệp phù hợp (`/` hoặc `\\`).  
- **UID không tìm thấy** – Xác minh UID tồn tại trong dự án bên ngoài; sử dụng `externalProject.getRootTask().getChildren().size()` để liệt kê các UID khả dụng.  
- **Ngoại lệ giấy phép** – Thiếu hoặc giấy phép không hợp lệ sẽ gây ra ngoại lệ giấy phép khi chạy.  
- **Dự án lớn** – Đối với các dự án có hơn 5.000 nhiệm vụ, cân nhắc sử dụng `ProjectReader` với cờ `LoadOptions` để truyền dữ liệu và giảm tiêu thụ bộ nhớ.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
A: Có, Aspose.Tasks hỗ trợ nhiều ngôn ngữ, bao gồm Java, .NET và các ngôn ngữ khác.

**Q: Tôi có thể tìm tài liệu chi tiết cho Aspose.Tasks cho Java ở đâu?**  
A: Tham khảo tài liệu **[đây](https://reference.aspose.com/tasks/java/)**.

**Q: Có bản dùng thử miễn phí cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí **[đây](https://releases.aspose.com/)**.

**Q: Làm thế nào tôi có thể nhận giấy phép tạm thời cho Aspose.Tasks?**  
A: Nhận giấy phép tạm thời **[đây](https://purchase.aspose.com/temporary-license/)**.

**Q: Cần trợ giúp hoặc có câu hỏi cụ thể?**  
A: Truy cập diễn đàn hỗ trợ Aspose.Tasks **[đây](https://forum.aspose.com/c/tasks/15)**.

---

**Cập nhật lần cuối:** 2026-09-09  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo các phụ thuộc nhiệm vụ quản lý dự án trong Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Đặt ngày bắt đầu dự án và quản lý nhiệm vụ cha và con trong Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Tạo dự án MPP Java – Thay đổi tiến độ nhiệm vụ với Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}