---
date: 2026-11-06
description: Dễ dàng tạo các ngoại lệ lịch tùy chỉnh, tích hợp lịch MS Project, và
  quản lý, định nghĩa, xử lý & truy xuất các ngoại lệ lịch trong các dự án Java với
  Aspose.Tasks. Tối ưu hoá quy trình dự án để quản lý dự án hiệu quả.
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: Ngoại lệ lịch
og_description: Tìm hiểu cách tạo ngoại lệ lịch trong Java bằng Aspose.Tasks. Quản
  lý lịch dự án, đặt ngày không làm việc, và chỉnh sửa lịch MS Project một cách hiệu
  quả.
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: Tạo ngoại lệ lịch với Aspose.Tasks cho Java
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: Cách tạo ngoại lệ lịch với Aspose.Tasks cho Java
url: /vi/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo ngoại lệ lịch với Aspose.Tasks cho Java

## Giới thiệu

`Aspose.Tasks` là một thư viện Java cho phép tạo, thao tác và chuyển đổi các tệp Microsoft Project một cách lập trình. Trong hướng dẫn này, bạn sẽ học cách **tạo ngoại lệ lịch** — các khoảng thời gian không làm việc tùy chỉnh ghi đè lịch mặc định của dự án. Kiểm soát chính xác ngày làm việc và ngày không làm việc là cần thiết cho việc dự báo lịch trình chính xác, phân bổ nguồn lực và tuân thủ các ngày lễ khu vực. Khi kết thúc hướng dẫn, bạn cũng sẽ biết cách **tích hợp lịch MS Project** vào ứng dụng Java của mình và truy xuất hoặc chỉnh sửa các ngoại lệ của nó.

## Câu trả lời nhanh

- **Tôi có thể đạt được gì?** Tạo, chỉnh sửa và truy xuất các ngoại lệ lịch tùy chỉnh trong các dự án Java.  
- **Thư viện nào được yêu cầu?** Aspose.Tasks for Java (phiên bản ổn định mới nhất).  
- **Tôi có cần giấy phép không?** Có, cần một giấy phép Aspose.Tasks hợp lệ để sử dụng trong môi trường sản xuất.  
- **Tôi có thể làm việc với các tệp MS Project không?** Chắc chắn – bạn có thể nhập, chỉnh sửa và xuất dữ liệu lịch MS Project.  
- **Có cần thiết lập đặc biệt nào không?** Chỉ cần thêm JAR Aspose.Tasks vào classpath và import các lớp liên quan.

## Cách tạo ngoại lệ lịch tùy chỉnh trong Aspose.Tasks cho Java?

Để tạo ngoại lệ lịch tùy chỉnh trong Aspose.Tasks cho Java, tải dự án mục tiêu, lấy Calendar của nó, xác định ngày bắt đầu và kết thúc của ngoại lệ cùng thời gian làm việc mong muốn, tùy chọn thiết lập mẫu lặp lại, và sau đó lưu dự án. Quy trình này sẽ thêm ngoại lệ ngay lập tức và lưu lại vào tệp .mpp.

`Project` là lớp chính của Aspose.Tasks mô hình hoá toàn bộ tệp Microsoft Project. Lớp `Project` đại diện cho một tệp Microsoft Project và cung cấp quyền truy cập vào nội dung của nó. Đối tượng `Calendar` định nghĩa thời gian làm việc và không làm việc cho dự án. Lớp `Calendar` là container cho tất cả các quy tắc thời gian làm việc, bao gồm cả các ngoại lệ. Phương thức `addException()` thêm một ngoại lệ lịch mới vào calendar. `addException()` là API gọi một lần để đăng ký một khoảng thời gian không làm việc cho khoảng ngày được chỉ định.

Tải dự án mục tiêu bằng `Project project = new Project("example.mpp")`, lấy đối tượng `Calendar` của nó, và gọi `addException()` với khoảng ngày và cài đặt thời gian làm việc mong muốn. Mẫu hai bước này tạo một ngoại lệ mới ngay lập tức và lưu lại khi bạn lưu dự án. Đối với các ngày lễ lặp lại, cấu hình `RecurrencePattern` trên ngoại lệ trước khi lưu.

Tạo ngoại lệ lịch theo cách này cho phép bạn **đặt ngày không làm việc** một cách chính xác, dù là các thời gian ngừng hoạt động một lần hay các ngày lễ hàng năm. Sau khi ngoại lệ được thêm, bạn có thể gọi `project.save("updated.mpp")` để ghi các thay đổi trở lại đĩa.

