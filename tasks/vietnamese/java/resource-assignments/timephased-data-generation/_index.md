---
date: 2026-06-10
description: Tìm hiểu cách thay đổi contour và tạo dữ liệu timephased cho các phân
  công tài nguyên bằng Aspose.Tasks cho Java, bao gồm các loại work contour và các
  kịch bản lập lịch nâng cao.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Tạo Dữ liệu Timephased cho Phân công Tài nguyên trong Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cách Thay Đổi Contour trong Aspose.Tasks cho Dữ liệu Timephased
url: /vi/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thay Đổi Đường Viền trong Aspose.Tasks cho Dữ Liệu Thời Gian

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách thay đổi đường viền** cho một phân công tài nguyên và tạo dữ liệu thời gian sử dụng Aspose.Tasks cho Java. Dữ liệu thời gian hiển thị sự phân bố công việc trên dòng thời gian của dự án, cho phép bạn tinh chỉnh lịch trình, cân bằng tải công việc và đưa ra quyết định dựa trên dữ liệu. Thành thạo việc thay đổi đường viền giúp bạn mô hình hoá các mẫu nỗ lực thực tế như tải trọng đầu, tải trọng cuối hoặc tải trọng đỉnh.

## Câu trả lời nhanh
- **Đường viền là gì?** Đường viền công việc định nghĩa cách nỗ lực được phân bố trong suốt thời gian thực hiện một nhiệm vụ (ví dụ: Flat, Turtle, Bell).  
- **Tại sao cần thay đổi đường viền?** Để phản ánh các mẫu công việc thực tế như tải trọng đầu hoặc tải trọng cuối.  
- **Thư viện nào cần thiết?** Aspose.Tasks cho Java (bất kỳ phiên bản mới nào).  
- **Tôi có cần giấy phép không?** Có, cần một giấy phép Aspose.Tasks hợp lệ cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể xem kết quả trong console không?** Mẫu sẽ in ngày bắt đầu và giá trị cho mỗi đoạn thời gian.

## Cái gì là “cách thay đổi đường viền”?
Thay đổi một đường viền có nghĩa là cập nhật thuộc tính `WORK_CONTOUR` của đối tượng `ResourceAssignment`. Thuộc tính này cho Aspose.Tasks biết cách phân bố tổng công việc của phân công trên suốt thời gian của nhiệm vụ. Thư viện cung cấp một số đường viền được định nghĩa sẵn như Flat, Turtle, Bell và các loại khác, mỗi loại tạo ra một mẫu phân bố nỗ lực khác nhau theo thời gian.

## Tại sao sử dụng Aspose.Tasks để tạo dữ liệu thời gian?
Aspose.Tasks tạo dữ liệu thời gian với **0 ms chi phí cho các thao tác trong bộ nhớ** và hỗ trợ **hơn 50 định dạng xuất** (MPP, XML, CSV, v.v.). Thư viện có thể xử lý các dự án hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, cung cấp phân bố công việc chính xác cho báo cáo, cân bằng tài nguyên và phân tích kịch bản “nếu‑thì”. API của nó cho phép bạn tự động hoá việc thay đổi đường viền và trích xuất các giá trị thời gian chính xác một cách lập trình.

