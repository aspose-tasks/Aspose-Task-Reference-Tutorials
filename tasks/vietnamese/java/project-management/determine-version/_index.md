---
date: 2026-05-31
description: Tìm hiểu cách lấy phiên bản dự án và truy xuất ngày lưu lần cuối từ các
  tệp MS Project bằng Aspose.Tasks cho Java. Hướng dẫn chi tiết từng bước kèm ví dụ
  mã.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Xác định phiên bản dự án với Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách lấy phiên bản dự án – Hướng dẫn Aspose.Tasks Java
url: /vi/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lấy phiên bản dự án – Hướng dẫn Aspose Tasks Java

Trong **hướng dẫn Aspose Tasks Java** này, bạn sẽ học **cách lấy phiên bản dự án** của một tệp Microsoft Project và cách **lấy ngày lưu cuối cùng** bằng cách sử dụng thư viện Aspose.Tasks cho Java. Biết được phiên bản tệp và thời gian lưu giúp bạn tránh các vấn đề tương thích, thực thi các chính sách di chuyển, và duy trì nhật ký kiểm toán chính xác. Chúng tôi sẽ hướng dẫn từng bước — từ thiết lập môi trường đến in ra phiên bản và ngày — để bạn có thể tích hợp kiểm tra này vào bất kỳ ứng dụng Java nào một cách tự tin.

## Câu trả lời nhanh
- **Mục tiêu của hướng dẫn này là gì?** Xác định phiên bản tệp MS Project và ngày lưu cuối cùng bằng Aspose.Tasks cho Java.  
- **Bạn có cần cài đặt Microsoft Project không?** Không, Aspose.Tasks hoạt động độc lập với Microsoft Project.  
- **Các định dạng tệp nào được hỗ trợ?** Các tệp Project dựa trên XML như MPP và XML được hỗ trợ đầy đủ.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 5‑10 phút cho một kiểm tra phiên bản cơ bản.  
- **Cần có giấy phép không?** Bản dùng thử miễn phí đủ cho việc đánh giá; cần giấy phép thương mại cho môi trường sản xuất.

## Aspose Tasks Java Tutorial là gì?
`Aspose.Tasks` Java tutorial là một hướng dẫn ngắn gọn, thực hành, cho thấy cách tương tác với dữ liệu Microsoft Project một cách lập trình. Nó chỉ cho bạn cách đọc, sửa đổi và phân tích thông tin dự án mà không cần cài đặt Microsoft Project trên máy chủ. Ngoài ra, nó còn bao gồm việc tải tệp, truy cập các thuộc tính và lưu thay đổi, cho phép các nhà phát triển tự động hoá các nhiệm vụ quản lý dự án một cách hiệu quả.