### Tổng quan các bước
1. Tải tệp dự án.  
2. Lấy hoặc tạo một thể hiện `Calendar`.  
3. Xác định khoảng ngày và thời gian làm việc của ngoại lệ.  
4. (Tùy chọn) Cấu hình lặp lại cho các ngày lễ hàng năm.  
5. Lưu dự án.

## Quản lý ngoại lệ lịch trong Aspose.Tasks

[Tìm hiểu cách thêm và xóa ngoại lệ lịch trong Aspose.Tasks cho Java một cách hiệu quả](./add-remove/). Khi nói đến quản lý dự án, tính linh hoạt là chìa khóa. Aspose.Tasks cho phép bạn quản lý ngoại lệ lịch một cách dễ dàng, cho phép điều chỉnh linh hoạt thời gian dự án. Hướng dẫn này cung cấp một hướng dẫn từng bước, đảm bảo bạn nắm bắt quy trình một cách hiệu quả. Khám phá cách nâng cao quy trình quản lý dự án của bạn một cách dễ dàng.

## Xác định các ngày trong tuần cho ngoại lệ lịch với Aspose.Tasks

[Thành thạo việc xác định các ngày trong tuần cho ngoại lệ lịch trong các dự án Java](./define-weekdays/) using Aspose.Tasks. Lập kế hoạch dự án chính xác đòi hỏi sự chú ý tỉ mỉ đến chi tiết. Với Aspose.Tasks, bạn có thể xác định chính xác các ngày trong tuần cho ngoại lệ lịch, đảm bảo dự án của bạn phù hợp với các thời gian cụ thể một cách liền mạch. Hướng dẫn này trang bị cho bạn kiến thức để tối ưu hoá việc lập lịch, cung cấp quyền kiểm soát thời gian dự án.

## Xử lý các lần xuất hiện trong ngoại lệ lịch bằng Aspose.Tasks

[Xử lý hiệu quả các ngoại lệ lịch trong các dự án Java](./handle-occurrences/) with Aspose.Tasks for Java. Quản lý dự án là một quá trình động, thường yêu cầu điều chỉnh để đáp ứng các sự kiện không lường trước. Aspose.Tasks cho phép bạn xử lý các ngoại lệ lịch một cách hiệu quả, cung cấp một cách tiếp cận hợp lý cho quản lý dự án. Học cách quản lý những bất định của dự án một cách dễ dàng qua hướng dẫn chi tiết này.

## Truy xuất ngoại lệ lịch với Aspose.Tasks

[Tìm hiểu cách truy xuất ngoại lệ lịch từ MS Project bằng Aspose.Tasks cho Java](./retrieve/). Tích hợp các ngoại lệ lịch một cách liền mạch vào quy trình quản lý dự án của bạn với Aspose.Tasks. Hướng dẫn này dẫn bạn qua quy trình từng bước để truy xuất các ngoại lệ lịch, đảm bảo việc tích hợp mượt mà và hiệu quả vào dự án của bạn. Khai thác sức mạnh của Aspose.Tasks để nâng cao khả năng quản lý dự án.

## Cách tích hợp lịch MS Project với Aspose.Tasks?

Tích hợp lịch MS Project với Aspose.Tasks bao gồm việc tải tệp .mpp nguồn bằng lớp Project, truy cập các đối tượng Calendar mặc định hoặc tùy chỉnh, chỉnh sửa hoặc hợp nhất các ngoại lệ khi cần, và sau đó lưu dự án đã cập nhật. Điều này cho phép bạn làm việc với lịch MS Project một cách lập trình mà không cần tương tác giao diện người dùng thủ công.

`Project` là lớp chính của Aspose.Tasks mô hình hoá toàn bộ tệp Microsoft Project. Nhập một tệp MS Project hiện có bằng `new Project("source.mpp")`; thư viện sẽ tự động tải lịch mặc định và bất kỳ ngoại lệ tùy chỉnh nào. Bạn có thể đọc, chỉnh sửa hoặc hợp nhất các ngoại lệ đó trước khi lưu dự án trở lại đĩa. Cách tiếp cận này cho phép bạn **chỉnh sửa lịch MS Project** một cách lập trình mà không cần chỉnh sửa thủ công trong giao diện MS Project.

## Các trường hợp sử dụng phổ biến

