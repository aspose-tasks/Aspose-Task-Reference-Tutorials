---
date: 2026-07-19
description: Tìm hiểu cách thêm aspose tasks resource notes vào các phân công tài
  nguyên bằng Aspose.Tasks for Java. Thực hiện theo hướng dẫn từng bước này để cải
  thiện giao tiếp trong dự án.
keywords:
- aspose tasks resource notes
- resource assignment notes
- aspose.tasks java
lastmod: 2026-07-19
linktitle: Cách Thêm Ghi chú vào Phân công Tài nguyên trong Aspose.Tasks
og_description: Tìm hiểu cách thêm aspose tasks resource notes vào các phân công tài
  nguyên bằng Aspose.Tasks for Java. Hướng dẫn này sẽ đưa bạn qua từng bước, từ cài
  đặt đến việc truy xuất ghi chú.
og_image_alt: 'Guide: Adding resource assignment notes with Aspose.Tasks for Java'
og_title: aspose tasks resource notes – Thêm Ghi chú vào Phân công
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  headline: aspose tasks resource notes – Add Notes to Assignments
  type: TechArticle
- description: Learn how to add aspose tasks resource notes to resource assignments
    using Aspose.Tasks for Java. Follow this step‑by‑step guide to improve project
    communication.
  name: aspose tasks resource notes – Add Notes to Assignments
  steps:
  - name: Set Data Directory
    text: Set the path to your data directory where your project files are located.
  - name: Load Project File
    text: Load the project file into your Java application.
  - name: Get Task and Resource
    text: Retrieve the task and resource to which you want to add notes.
  - name: Create Resource Assignment
    text: Create a resource assignment for the task and resource.
  - name: Set Notes
    text: Set the notes for the resource assignment.
  - name: Display Notes
    text: Display the notes text and RTF format.
  - name: Process Completion
    text: Print a success message indicating the completion of the process.
  type: HowTo
- questions:
  - answer: Yes, simply call `assn.set(Asn.NOTES_TEXT, "Updated note")` again with
      the new content.
    question: Can I edit notes after they have been set?
  - answer: Absolutely. When you save the `Project` object, the notes become part
      of the assignment data inside the file.
    question: Are notes stored in the .mpp file?
  - answer: You must open the project with the correct password using the appropriate
      `Project` constructor overload before accessing assignments.
    question: Does this work with encrypted project files?
  - answer: Practically, notes can be several kilobytes long; extremely large notes
      may affect performance when loading the project.
    question: Is there a limit to the length of a note?
  - answer: Yes, iterate over `prj.getResourceAssignments()` and set `Asn.NOTES_TEXT`
      for each assignment as needed.
    question: Can I add notes to multiple assignments in a loop?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- resource notes
- java project management
- resource assignments
- aspose tasks java
title: aspose tasks resource notes – Thêm Ghi chú vào Phân công
url: /vi/java/resource-assignments/resource-assignment-notes/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Ghi Chú vào Phân Công Tài Nguyên trong Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách thêm ghi chú vào phân công tài nguyên** với Aspose.Tasks cho Java – thư viện hàng đầu trong ngành xử lý các tệp quản lý dự án. Khi kết thúc hướng dẫn, bạn sẽ có thể đính kèm các bình luận dạng văn bản thuần hoặc văn bản định dạng (rich‑text) trực tiếp vào liên kết nhiệm vụ‑tài nguyên, làm cho dữ liệu dự án của bạn trở nên giao tiếp hơn và sẵn sàng cho kiểm toán.

## Câu trả lời nhanh
- **Thêm ghi chú ảnh hưởng gì?** Nó lưu trữ ghi chú dạng văn bản thuần và RTF trên một phân công tài nguyên.  
- **Lớp nào chứa dữ liệu ghi chú?** Lớp `Asn` (ví dụ, `Asn.NOTES_TEXT`).  
- **Tôi có cần giấy phép để thử không?** Không, một bản dùng thử miễn phí có sẵn trên trang web Aspose.  
- **Tôi có thể lấy ghi chú ở định dạng RTF không?** Có, sử dụng `Asn.NOTES_RTF`.  
- **Điều này có tương thích với mọi IDE Java không?** Hoàn toàn tương thích – IntelliJ IDEA, Eclipse, NetBeans, v.v.  