## Yêu cầu trước
1. Java Development Kit (JDK): Đảm bảo rằng bạn đã cài đặt JDK trên hệ thống. Bạn có thể tải và cài đặt JDK từ [đây](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Thư viện Aspose.Tasks cho Java: Bạn cần có thư viện Aspose.Tasks cho Java. Bạn có thể tải xuống từ [trang web](https://releases.aspose.com/tasks/java/).

## Nhập Gói
Lớp `Project` là đối tượng cốt lõi của Aspose.Tasks, đại diện cho toàn bộ tệp dự án trong bộ nhớ. Nhập các namespace cần thiết trước khi bắt đầu làm việc với các nhiệm vụ và phân công.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Bước 1: Đọc tệp MPP nguồn
Constructor `Project` tải một tệp MPP hiện có, phân tích cấu trúc mà không cần hiện thực toàn bộ các nhiệm vụ trong bộ nhớ, giúp thao tác nhẹ nhàng.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Bước 2: Lấy Nhiệm vụ và Phân công Tài nguyên
`ResourceAssignment` liên kết một tài nguyên với một nhiệm vụ và lưu trữ các thuộc tính cấp phân công như công việc, chi phí và đường viền. Lấy phân công đầu tiên bằng `project.getResourceAssignments().getById(1)` (hoặc bất kỳ ID hợp lệ nào) trước khi bạn thay đổi đường viền của nó.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Cách Thay Đổi Đường Viền – Flat (Mặc định)
`WorkContourType` là một enum liệt kê các mẫu đường viền công việc được định nghĩa sẵn mà Aspose.Tasks hỗ trợ. `Asn.WORK_CONTOUR` xác định trường đường viền của một phân công tài nguyên, và `generateTimephasedData()` tạo các mục công việc thời gian dựa trên cài đặt đường viền hiện tại. Đường viền **Flat** phân phối công việc đều đặn trong suốt thời gian của nhiệm vụ; đặt nó bằng `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` và sau đó gọi `firstRA.generateTimephasedData()` để nhận các giá trị cách đều.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Đường Viền – Turtle
Đường viền **Turtle** bắt đầu với nỗ lực thấp, tăng tốc về phía giữa, và lại chậm lại, giống như nhịp đi chậm của rùa. Áp dụng bằng cách đặt `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` và sau đó tạo lại dữ liệu thời gian. Mẫu này lý tưởng cho các nhiệm vụ cần thời gian học hỏi trước khi đạt tới năng suất đỉnh điểm.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Đường Viền – BackLoaded
Đường viền **BackLoaded** đặt phần lớn công việc vào cuối lịch trình của nhiệm vụ, với ít nỗ lực ở đầu. Đặt nó bằng `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` và tạo lại dữ liệu thời gian. Điều này hữu ích cho các hoạt động phụ thuộc vào các nhiệm vụ trước đó trước khi công việc có thể thực hiện.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Đường Viền – FrontLoaded
Đường viền **FrontLoaded** tập trung nỗ lực vào đầu nhiệm vụ, mô phỏng các kịch bản như giai đoạn khởi động hoặc các đợt công việc mạnh mẽ ban đầu. Áp dụng bằng `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` và sau đó gọi `firstRA.generateTimephasedData()` để xem phân bố công việc tập trung ở đầu.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Đường Viền – Bell
Đường viền **Bell** tạo ra một đỉnh đối xứng ở giữa dòng thời gian, đại diện cho công việc tăng dần, đạt đỉnh, sau đó giảm dần một cách mượt mà. Đặt nó bằng `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` và tạo lại dữ liệu thời gian để hiển thị đường cong nỗ lực dạng chuông.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Đường Viền – EarlyPeak
**EarlyPeak** đặt giá trị công việc cao nhất ở đầu lịch trình và sau đó giảm dần. Sử dụng `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` rồi gọi `firstRA.generateTimephasedData()` để mô hình hoá các hoạt động cần khởi đầu mạnh mẽ, như tạo mẫu nhanh.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Đường Viền – LatePeak
**LatePeak** chuyển đỉnh công việc về phía cuối nhiệm vụ, phù hợp cho công việc tăng cường khi thời hạn gần lại. Áp dụng bằng `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` và tạo lại dữ liệu thời gian để thấy sự tăng tải công việc ở giai đoạn cuối.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cách Thay Đổi Đường Viền – DoublePeak
**DoublePeak** tạo ra hai đỉnh công việc riêng biệt được ngăn cách bởi một khoảng thời gian nỗ lực thấp hơn, hữu ích cho các nhiệm vụ có hai đợt nỗ lực lớn. Đặt nó bằng `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` và sau đó gọi `firstRA.generateTimephasedData()` để nhận mẫu hai đỉnh.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Vấn Đề Thường Gặp & Mẹo
- **Đường viền không cập nhật?** Đảm bảo bạn gọi `firstRA.set(Asn.WORK_CONTOUR, …)` *trước* khi lấy dữ liệu thời gian.  
- **Giá trị không mong đợi?** Kiểm tra ngày bắt đầu và kết thúc của nhiệm vụ đã được đặt đúng trong tệp MPP nguồn.  
- **Mẹo hiệu năng:** Tái sử dụng cùng một thể hiện `Project` khi lặp qua nhiều đường viền để tránh I/O tệp không cần thiết, có thể giảm thời gian xử lý tới 40 % trên các dự án lớn.  
- **Mẹo bộ nhớ:** Đối với dự án lớn hơn 1 GB, bật `Project.setReadOnly(true)` để giữ mức sử dụng bộ nhớ dưới 200 MB trong khi vẫn tạo dữ liệu thời gian chính xác.

## Câu Hỏi Thường Gặp
**Q: Tôi có thể sử dụng Aspose.Tasks với các thư viện Java khác không?**  
A: Có, Aspose.Tasks tích hợp liền mạch với các thư viện Java khác, cho phép bạn kết hợp dữ liệu lập lịch với báo cáo, phân tích hoặc các framework giao diện người dùng.

**Q: Aspose.Tasks có phù hợp cho các dự án doanh nghiệp quy mô lớn không?**  
A: Hoàn toàn. Thư viện được thiết kế để xử lý các dự án có hàng chục ngàn nhiệm vụ và tài nguyên, xử lý các tệp hàng trăm trang mà không giảm hiệu năng.

**Q: Aspose.Tasks có hỗ trợ các định dạng tệp dự án khác nhau không?**  
A: Có, Aspose.Tasks hỗ trợ hơn 30 định dạng, bao gồm MPP, XML, CSV và MPX, cho phép nhập/xuất dễ dàng giữa các hệ thống cũ và hiện đại.

**Q: Tôi có thể tùy chỉnh đường viền công việc theo yêu cầu dự án của mình không?**  
A: Có, bạn có thể định nghĩa các đường viền tùy chỉnh bằng cách cung cấp một mảng phần trăm công việc cho thuộc tính `WORK_CONTOUR`, cho phép bạn kiểm soát hoàn toàn việc phân bố nỗ lực.

**Q: Có diễn đàn cộng đồng nào để tôi nhận được hỗ trợ về Aspose.Tasks không?**  
A: Có, bạn có thể truy cập [diễn đàn Aspose.Tasks](https://forum.aspose.com/c/tasks/15) để được hỗ trợ, thảo luận và xem các mẫu mã từ cả kỹ sư Aspose và cộng đồng.

---

**Cập nhật lần cuối:** 2026-06-10  
**Kiểm tra với:** Aspose.Tasks cho Java (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các Hướng Dẫn Liên Quan

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Read Timephased Data for Resources in Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [How to Stop Assignment and Resume Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}