## Tại sao nên sử dụng Aspose.Tasks để xác định phiên bản dự án?
Aspose.Tasks cung cấp **siêu dữ liệu phiên bản chính xác** và **dấu thời gian lưu cuối cùng** khi chạy trên bất kỳ hệ điều hành nào hỗ trợ Java. Nó xử lý các tệp lên tới **500 trang trong vòng dưới 2 giây** trên CPU tiêu chuẩn 2.5 GHz, làm cho nó trở thành lựa chọn lý tưởng cho tự động hoá hàng loạt và các kịch bản di chuyển quy mô lớn.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – phiên bản 8 hoặc mới hơn.  
2. **Aspose.Tasks for Java JAR** – tải xuống từ [website](https://releases.aspose.com/tasks/java/) và thêm vào classpath của dự án.  
3. **MS Project file** – một tệp Project dựa trên XML (ví dụ, `input.xml`) mà bạn muốn kiểm tra.  

> **Mẹo chuyên nghiệp:** Lưu tệp Project trong thư mục `data` riêng để giữ đường dẫn gọn gàng và tránh ghi đè vô tình.

## Nhập các gói
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Cách thiết lập thư mục dự án
Để định vị đúng các tệp dự án của bạn, hãy tạo một thư mục riêng trong cấu trúc ứng dụng và lưu tất cả các tệp đầu vào ở đó. Điều này giữ cho mã sạch sẽ và tránh các lỗi liên quan đến đường dẫn khi tải tệp. Sử dụng tên biến rõ ràng cho đường dẫn thư mục, có thể là đường dẫn tuyệt đối hoặc tương đối so với thư mục gốc của dự án.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Thay thế `"Your Data Directory"` bằng đường dẫn tuyệt đối hoặc tương đối nơi `input.xml` nằm.

## Cách tải dự án
`Project` là đối tượng Aspose.Tasks chính đại diện cho một tệp Microsoft Project trong bộ nhớ, cho phép bạn truy cập vào tất cả các thuộc tính và bộ sưu tập của dự án. Sau khi tạo thể hiện `Project`, bạn có thể truy vấn các trường của nó, lặp qua các nhiệm vụ, hoặc sửa đổi dữ liệu trước khi lưu tệp trở lại đĩa.

```java
Project project = new Project(dataDir + "input.xml");
```

Nếu tệp của bạn có tên khác, hãy điều chỉnh `"input.xml"` cho phù hợp.

## Cách xác định phiên bản dự án
`Prj.SAVE_VERSION` là một thuộc tính cho biết số phiên bản của Microsoft Project đã lưu tệp. `Prj.LAST_SAVED` là một thuộc tính lưu trữ ngày và giờ khi tệp được lưu lần cuối. `Prj.SAVE_VERSION` trả về phiên bản số của ứng dụng Microsoft Project đã lưu tệp (ví dụ, 12 cho Project 2010). `Prj.LAST_SAVED` cung cấp ngày và giờ chính xác của lần lưu gần nhất.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

## Cách hiển thị kết quả
Sau khi lấy được thông tin phiên bản và ngày lưu cuối cùng, bạn thường muốn xuất chúng ra console hoặc tệp log. Sử dụng `System.out.println` để hiển thị các giá trị, định dạng ngày theo nhu cầu. Điều này xác nhận việc trích xuất thành công và cung cấp phản hồi ngay lập tức trong quá trình phát triển hoặc trong các script tự động.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| `NullPointerException` on `project.get(...)` | Không tìm thấy tệp hoặc đường dẫn không đúng | Kiểm tra `dataDir` và tên tệp; sử dụng đường dẫn tuyệt đối để thử nghiệm. |
| Số phiên bản không mong đợi (ví dụ, 0) | Đang tải một tệp XML không phải Project | Đảm bảo tệp là tệp Microsoft Project hợp lệ (MPP/XML). |
| License exception | Sử dụng bản dùng thử mà không có giấy phép hợp lệ trong môi trường sản xuất | Áp dụng giấy phép Aspose.Tasks của bạn (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks với các ngôn ngữ lập trình khác không?**  
A: Có, Aspose.Tasks hỗ trợ .NET, Java và C++ cùng các ngôn ngữ khác.

**Q: Aspose.Tasks có phù hợp cho các dự án quy mô lớn không?**  
A: Chắc chắn; nó có thể xử lý các dự án hàng trăm trang trong vài giây mà không cần tải toàn bộ tệp vào bộ nhớ.

**Q: Tôi có thể tùy chỉnh dữ liệu dự án bằng Aspose.Tasks không?**  
A: Có, bạn có thể sửa đổi các nhiệm vụ, nguồn lực, lịch và bất kỳ thành phần dự án nào khác thông qua API.

**Q: Aspose.Tasks có yêu cầu cài đặt Microsoft Project không?**  
A: Không, thư viện hoạt động độc lập và không cần Microsoft Project trên máy chủ.

**Q: Có hỗ trợ kỹ thuật cho Aspose.Tasks không?**  
A: Có, bạn có thể nhận trợ giúp từ diễn đàn Aspose.Tasks [tại đây](https://forum.aspose.com/c/tasks/15).

**Câu hỏi bổ sung**

**Q: Làm thế nào để tôi lấy các thuộc tính dự án khác (ví dụ, tác giả, công ty)?**  
A: Sử dụng `project.get(Prj.AUTHOR)` hoặc `project.get(Prj.COMPANY)` theo cách bạn lấy phiên bản.

**Q: Tôi có thể kiểm tra phiên bản của tệp MPP (nhị phân) không?**  
A: Có, Aspose.Tasks tải trực tiếp các tệp `.mpp`; thuộc tính `Prj.SAVE_VERSION` cũng hoạt động cho các định dạng nhị phân.

**Q: Có cách nào để nâng cấp một tệp dự án cũ lên phiên bản mới hơn bằng lập trình không?**  
A: Tải tệp cũ, sau đó lưu nó bằng `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks sẽ ghi tệp ở định dạng mới nhất theo mặc định.

## Kết luận
Bạn đã nắm vững **cách lấy phiên bản dự án** và **lấy ngày lưu cuối cùng** từ các tệp MS Project bằng Aspose.Tasks cho Java. Hãy tích hợp các đoạn mã này vào các pipeline tự động, công cụ báo cáo, hoặc tiện ích di chuyển để đảm bảo bạn luôn biết chính xác phiên bản Project đang xử lý.

---

**Cập nhật lần cuối:** 2026-05-31  
**Kiểm thử với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Đặt ngày bắt đầu dự án trong MS Project bằng Aspose.Tasks cho Java](/tasks/java/project-properties/write-project-info/)
- [Đọc cơ sở dữ liệu Microsoft Project bằng Aspose.Tasks cho Java](/tasks/java/project-data-reading/read-project-database/)
- [Lưu dự án dưới dạng mẫu, CSV và văn bản bằng Aspose.Tasks cho Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}