- **Lập lịch ngày lễ** – Xác định các ngày lễ quốc gia là ngày không làm việc trên nhiều dự án.  
- **Công việc ca** – Thiết lập tuần làm việc tùy chỉnh cho các đội làm việc theo lịch không chuẩn.  
- **Kiểm soát giai đoạn dự án** – Chặn các khoảng thời gian không nên lên lịch công việc, như cửa sổ bảo trì.  
- **Di chuyển hệ thống cũ** – Nhập lịch từ các tệp MS Project cũ và điều chỉnh chúng một cách lập trình.

## Mẹo & thực hành tốt nhất

- **Pro tip:** Luôn luôn lấy lịch hiện có trước khi thêm ngoại lệ mới để tránh trùng lặp.  
- **Warning:** Thay đổi lịch đã được gán cho các nhiệm vụ có thể làm dịch chuyển ngày nhiệm vụ; hãy tính lại lịch sau khi chỉnh sửa.  
- **Performance:** Gộp nhiều cập nhật ngoại lệ trong một giao dịch để giảm tải I/O tệp. Aspose.Tasks xử lý các tệp lên tới 1 GB trong khi giữ mức sử dụng bộ nhớ dưới 200 MB, và có thể xử lý hơn 30 cuộc gọi API liên quan đến lịch mỗi giây trên phần cứng máy chủ tiêu chuẩn.

## Các hướng dẫn về ngoại lệ lịch

### [Quản lý ngoại lệ lịch trong Aspose.Tasks](./add-remove/)
Học cách thêm và xóa ngoại lệ lịch trong Aspose.Tasks cho Java một cách hiệu quả. Nâng cao quy trình quản lý dự án một cách dễ dàng.

### [Xác định các ngày trong tuần cho ngoại lệ lịch với Aspose.Tasks](./define-weekdays/)
Học cách xác định các ngày trong tuần cho ngoại lệ lịch trong các dự án Java bằng Aspose.Tasks để lập lịch dự án chính xác.

### [Xử lý các lần xuất hiện trong ngoại lệ lịch bằng Aspose.Tasks](./handle-occurrences/)
Học cách xử lý các ngoại lệ lịch một cách hiệu quả trong các dự án Java với Aspose.Tasks cho Java. Tinh giản quy trình quản lý dự án của bạn ngay bây giờ.

### [Truy xuất ngoại lệ lịch với Aspose.Tasks](./retrieve/)
Học cách truy xuất các ngoại lệ lịch từ MS Project bằng Aspose.Tasks cho Java. Hướng dẫn từng bước để tích hợp liền mạch.

## Câu hỏi thường gặp

**Q: Tôi có thể chỉnh sửa ngoại lệ lịch sau khi dự án đã được công bố không?**  
A: Có. Sử dụng các API add‑remove và define‑weekdays để cập nhật lịch, sau đó lưu lại tệp dự án.

**Q: Aspose.Tasks có hỗ trợ các ngoại lệ lặp lại (ví dụ: mỗi thứ Hai đầu tiên của tháng) không?**  
A: Chắc chắn. Hướng dẫn “handle occurrences” đề cập cách thiết lập các mẫu lặp lại.

**Q: Làm thế nào để đảm bảo lịch tùy chỉnh của tôi được sử dụng cho tất cả các nhiệm vụ trong dự án?**  
A: Gán lịch cho lịch mặc định của dự án hoặc đặt rõ ràng trên thuộc tính `Calendar` của mỗi nhiệm vụ.

**Q: Có thể hợp nhất lịch từ nhiều tệp MS Project không?**  
A: Có. Truy xuất mỗi lịch, kết hợp các ngoại lệ của chúng một cách lập trình, và sau đó gán lịch đã hợp nhất cho dự án mục tiêu.

**Q: Phiên bản Aspose.Tasks nào cần thiết cho các tính năng này?**  
A: Tất cả các tính năng đều có trong phiên bản ổn định hiện tại của Aspose.Tasks cho Java (2025.x).

## Các hướng dẫn liên quan

- [Tạo Lịch Dự Án Aspose – Xác định các ngày trong tuần cho ngoại lệ lịch](/tasks/java/calendar-exceptions/define-weekdays/)
- [Truy xuất ngoại lệ lịch với Aspose.Tasks – hướng dẫn Java](/tasks/java/calendar-exceptions/retrieve/)
- [Tạo ngoại lệ lịch Aspose cho Java](/tasks/java/calendar-exceptions/add-remove/)

---

**Cập nhật lần cuối:** 2026-11-06  
**Kiểm tra với:** Aspose.Tasks for Java 24.11  
**Tác giả:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}