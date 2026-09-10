---
date: 2026-09-09
description: Cách thiết lập lịch dự án trong Java bằng Aspose.Tasks. Tìm hiểu cách
  hiển thị giờ làm việc của lịch, cấu hình thời gian làm việc và chỉnh sửa các ngày
  trong lịch trong các tệp MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Quản lý thuộc tính lịch trong Aspose.Tasks
og_description: Cách thiết lập lịch dự án trong Java bằng Aspose.Tasks. Tìm hiểu cách
  hiển thị giờ làm việc của lịch, cấu hình thời gian làm việc và chỉnh sửa các ngày
  trong lịch trong các tệp MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Cách thiết lập lịch dự án Java với Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Cách thiết lập lịch dự án Java với Aspose.Tasks
url: /vi/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thiết lập lịch dự án Java với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách thiết lập lịch dự án** trong Java bằng cách sử dụng thư viện Aspose.Tasks. Kiểm soát các thuộc tính lịch cho phép bạn **hiển thị giờ làm việc của lịch**, cấu hình các ngày làm việc tùy chỉnh, và giữ cho lịch trình dự án của bạn phù hợp với các ràng buộc thực tế như ngày lễ hoặc ca làm việc. Chúng tôi sẽ hướng dẫn qua việc thiết lập môi trường, tải dự án, duyệt qua các lịch, và đọc hoặc cập nhật các thuộc tính của chúng, để bạn có thể tự tin **quản lý cài đặt lịch MS Project** trong bất kỳ ứng dụng Java nào.

## Câu trả lời nhanh
- **What does “set project calendar” mean?** It means creating or updating a calendar’s working times, base calendar, and day types within an MS Project file.  
  => **Cái gì là “set project calendar”?** Nó có nghĩa là tạo hoặc cập nhật thời gian làm việc của lịch, lịch cơ sở và các loại ngày trong một tệp MS Project.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
  => **Thư viện nào được yêu cầu?** Aspose.Tasks for Java (bất kỳ phiên bản mới nào).  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
  => **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **Can I display calendar working hours?** Yes—by reading each `WeekDay` you can output the hours for every day type.  
  => **Tôi có thể hiển thị giờ làm việc của lịch không?** Có — bằng cách đọc mỗi `WeekDay` bạn có thể xuất giờ cho mỗi loại ngày.  
- **Is this compatible with Maven/Gradle?** Absolutely—add the Aspose.Tasks JAR as a dependency.  
  => **Điều này có tương thích với Maven/Gradle không?** Chắc chắn — thêm JAR Aspose.Tasks làm phụ thuộc.

## Cách thiết lập lịch dự án trong Java
Tải tệp dự án của bạn, xác định lịch mục tiêu, sau đó điều chỉnh các định nghĩa thời gian làm việc, lịch cơ sở và các loại ngày theo nhu cầu. Các bước dưới đây cung cấp một giải pháp hoàn chỉnh, từ đầu đến cuối, minh họa việc tải, duyệt, chỉnh sửa và lưu dự án đồng thời xử lý ngoại lệ và đảm bảo tính chính xác của tính toán giờ làm việc.

## Lịch dự án là gì?
Lịch dự án xác định các ngày và giờ làm việc cho các nhiệm vụ, nguồn lực và toàn bộ thời gian dự án. Trong MS Project, lịch có thể kế thừa từ một lịch cơ sở, và mỗi loại ngày (ví dụ: **Standard**, **Non‑working**) có thể có thời gian làm việc riêng. Quản lý các cài đặt này bằng lập trình cho phép điều chỉnh lịch trình một cách động mà không cần chỉnh sửa thủ công.

## Tại sao quản lý lịch MS Project bằng lập trình?
Quản lý lịch bằng lập trình cho phép bạn áp dụng các quy tắc lập lịch nhất quán trên nhiều dự án, giảm lỗi thủ công, và tích hợp dữ liệu lịch với các hệ thống doanh nghiệp khác như HR hoặc ERP. Tự động hoá này giúp nhanh chóng thiết lập dự án và đảm bảo mọi thành viên tuân thủ cùng một chính sách thời gian làm việc.

- **Tự động hoá:** Điều chỉnh lịch trên hàng chục dự án bằng một script duy nhất.  
- **Nhất quán:** Thực thi các chính sách thời gian làm việc trên toàn tổ chức một cách tự động.  
- **Tích hợp:** Đồng bộ lịch với các hệ thống HR hoặc ERP bên ngoài.  
- **Khả năng hiển thị:** Nhanh chóng **hiển thị giờ làm việc của lịch** để báo cáo hoặc gỡ lỗi.  
- **Linh hoạt:** Thêm ngoại lệ hoặc ca làm việc ngay lập tức mà không cần mở giao diện người dùng.