## Thêm ghi chú vào phân công tài nguyên là gì?
Thêm ghi chú có nghĩa là gắn văn bản mô tả—dạng văn bản thuần hoặc văn bản định dạng (RTF)—vào liên kết giữa một nhiệm vụ và một tài nguyên. Tính năng này cho phép các nhà quản lý dự án nhúng ngữ cảnh, hướng dẫn đặc biệt, hoặc bình luận nhật ký thay đổi trực tiếp vào phân công, đảm bảo rằng bất kỳ ai xem xét lịch trình đều có thể ngay lập tức hiểu “lý do” đằng sau mỗi phân bổ.

## Tại sao cần thêm ghi chú?
Thêm ghi chú tạo ra một kênh giao tiếp ngay lập tức bên trong tệp dự án. Nó loại bỏ nhu cầu sử dụng các bảng tính hoặc chuỗi email bên ngoài, cung cấp một dấu vết kiểm toán tích hợp, và, nhờ hỗ trợ RTF, cho phép bạn nhấn mạnh thông tin quan trọng bằng kiểu chữ in đậm hoặc in nghiêng—tất cả mà không cần rời khỏi môi trường quản lý dự án.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – phiên bản 8 trở lên, được cấu hình đúng trên máy của bạn.  
2. **Aspose.Tasks for Java** – tải JAR mới nhất từ [official website](https://releases.aspose.com/tasks/java/).  
3. **Một IDE** – IntelliJ IDEA, Eclipse, NetBeans, hoặc bất kỳ trình chỉnh sửa nào tương thích Java mà bạn thích.  

## Nhập các gói
Start by importing the necessary packages into your Java project:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

## Cách Thêm Ghi Chú vào Phân Công Tài Nguyên
Trong phần này, chúng tôi sẽ hướng dẫn quy trình đầy đủ để gắn ghi chú vào một phân công tài nguyên. Bắt đầu từ việc thiết lập thư mục dữ liệu, tải dự án, lấy nhiệm vụ và tài nguyên liên quan, tạo phân công, và cuối cùng thiết lập và hiển thị cả ghi chú dạng văn bản thuần và RTF, mỗi bước được minh họa bằng các placeholder mã mà bạn có thể thay thế bằng các đoạn mã gốc.

### Bước 1: Đặt Thư Mục Dữ Liệu
Đặt đường dẫn tới thư mục dữ liệu nơi các tệp dự án của bạn được lưu trữ.
```java
String dataDir = "Your Data Directory";
```

### Bước 2: Tải Tệp Dự Án
Tải tệp dự án vào ứng dụng Java của bạn.
```java
Project prj = new Project(dataDir + "UpdateResourceAssignment.mpp");
```

### Bước 3: Lấy Nhiệm Vụ và Tài Nguyên
Lấy nhiệm vụ và tài nguyên mà bạn muốn thêm ghi chú.
```java
Task task = prj.getRootTask().getChildren().getById(1);
Resource rsc = prj.getResources().getById(1);
```

### Bước 4: Tạo Phân Công Tài Nguyên
Tạo một phân công tài nguyên cho nhiệm vụ và tài nguyên.
```java
ResourceAssignment assn = prj.getResourceAssignments().add(task, rsc);
```

### Bước 5: Đặt Ghi Chú
Đặt ghi chú cho phân công tài nguyên.
```java
assn.set(Asn.NOTES_TEXT, "Newly added assignment");
```

### Bước 6: Hiển Thị Ghi Chú
Hiển thị văn bản ghi chú và định dạng RTF.
```java
System.out.println("Notes text: " + assn.get(Asn.NOTES_TEXT));
System.out.println("Notes RTF: " + assn.get(Asn.NOTES_RTF));
```

### Bước 7: Hoàn Thành Quy Trình
In ra thông báo thành công cho biết quá trình đã hoàn tất.
```java
System.out.println("Process completed Successfully");
```

## Lớp Asn là gì?
Lớp `Asn` định nghĩa các hằng số đại diện cho các trường trên một phân công tài nguyên, chẳng hạn như ghi chú, chi phí và công việc. Bạn sử dụng các hằng số này với các phương thức `set` và `get` trên đối tượng `ResourceAssignment` để đọc hoặc ghi dữ liệu tương ứng. Ví dụ, `Asn.NOTES_TEXT` lưu trữ ghi chú dạng văn bản thuần, trong khi `Asn.NOTES_RTF` chứa phiên bản văn bản định dạng.

## Các vấn đề thường gặp và giải pháp
- **NullPointerException khi lấy nhiệm vụ/tài nguyên:** Xác minh rằng các ID (`1` trong ví dụ) thực sự tồn tại trong tệp `.mpp` của bạn.  
- **Ghi chú không hiển thị trong giao diện người dùng:** Đảm bảo bạn đang xem bảng ghi chú phân công trong Microsoft Project hoặc trình xem khác hỗ trợ ghi chú phân công.  
- **Kết quả RTF trông trống:** API chỉ trả về RTF nếu ghi chú chứa định dạng văn bản định dạng; văn bản thuần sẽ cho ra một chuỗi RTF trống.  

## Câu hỏi thường gặp
**Q: Tôi có thể chỉnh sửa ghi chú sau khi đã đặt không?**  
A: Có, chỉ cần gọi lại `assn.set(Asn.NOTES_TEXT, "Updated note")` với nội dung mới.

**Q: Ghi chú có được lưu trong tệp .mpp không?**  
A: Chắc chắn. Khi bạn lưu đối tượng `Project`, các ghi chú sẽ trở thành một phần của dữ liệu phân công trong tệp.

**Q: Điều này có hoạt động với các tệp dự án được mã hóa không?**  
A: Bạn phải mở dự án bằng mật khẩu đúng sử dụng hàm khởi tạo `Project` phù hợp trước khi truy cập các phân công.

**Q: Có giới hạn độ dài của một ghi chú không?**  
A: Thực tế, ghi chú có thể dài vài kilobyte; ghi chú quá lớn có thể ảnh hưởng đến hiệu năng khi tải dự án.

**Q: Tôi có thể thêm ghi chú vào nhiều phân công trong một vòng lặp không?**  
A: Có, lặp qua `prj.getResourceAssignments()` và đặt `Asn.NOTES_TEXT` cho mỗi phân công theo nhu cầu.

## Kết luận
Bằng cách thực hiện các bước này, bạn giờ đã biết **cách thêm ghi chú vào phân công tài nguyên** với Aspose.Tasks cho Java. Việc tận dụng ghi chú tài nguyên của Aspose.Tasks cải thiện độ rõ ràng của dự án, tạo ra một dấu vết kiểm toán tích hợp, và cho phép bạn nhúng các bình luận văn bản định dạng mà không cần rời khỏi tệp lịch. Khám phá thêm các tính năng API như cập nhật hàng loạt, trường tùy chỉnh, và tích hợp với các quy trình quản lý dự án hiện có của bạn.

---

**Cập nhật lần cuối:** 2026-07-19  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thêm tài nguyên vào dự án với Aspose.Tasks cho Java](/tasks/java/resource-management/create-resources/)
- [Cách Thêm Tài Nguyên vào Dự Án và Xử Lý Thuộc Tính Độ Trễ Cân Bằng trong Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)
- [Cách Dừng Phân Công và Tiếp Tục Phân Công Tài Nguyên trong Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}