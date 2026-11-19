---
date: 2026-11-19
description: Tìm hiểu cách tạo lịch tùy chỉnh Java bằng cách sử dụng Aspose.Tasks.
  Hướng dẫn này chỉ cho bạn cách xác định ngày làm việc, thiết lập giờ làm việc và
  chỉnh sửa lịch MS Project bằng lập trình.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Lịch
og_description: Tìm hiểu cách tạo lịch tùy chỉnh Java với Aspose.Tasks. Thành thạo
  việc xác định ngày làm việc, thiết lập giờ làm việc và chỉnh sửa lịch MS Project
  một cách hiệu quả.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Cách tạo lịch tùy chỉnh Java với Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Cách tạo lịch tùy chỉnh Java với Aspose.Tasks
url: /vi/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lịch

## Giới thiệu

Nếu bạn là một nhà phát triển Java muốn **tạo các giải pháp lịch tùy chỉnh Java**, bạn đã đến đúng nơi. Trung tâm này tập hợp tất cả các hướng dẫn Aspose.Tasks cho Java minh họa cách **định nghĩa ngày làm việc trong MS Project**, **đặt giờ làm việc trong MS Project**, và điều chỉnh cài đặt lịch một cách lập trình. Dù bạn đang xây dựng một công cụ lập lịch mới hay mở rộng một kế hoạch hiện có, việc thành thạo các API này cho phép bạn kiểm soát chính xác các mẫu ngày làm việc, ngày nghỉ lễ và ca làm việc tùy chỉnh—mà không cần mở giao diện MS Project.

## Câu trả lời nhanh
- **Mục đích chính của việc định nghĩa các ngày trong tuần là gì?**  
  Để thông báo cho MS Project biết ngày nào là ngày làm việc và giờ làm việc của chúng là bao nhiêu.  
- **Thư viện nào xử lý việc định nghĩa ngày trong tuần trong Java?**  
  Aspose.Tasks for Java cung cấp một API fluent để thao tác lịch.  
- **Tôi có cần giấy phép không?**  
  Giấy phép đánh giá miễn phí hoạt động cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể định nghĩa nhiều lịch cho các nhóm khác nhau không?**  
  Có – mỗi dự án có thể chứa nhiều lịch, mỗi lịch có cài đặt ngày trong tuần riêng.  
- **Có dự án mẫu để bắt đầu không?**  
  Hướng dẫn “Define Weekdays in Calendar” được liên kết bên dưới bao gồm một ví dụ sẵn sàng chạy.

## Cách tạo lịch tùy chỉnh Java?

Tải một dự án, tạo hoặc lấy một lịch, thêm các định nghĩa ngày trong tuần, và lưu tệp—tất cả chỉ trong một vài lời gọi API. Cách tiếp cận này loại bỏ các bước thao tác UI thủ công, cho phép bạn tự động tạo lịch cho hàng chục dự án và đảm bảo các mẫu ngày làm việc nhất quán trong toàn tổ chức.

## Lớp Project là gì?

Lớp `Project` là đối tượng trung tâm để tải, chỉnh sửa và lưu các tệp MS Project. Nó chứa các bộ sưu tập nhiệm vụ, nguồn lực và lịch, cung cấp các phương thức cho phép bạn đọc và sửa đổi mọi khía cạnh của dự án một cách lập trình. Sử dụng lớp này, bạn có thể truy cập bộ sưu tập lịch của dự án, điều chỉnh thời gian làm việc và ghi lại các thay đổi trở lại tệp MPP hoặc XML.

## Làm thế nào để định nghĩa các ngày trong tuần trong lịch MS Project?

