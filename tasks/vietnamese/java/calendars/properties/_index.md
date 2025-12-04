---
date: 2025-12-04
description: Tìm hiểu cách thiết lập lịch dự án và quản lý các thuộc tính lịch MS
  Project trong Java bằng Aspose.Tasks. Hướng dẫn từng bước để hiển thị giờ làm việc
  của lịch và tùy chỉnh lịch trình.
language: vi
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách thiết lập Lịch dự án với Aspose.Tasks cho Java
url: /java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thiết lập Lịch dự án với Aspose.Tasks cho Java

## Introduction
Trong hướng dẫn này, bạn sẽ khám phá **cách thiết lập lịch dự án** một cách lập trình bằng thư viện Aspose.Tasks cho Java. Kiểm soát các thuộc tính lịch cho phép bạn **hiển thị giờ làm việc của lịch**, định nghĩa ngày làm việc tùy chỉnh, và đồng bộ lịch trình dự án của bạn với các ràng buộc thực tế. Chúng tôi sẽ hướng dẫn từng bước—từ việc thiết lập môi trường đến duyệt qua các lịch và đọc các thuộc tính của chúng—để bạn có thể tự tin quản lý các lịch MS Project trong ứng dụng của mình.

## Quick Answers
- **Câu hỏi: “thiết lập lịch dự án” có nghĩa là gì?** Nó có nghĩa là tạo hoặc cập nhật thời gian làm việc của lịch, lịch cơ sở và các loại ngày trong một tệp MS Project.  
- **Thư viện nào cần thiết?** Aspose.Tasks for Java (bất kỳ phiên bản mới nào).  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể hiển thị giờ làm việc của lịch không?** Có—bằng cách đọc từng `WeekDay` bạn có thể xuất giờ cho mỗi loại ngày.  
- **Liệu điều này có tương thích với Maven/Gradle không?** Hoàn toàn—thêm JAR Aspose.Tasks làm phụ thuộc.

## What Is a Project Calendar?
Lịch dự án xác định các ngày và giờ làm việc cho nhiệm vụ, nguồn lực và toàn bộ thời gian dự án. Trong MS Project, các lịch có thể kế thừa từ một lịch cơ sở, và mỗi loại ngày (ví dụ, **Standard**, **Non‑working**) có thể có thời gian làm việc riêng. Quản lý các cài đặt này một cách lập trình cho phép điều chỉnh lịch trình động mà không cần chỉnh sửa thủ công.

## Why Manage MS Project Calendar Programmatically?
- **Tự động hóa:** Điều chỉnh lịch cho nhiều dự án bằng một script duy nhất.  
- **Nhất quán:** Thực thi các chính sách thời gian làm việc trên toàn tổ chức.  
- **Tích hợp:** Đồng bộ lịch với các hệ thống bên ngoài (HR, ERP).  
- **Tầm nhìn:** Nhanh chóng **hiển thị giờ làm việc của lịch** để báo cáo hoặc gỡ lỗi.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- **Java Development Kit (JDK) 8+** được cài đặt và cấu hình `JAVA_HOME`.  
- **Thư viện Aspose.Tasks for Java** được tải xuống từ [trang tải xuống](https://releases.aspose.com/tasks/java/). Thêm JAR vào classpath của dự án hoặc các phụ thuộc Maven/Gradle.  

## Import Packages
First, import the core Aspose.Tasks classes that we’ll use throughout the tutorial:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
Define the folder that contains your project files. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
Working times are expressed in milliseconds. Defining reusable constants makes the code easier to read.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
Create a `Project` instance by loading an existing MS Project XML file (`.xml` or `.mpp`). This gives us access to all calendars stored in the file.

```java
Project project = new Project(dataDir + "project.xml");
```

## Step 4: Iterate Through Calendars and Display Working Hours
Now we loop through every calendar, print its unique identifier, name, base calendar, and the working hours for each day type. This demonstrates **how to set project calendar** values and also how to **display calendar working hours**.

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

### What This Code Does
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
- **Prints UID and name** – useful for identifying the calendar later.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`).  

## Common Issues and Solutions
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| `NullPointerException` on `cal.getBaseCalendar()` | Lịch là một lịch cơ sở tự nó (`isBaseCalendar()` trả về `true`). | Sử dụng kiểm tra ba ngôi như đã minh họa (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | Tệp dự án sử dụng đơn vị thời gian khác (ticks). | Xác minh định dạng tệp; Aspose.Tasks chuẩn hóa sang milliseconds, nhưng đảm bảo bạn đang tải đúng loại tệp. |
| Unable to locate `project.xml` | Đường dẫn `dataDir` không đúng. | Sử dụng đường dẫn tuyệt đối hoặc `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently Asked Questions

**Q: Tôi có thể sửa đổi các thuộc tính lịch một cách lập trình bằng Aspose.Tasks không?**  
A: Có, API cung cấp quyền đọc/ghi đầy đủ cho các lịch, cho phép bạn thêm, chỉnh sửa hoặc xóa thời gian làm việc, ngoại lệ và quan hệ lịch cơ sở.

**Q: Có bất kỳ giới hạn nào đối với việc tùy chỉnh lịch với Aspose.Tasks không?**  
A: Thư viện phản ánh đầy đủ các khả năng của Microsoft Project, vì vậy bạn có thể tùy chỉnh hầu hết mọi khía cạnh của lịch. Chỉ các phiên bản tệp Project rất cũ có thể gặp một số vấn đề tương thích nhỏ.

**Q: Tôi có thể tích hợp quản lý lịch vào các dự án Java hiện có không?**  
A: Chắc chắn. Chỉ cần thêm JAR Aspose.Tasks vào đường dẫn biên dịch và sử dụng các mẫu mã giống như trong hướng dẫn.

**Q: Aspose.Tasks có hỗ trợ các chức năng quản lý dự án khác ngoài quản lý lịch không?**  
A: Có, nó bao gồm nhiệm vụ, nguồn lực, phân công, cấu trúc, baseline và hơn thế nữa—làm cho nó trở thành giải pháp toàn diện cho tự động hoá dự án dựa trên Java.

**Q: Có hỗ trợ kỹ thuật cho các nhà phát triển sử dụng Aspose.Tasks không?**  
A: Có, Aspose cung cấp các diễn đàn chuyên biệt, hỗ trợ qua email và tài liệu chi tiết cho tất cả người dùng có giấy phép.

## Conclusion
Bằng cách theo dõi hướng dẫn này, bạn đã biết **cách thiết lập giá trị lịch dự án**, đọc và **hiển thị giờ làm việc của lịch**, và tích hợp các khả năng này vào bất kỳ ứng dụng Java nào sử dụng Aspose.Tasks. Điều này cho phép bạn tự động điều chỉnh lịch trình, thực thi các chính sách làm việc nhất quán, và xây dựng các giải pháp quản lý dự án phong phú hơn.

---

**Cập nhật lần cuối:** 2025-12-04  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}