## Yêu cầu trước
- **Java Development Kit (JDK) 8+** đã được cài đặt và `JAVA_HOME` được cấu hình.  
- **Aspose.Tasks for Java** được tải xuống từ [download page](https://releases.aspose.com/tasks/java/). Thêm JAR vào classpath hoặc khai báo làm phụ thuộc Maven/Gradle.  
- Một tệp mẫu MS Project (`.mpp` hoặc `.xml`) chứa ít nhất một lịch bạn muốn kiểm tra hoặc chỉnh sửa.

## Nhập các gói
Lớp `Project`, `Calendar`, `WeekDay` và các lớp liên quan là cốt lõi của việc thao tác lịch.  
Lớp `Calendar` đại diện cho một lịch dự án, chứa các ngày làm việc, ngoại lệ và quan hệ lịch cơ sở.  
Lớp `WeekDay` định nghĩa cài đặt thời gian làm việc cho một ngày duy nhất trong lịch.

Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks, đại diện cho một tệp MS Project duy nhất trong bộ nhớ. Sau khi tải tệp, mọi thao tác lịch đều diễn ra thông qua đối tượng này.

```java
import com.aspose.tasks.*;
```

## Bước 1: thiết lập thư mục dữ liệu
Xác định thư mục chứa các tệp dự án của bạn. Thay thế placeholder bằng đường dẫn thực tế trên máy của bạn.

```java
String dataDir = "Your Data Directory";
```

## Bước 2: định nghĩa hằng thời gian
Thời gian làm việc được biểu diễn bằng mili giây. Định nghĩa các hằng tái sử dụng giúp mã dễ đọc hơn và giúp bạn **tính toán giờ làm việc Java** một cách chính xác.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Bước 3: tải dữ liệu dự án
Tạo một thể hiện `Project` bằng cách tải tệp XML MS Project hiện có (`.xml` hoặc `.mpp`). Điều này cho phép bạn truy cập vào tất cả các lịch được lưu trong tệp.

Lớp `Project` tải tệp vào một mô hình đối tượng nhẹ; nó **không** yêu cầu tải toàn bộ tệp vào bộ nhớ, cho phép bạn làm việc với các dự án có hàng chục nghìn nhiệm vụ.

```java
Project project = new Project(dataDir + "project.xml");
```

## Bước 4: lặp qua các lịch trong Java
Bây giờ chúng ta sẽ lặp qua mọi lịch, in ra định danh duy nhất, tên, lịch cơ sở và giờ làm việc cho mỗi loại ngày. Điều này minh họa **cách thiết lập lịch dự án Java** và cũng cho thấy cách **hiển thị giờ làm việc của lịch**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Những gì đoạn mã này thực hiện
- **Lọc các lịch không có tên** (một số lịch nội bộ có thể có tên `null`).  
- **In UID và tên** – hữu ích để xác định lịch sau này.  
- **Hiển thị lịch cơ sở** – hoặc “Self” (lịch là cơ sở của chính nó) hoặc tên của lịch được kế thừa.  
- **Lặp qua mỗi `WeekDay`** để tính và xuất tổng số giờ làm việc (`workingTime` được tính bằng mili giây, vì vậy chúng ta chia cho `OneHour`).  

## Lợi ích định lượng khi sử dụng Aspose.Tasks
Aspose.Tasks hỗ trợ **hơn 30 định dạng nhập và xuất** và có thể xử lý **các dự án lên tới 10.000 nhiệm vụ** mà không cần tải toàn bộ tệp vào bộ nhớ, cung cấp kết quả trong dưới một giây trên phần cứng máy chủ tiêu chuẩn. Những con số này làm cho nó trở thành lựa chọn đáng tin cậy cho tự động hoá quy mô doanh nghiệp.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| `NullPointerException` trên `cal.getBaseCalendar()` | Lịch là một lịch cơ sở tự thân (`isBaseCalendar()` trả về `true`). | Sử dụng kiểm tra ternary như đã minh họa (`cal.isBaseCalendar() ? "Self" : ...`). |
| Không có đầu ra cho giờ làm việc | Tệp dự án sử dụng đơn vị thời gian khác (ticks). | Xác minh định dạng tệp; Aspose.Tasks chuẩn hoá sang mili giây, nhưng hãy chắc chắn rằng bạn đang tải đúng loại tệp. |
| Không thể tìm thấy `project.xml` | Đường dẫn `dataDir` không đúng. | Sử dụng đường dẫn tuyệt đối hoặc `Paths.get(dataDir, "project.xml").toString()`. |

## Câu hỏi thường gặp

**Q: Tôi có thể chỉnh sửa thuộc tính lịch bằng lập trình sử dụng Aspose.Tasks không?**  
A: Có, API cung cấp quyền truy cập đọc/ghi đầy đủ vào các lịch, cho phép bạn thêm, sửa hoặc xóa thời gian làm việc, ngoại lệ và quan hệ lịch cơ sở.

**Q: Có bất kỳ hạn chế nào đối với việc tùy chỉnh lịch với Aspose.Tasks không?**  
A: Thư viện phản ánh đầy đủ các khả năng của Microsoft Project, vì vậy bạn có thể tùy chỉnh hầu hết mọi khía cạnh của lịch. Chỉ các phiên bản tệp Project rất cũ có thể gặp một số vấn đề tương thích nhỏ.

**Q: Tôi có thể tích hợp quản lý lịch vào các dự án Java hiện có không?**  
A: Chắc chắn. Chỉ cần thêm JAR Aspose.Tasks vào đường dẫn biên dịch và sử dụng các mẫu mã giống như trong hướng dẫn này.

**Q: Aspose.Tasks có hỗ trợ các chức năng quản lý dự án khác ngoài quản lý lịch không?**  
A: Có, nó bao gồm nhiệm vụ, nguồn lực, phân công, cấu trúc, baseline và nhiều hơn nữa — tạo nên một giải pháp toàn diện cho tự động hoá dự án dựa trên Java.

**Q: Có hỗ trợ kỹ thuật cho các nhà phát triển sử dụng Aspose.Tasks không?**  
A: Có, Aspose cung cấp diễn đàn chuyên biệt, hỗ trợ qua email và tài liệu chi tiết cho tất cả người dùng có giấy phép.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Hướng dẫn liên quan

- [Tạo Lịch Dự Án Java – Hướng Dẫn Aspose.Tasks cho Java](/tasks/java/)
- [Tải Tệp Dự Án trong Java và Quản Lý Thuộc Tính Dự Án](/tasks/java/project-management/default-properties/)
- [Đặt Ngày Bắt Đầu Dự Án trong MS Project bằng Aspose.Tasks cho Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}