Lớp `Project` đại diện cho một tệp MS Project và cung cấp quyền truy cập vào các cấu trúc dữ liệu của nó. Đối tượng `Calendar` lưu trữ các định nghĩa thời gian làm việc và các ngoại lệ cho một dự án. Tải dự án của bạn bằng `new Project("myproject.mpp")`, lấy (hoặc tạo) một đối tượng `Calendar`, sau đó gọi `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Dòng lệnh duy nhất này tạo một mục ngày làm việc thứ Hai với ca 8 giờ. Lặp lại cho các ngày khác và cuối cùng lưu dự án bằng `project.save("updated.mpp")`. Mẫu ngắn gọn này cho phép bạn định nghĩa, sửa đổi hoặc xóa các ngày trong tuần chỉ với vài lời gọi API, loại bỏ nhu cầu tương tác UI thủ công.

## Đối tượng WeekDay là gì?

Đối tượng `WeekDay` đại diện cho một mục ngày trong tuần trong lịch. Nó lưu trữ thông tin ngày có phải là ngày làm việc hay không, các khoảng thời gian làm việc cho ngày đó và các cờ cho hành vi mặc định. Bạn có thể gắn một hoặc nhiều khoảng `WorkingTime` để mô hình hoá ca làm việc chia đoạn, đặt ngày là không làm việc, hoặc kế thừa mặc định từ lịch cha.

## Cách định nghĩa ngày làm việc trong MS Project?

Bạn định nghĩa ngày làm việc bằng cách thêm các đối tượng `WeekDay` vào bộ sưu tập `WeekDays` của một lịch. Mỗi `WeekDay` chỉ định ngày có phải là ngày làm việc và các khoảng thời gian được coi là thời gian làm việc. Ví dụ, để làm cho thứ Bảy là nửa ngày, thêm một `WeekDay` với một `WorkingTime` duy nhất từ 10:00 đến 14:00. API sẽ tự động cập nhật các tính toán lịch của dự án.

## Cách đặt giờ làm việc trong MS Project?

Đặt giờ làm việc bằng cách tạo một hoặc nhiều khoảng `WorkingTime` cho mỗi `WeekDay`. Một `WorkingTime` nhận các giá trị giờ‑bắt đầu, phút‑bắt đầu, giờ‑kết thúc và phút‑kết thúc. Bạn có thể gán nhiều khoảng cho một ngày để mô hình hoá ca làm việc chia đoạn (ví dụ: 08:00‑12:00 và 13:00‑17:00). Sau khi cấu hình tất cả các ngày trong tuần, gọi `project.save(...)` để lưu các thay đổi.

## Tại sao nên sử dụng Aspose.Tasks cho Java để định nghĩa các ngày trong tuần?

- **Kiểm soát API đầy đủ** – Không có giới hạn giao diện; bạn có thể tạo, sửa đổi hoặc xóa các mục ngày trong tuần một cách lập trình.  
- **Đa nền tảng** – Hoạt động trên bất kỳ môi trường tương thích JVM nào, từ ứng dụng desktop đến dịch vụ đám mây.  
- **Độ chính xác** – Đặt thời gian làm việc khác nhau cho mỗi ngày trong tuần, thêm ngoại lệ cho ngày lễ, và đồng bộ lịch giữa nhiều dự án.  
- **Hiệu năng** – Xử lý các dự án có tới 500+ nhiệm vụ và lịch chứa 100+ tuần mà không cần tải toàn bộ UI, đạt thời gian chuyển đổi dưới 2 giây trên máy chủ tiêu chuẩn 2.5 GHz (khẳng định dựa trên benchmark của Aspose).  
- **Hỗ trợ đa định dạng** – Aspose.Tasks hỗ trợ hơn 30 API liên quan đến lịch và có thể nhập/xuất hơn 20 định dạng tệp, giúp tích hợp liền mạch với các pipeline dữ liệu dự án hiện có.

## Yêu cầu trước
- Java 8 hoặc cao hơn đã được cài đặt.  
- Thư viện Aspose.Tasks for Java (tải từ trang web Aspose hoặc thêm qua Maven/Gradle).  
- Giấy phép Aspose.Tasks hợp lệ (giấy phép đánh giá đủ cho việc học).

## Quản lý thuộc tính lịch MS Project trong Aspose.Tasks

Mở khóa tiềm năng đầy đủ của việc quản lý thuộc tính lịch MS Project trong Java với Aspose.Tasks. Hướng dẫn của chúng tôi sẽ đưa bạn qua các chi tiết của quản lý lịch, cung cấp những hiểu biết quý giá về tùy chỉnh và tối ưu hoá. Từ việc điều chỉnh giờ làm việc đến việc định nghĩa các ngày đặc biệt, bạn sẽ thành thạo mọi khía cạnh.

Sẵn sàng kiểm soát thời gian dự án của mình? [Khám phá hướng dẫn tại đây](./properties/).

## Tạo lịch MS Project bằng Aspose.Tasks

Tiết kiệm thời gian quản lý dự án của bạn bằng việc tạo lịch MS Project sử dụng Aspose.Tasks cho Java. Hướng dẫn của chúng tôi đơn giản hoá quy trình, đảm bảo bạn có thể thiết lập các lịch phù hợp với nhu cầu riêng của dự án. Bước đầu tiên hướng tới lập kế hoạch và tổ chức dự án hiệu quả.

Sẵn sàng tạo lịch một cách dễ dàng? [Xem hướng dẫn](./create/).

## Định nghĩa các ngày trong tuần trong lịch với Aspose.Tasks

Tùy chỉnh lịch MS Project của bạn bằng cách định nghĩa các ngày trong tuần sử dụng Aspose.Tasks cho Java. Hướng dẫn này sẽ chỉ cho bạn cách điều chỉnh ngày làm việc và thời gian, mang lại sự linh hoạt cần thiết cho quản lý dự án thành công. Hãy để lịch của bạn làm việc cho bạn.

Sẵn sàng định nghĩa các ngày trong tuần một cách nhanh chóng? [Bắt đầu tại đây](./define-weekdays/).

Khi bạn duyệt qua các hướng dẫn này, bạn sẽ khám phá thêm các chủ đề về trích xuất giờ làm việc, tạo lịch chuẩn, đọc tuần làm việc và cập nhật lịch sang định dạng MPP. Mỗi hướng dẫn đều được thiết kế để cung cấp kiến thức thực tiễn, giúp bạn áp dụng ngay vào các dự án Java của mình.

## Lấy giờ làm việc từ lịch bằng Aspose.Tasks

Đơn giản hoá các nhiệm vụ quản lý dự án của bạn bằng cách trích xuất giờ làm việc từ lịch MS Project sử dụng Aspose.Tasks cho Java. Hướng dẫn này trang bị cho bạn kỹ năng tối ưu hoá thời gian dự án một cách hiệu quả.

Sẵn sàng trích xuất giờ làm việc một cách dễ dàng? [Khám phá hướng dẫn](./working-hours/).

## Tạo lịch chuẩn trong Aspose.Tasks

Nâng cao khả năng quản lý dự án của bạn bằng cách học cách tạo một lịch MS Project chuẩn trong Java với Aspose.Tasks. Hướng dẫn từng bước này đảm bảo bạn có thể triển khai một phương pháp chuẩn hoá cho thời gian dự án của mình.

Sẵn sàng tạo lịch chuẩn? [Xem hướng dẫn](./make-standard/).

## Đọc tuần làm việc từ lịch MS Project với Aspose.Tasks

Hiểu sâu về cách đọc tuần làm việc từ lịch MS Project sử dụng Aspose.Tasks cho Java. Hướng dẫn này cung cấp các chỉ dẫn chi tiết, giúp bạn quản lý lịch trình dự án một cách hiệu quả.

Sẵn sàng đọc tuần làm việc một cách dễ dàng? [Bắt đầu tại đây](./read-work-weeks/).

## Cập nhật lịch MS Project sang định dạng MPP với Aspose.Tasks

Cập nhật lịch MS Project sang định dạng MPP một cách dễ dàng bằng Aspose.Tasks cho Java. Hướng dẫn này cung cấp một cách tiếp cận liền mạch để đảm bảo dữ liệu dự án của bạn ở định dạng phù hợp cho khả năng tương thích tối ưu.

Sẵn sàng cập nhật lịch sang định dạng MPP? [Khám phá hướng dẫn](./update-to-mpp/).

Mở khóa tiềm năng đầy đủ của Aspose.Tasks cho Java và nâng cao kỹ năng quản lý dự án của bạn. Mỗi hướng dẫn được thiết kế để phù hợp với các nhà phát triển ở mọi cấp độ, đảm bảo trải nghiệm học tập suôn sẻ. Hãy khám phá và cách mạng hoá hành trình quản lý dự án Java của bạn ngay hôm nay!

## Hướng dẫn về Lịch
### [Quản lý thuộc tính lịch MS Project trong Aspose.Tasks](./properties/)
Tìm hiểu cách quản lý thuộc tính lịch MS Project trong Java bằng Aspose.Tasks. Hướng dẫn này cung cấp các bước chi tiết cho lịch trong các ứng dụng Java của bạn.
### [Tạo lịch MS Project bằng Aspose.Tasks](./create/)
Tìm hiểu cách tạo lịch MS Project bằng Aspose.Tasks cho Java. Đơn giản hoá quản lý dự án một cách dễ dàng.
### [Định nghĩa các ngày trong tuần trong lịch với Aspose.Tasks](./define-weekdays/)
Tìm hiểu cách định nghĩa các ngày trong tuần trong lịch MS Project bằng Aspose.Tasks cho Java. Tùy chỉnh ngày làm việc và thời gian một cách nhanh chóng.
### [Lấy giờ làm việc từ lịch bằng Aspose.Tasks](./working-hours/)
Trích xuất giờ làm việc từ lịch MS Project một cách dễ dàng với Aspose.Tasks cho Java. Đơn giản hoá các nhiệm vụ quản lý dự án.
### [Tạo lịch chuẩn trong Aspose.Tasks](./make-standard/)
Tìm hiểu cách tạo một lịch MS Project chuẩn trong Java sử dụng Aspose.Tasks. Nâng cao khả năng quản lý dự án của bạn với hướng dẫn từng bước này.
### [Đọc tuần làm việc từ lịch MS Project với Aspose.Tasks](./read-work-weeks/)
Tìm hiểu cách đọc tuần làm việc từ lịch MS Project sử dụng Aspose.Tasks cho Java. Nhận các hướng dẫn chi tiết trong tutorial toàn diện này.
### [Cập nhật lịch MS Project sang định dạng MPP một cách dễ dàng bằng Aspose.Tasks cho Java](./update-to-mpp/)
Tìm hiểu cách cập nhật lịch MS Project sang định dạng MPP một cách dễ dàng bằng Aspose.Tasks cho Java.

## Câu hỏi thường gặp

**Q: Tôi có thể định nghĩa giờ làm việc khác nhau cho mỗi ngày trong tuần không?**  
A: Có. Aspose.Tasks cho phép bạn đặt thời gian bắt đầu và kết thúc riêng biệt cho mỗi ngày từ Thứ Hai đến Chủ Nhật.

**Q: Làm thế nào để xử lý ngày lễ hoặc ngày không làm việc?**  
A: Sau khi định nghĩa các ngày trong tuần, bạn có thể thêm các ngoại lệ (ngày) để đánh dấu ngày lễ hoặc khoảng thời gian không làm việc tùy chỉnh.

**Q: Có thể sao chép định nghĩa ngày trong tuần từ một lịch sang lịch khác không?**  
A: Chắc chắn. Bạn có thể lấy đối tượng `WeekDay` từ một lịch hiện có và thêm nó vào một đối tượng lịch khác.

**Q: Tôi có cần tải lại dự án sau khi cập nhật các ngày trong tuần không?**  
A: Không. Các thay đổi được áp dụng trực tiếp lên đối tượng `Project` trong bộ nhớ; chỉ cần lưu dự án khi hoàn thành.

**Q: Phiên bản Aspose.Tasks nào cần thiết cho việc thao tác ngày trong tuần?**  
A: Tất cả các phiên bản gần đây (20.10 trở lên) đều hỗ trợ đầy đủ API ngày trong tuần. Chúng tôi khuyên bạn nên sử dụng bản phát hành ổn định mới nhất để đạt hiệu năng tốt nhất.

---

**Cập nhật lần cuối:** 2026-11-19  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thêm lịch vào dự án với Aspose.Tasks cho Java](/tasks/java/calendars/create/)
- [Xác định ngày làm việc & giờ làm việc với Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Tạo ngoại lệ lịch tùy chỉnh với Aspose.Tasks cho Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}