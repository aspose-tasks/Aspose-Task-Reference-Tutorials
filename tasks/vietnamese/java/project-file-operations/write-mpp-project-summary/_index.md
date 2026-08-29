---
date: 2026-03-29
description: Tìm hiểu cách đặt từ khóa và ngày tạo trong dự án MPP bằng Java sử dụng
  Aspose.Tasks for Java. Hướng dẫn chi tiết từng bước kèm ví dụ mã.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách thiết lập từ khóa trong bản tóm tắt dự án MPP bằng Aspose.Tasks
url: /vi/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Từ Khóa trong Tóm Tắt Dự Án MPP bằng Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách đặt từ khóa** và các thông tin tóm tắt khác cho tệp dự án MPP bằng cách sử dụng Aspose.Tasks cho Java. Cho dù bạn cần nhúng thông tin tác giả, số phiên bản, hoặc ngày tạo tùy chỉnh, hướng dẫn này sẽ dẫn bạn qua các bước chính xác, kèm theo mã sẵn sàng chạy. Khi hoàn thành, bạn sẽ có thể đặt từ khóa, đặt ngày tạo java, và truy xuất dữ liệu trở lại từ tệp.

## Câu trả lời nhanh
- **Thư viện nào được sử dụng?** Aspose.Tasks for Java  
- **Mục đích chính?** Set keywords, author info, and creation date in an MPP file  
- **Có bao nhiêu bước mã?** Three simple code blocks (initialize, save, read)  
- **Tôi có cần giấy phép không?** A free trial works for development; a commercial license is required for production  
- **Phiên bản Java được hỗ trợ?** Java 8 and higher  

## “cách đặt từ khóa” trong tệp MPP là gì?
Từ khóa là các trường siêu dữ liệu được lưu trong tệp Microsoft Project (MPP). Chúng giúp phân loại dự án, cho phép tìm kiếm nhanh và cung cấp thông tin ngữ cảnh cho các công cụ downstream. Aspose.Tasks cung cấp thuộc tính `Prj.KEYWORDS`, giúp việc ghi hoặc cập nhật giá trị này một cách lập trình trở nên đơn giản.

## Tại sao nên sử dụng Aspose.Tasks cho Java để đặt từ khóa và ngày tạo?
* **Tương thích đầy đủ .MPP** – hoạt động với mọi định dạng Project 2007‑2023.  
* **Không cần cài đặt COM hoặc Office** – thuần Java, hoàn hảo cho môi trường máy chủ.  
* **API phong phú** – ngoài từ khóa, bạn có thể đặt tác giả, phiên bản, bình luận và ngày trong một lời gọi duy nhất.  
* **Tối ưu hiệu năng** – đọc/ghi nhanh ngay cả với các tệp dự án lớn.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:
1. **Java Development Kit (JDK)** – JDK 8 hoặc mới hơn đã được cài đặt.  
2. **Aspose.Tasks for Java** – download the latest JAR from [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, hoặc bất kỳ trình chỉnh sửa nào bạn thích.

## Nhập gói
Đầu tiên, nhập các lớp bạn sẽ cần. Các import này cho phép bạn truy cập vào đối tượng `Project`, enumeration `Prj` cho các trường tóm tắt, và enum `SaveFileFormat` để lưu.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Bước 1: Thiết lập Dự án và Định nghĩa Thông tin Tóm tắt
Tạo một thể hiện `Project`, sau đó sử dụng phương thức `set` để ghi siêu dữ liệu mong muốn. Lưu ý cách chúng tôi **đặt từ khóa** và **đặt ngày tạo java** bằng một đối tượng `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Bước 2: Lưu Thông tin Tóm tắt Dự án
Sau khi điền các trường, lưu lại các thay đổi. Ở đây chúng tôi lưu dự án dưới dạng XML để dễ kiểm tra, nhưng bạn cũng có thể lưu lại dưới dạng MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Bước 3: Đọc Thông tin Tóm tắt Dự án
Để xác minh rằng siêu dữ liệu đã được ghi đúng, tải lại tệp và đọc lại từng thuộc tính. Bước này chứng minh rằng **cách đặt từ khóa** thực sự hoạt động từ đầu đến cuối.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Vấn đề Thường gặp và Giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **NullPointerException trên `project.get(Prj.CREATION_DATE)`** | Lịch không bao giờ được thiết lập trước khi lưu. | Đảm bảo gọi `project.set(Prj.CREATION_DATE, cal.getTime())` trước `save()`. |
| **Từ khóa không hiển thị trong giao diện Microsoft Project** | Tệp đã được lưu dưới dạng XML và mở trực tiếp trong Project. | Lưu lại dưới dạng MPP (`SaveFileFormat.MPP`) hoặc mở XML qua *Import* trong Project. |
| **Giá trị ngày bị dịch theo múi giờ** | Java `Date` bao gồm thông tin múi giờ. | Sử dụng `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` nếu bạn cần ngày ở UTC. |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Tasks for Java can be seamlessly integrated with other Java libraries to enhance your project management capabilities.

**Q: Có phiên bản dùng thử cho Aspose.Tasks cho Java không?**  
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).

**Q: Aspose.Tasks cho Java được cập nhật thường xuyên như thế nào?**  
A: Aspose.Tasks for Java is regularly updated to ensure compatibility with the latest versions of Java and Microsoft Project files.

**Q: Tôi có thể tùy chỉnh thêm thông tin tóm tắt dự án không?**  
A: Absolutely, Aspose.Tasks for Java provides extensive options for customizing project summary information according to your specific requirements.

**Q: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?**  
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

---

**Cập nhật lần cuối:** 2026-03-29  
**Được kiểm tra với:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}