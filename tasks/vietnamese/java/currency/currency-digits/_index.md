---
date: 2026-02-10
description: Tìm hiểu cách lấy giá trị tiền tệ, đọc tệp MS Project và chuyển đổi tệp
  dự án sang Java bằng Aspose.Tasks. Hướng dẫn từng bước để trích xuất các chữ số
  tiền tệ.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách lấy tiền tệ từ MS Project bằng Aspose.Tasks
url: /vi/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lấy tiền tệ từ MS Project bằng Aspose.Tasks

## Giới thiệu
Nếu bạn đang tự hỏi **how to get currency** từ một tệp Microsoft Project, bạn đã đến đúng nơi. Trong hướng dẫn toàn diện này, bạn sẽ khám phá **how to work with ms project currency** bằng cách sử dụng thư viện Aspose.Tasks cho Java. Cho dù bạn đang xây dựng công cụ báo cáo, tiện ích di chuyển, hoặc chỉ cần đọc cài đặt tiền tệ từ một **java project file**, hướng dẫn này sẽ dẫn bạn qua mọi bước — từ việc tải tệp *.mpp* đến việc trích xuất các chữ số tiền tệ. Khi hoàn thành, bạn sẽ tự tin xử lý dữ liệu tiền tệ của ms project trong các ứng dụng của mình.

## Câu trả lời nhanh
- **What library reads MS Project files?** Aspose.Tasks for Java.  
- **How many lines of code to get currency digits?** Just three concise lines after the project is loaded.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 or higher (any JDK that runs Aspose.Tasks).  
- **Can I retrieve other Project properties?** Yes – Aspose.Tasks exposes a full set of Project fields (e.g., start date, cost rates, etc.).

## ms project currency là gì?
`ms project currency` đề cập đến độ chính xác số (số chữ số thập phân) mà Microsoft Project sử dụng khi hiển thị các giá trị tiền tệ. Nó được lưu trong tệp Project dưới dạng thuộc tính **CURRENCY_DIGITS** và xác định liệu các khoản tiền có hiển thị dưới dạng số nguyên, một chữ thập phân, hai chữ thập phân, v.v.

## Tại sao nên sử dụng Aspose.Tasks để xử lý ms project currency?
- **No Microsoft Project installation required** – work directly with *.mpp* files on any platform that supports Java.  
- **Strong type safety** – the API returns strongly‑typed values, reducing parsing errors.  
- **Performance‑optimized** – load large projects quickly and extract only the fields you need.  
- **Cross‑platform** – run on Windows, Linux, or macOS without modification.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có những thứ sau:

1. **Java Development Environment** – JDK 8 or newer installed and configured.  
2. **Aspose.Tasks for Java** – download the latest JAR from the official site: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – you should be comfortable creating a Java project, adding external libraries, and running a `main` method.  

## Nhập khẩu các gói
Đầu tiên, nhập các lớp mà chúng ta sẽ cần.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Bước 1: Xác định thư mục dữ liệu
Xác định thư mục chứa **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối hoặc tương đối nơi `project.mpp` nằm.

## Bước 2: Tải tệp MPP
Bây giờ chúng ta sẽ xem **how to load mpp** files bằng cách sử dụng Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Đảm bảo tên tệp khớp chính xác; nếu không, một `IOException` sẽ được ném.

## Bước 3: Lấy chữ số tiền tệ
Với dự án đã được tải, việc trích xuất chữ số **ms project currency** chỉ cần một dòng lệnh:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
Lệnh này trả về một `Integer` đại diện cho số chữ số thập phân (ví dụ, `2` cho cent). Giá trị được in ra console, nhưng bạn cũng có thể lưu nó vào một biến để xử lý tiếp theo.

## Các vấn đề thường gặp & Mẹo
- **File not found** – double‑check the `dataDir` path and ensure the file name is correct, including the `.mpp` extension.  
- **Unsupported file version** – Aspose.Tasks supports Project 2000‑2024 formats; older or corrupted files may need conversion.  
- **License not set** – during development a trial works, but for production you must apply a valid license to avoid evaluation watermarks.

## Câu hỏi thường gặp

**Q: Can Aspose.Tasks handle other Project attributes besides currency digits?**  
A: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate various aspects of Project files, such as tasks, resources, and custom fields.

**Q: Is Aspose.Tasks suitable for enterprise‑level applications?**  
A: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade projects, offering high performance and scalability.

**Q: Does Aspose.Tasks support cross‑platform development?**  
A: Yes, you can use Aspose.Tasks for Java on any platform that supports the Java Runtime Environment (Windows, Linux, macOS).

**Q: Can I try Aspose.Tasks before purchasing?**  
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).

**Q: Where can I get support for Aspose.Tasks?**  
A: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kết luận
Bạn giờ đã biết **how to get currency** chữ số từ một tệp MS Project bằng Aspose.Tasks cho Java. Quy trình rất đơn giản: tải dự án, gọi `project.get(Prj.CURRENCY_DIGITS)`, và sử dụng kết quả trong ứng dụng của bạn. Hãy tự do khám phá các thuộc tính dự án khác theo cùng mẫu, và tích hợp logic này vào các giải pháp báo cáo hoặc di chuyển lớn hơn.

---

**Cập nhật lần cuối:** 2026-02-10  
**Kiểm tra với:** Aspose.Tasks for Java (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}