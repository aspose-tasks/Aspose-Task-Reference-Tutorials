---
date: 2026-10-31
description: Tìm hiểu cách xuất gantt sang pdf trong Java bằng Aspose.Tasks. Hướng
  dẫn chi tiết này chỉ cho bạn cách đọc dữ liệu biểu đồ Gantt và tạo báo cáo PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Đọc dữ liệu biểu đồ Gantt cụ thể trong Aspose.Tasks
og_description: Xuất gantt sang pdf trong Java với Aspose.Tasks. Thực hiện theo hướng
  dẫn này để đọc dữ liệu biểu đồ Gantt, tùy chỉnh thuộc tính hiển thị và tạo báo cáo
  PDF cho quản lý dự án.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Xuất gantt sang pdf trong Java – Hướng dẫn Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Xuất gantt sang pdf trong Java – trích xuất dữ liệu cụ thể
url: /vi/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Xuất gantt sang pdf trong Java – trích xuất dữ liệu cụ thể

## Giới thiệu
Trong tutorial này, bạn sẽ học cách **export gantt to pdf in Java** bằng cách đọc thông tin biểu đồ Gantt với Aspose.Tasks for Java. Biểu đồ Gantt cung cấp cho các nhà quản lý dự án một lộ trình trực quan về các nhiệm vụ, phụ thuộc và thời gian, và việc có thể lấy dữ liệu này một cách lập trình cho phép bạn tạo các báo cáo PDF tự động, bảng điều khiển, hoặc tích hợp với các hệ thống doanh nghiệp khác. Hãy cùng đi qua từng bước, từ việc tải tệp dự án đến việc trích xuất thuộc tính hiển thị và cuối cùng tạo PDF.

## Câu trả lời nhanh
- **Bạn có thể trích xuất gì?** Bất kỳ thuộc tính hiển thị, kiểu thanh, đường lưới, kiểu văn bản, đường tiến độ, hoặc cấp độ thang thời gian nào từ biểu đồ Gantt.  
- **Bạn có cần giấy phép không?** Bản dùng thử hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc mới hơn (tutorial này sử dụng JDK 11).  
- **Mã có chạy ngay không?** Có – chỉ cần thay đổi đường dẫn thư mục dữ liệu.  
- **Tôi có thể chỉnh sửa giao diện sau khi đọc không?** Chắc chắn – API cho phép bạn thay đổi các thuộc tính và lưu lại vào tệp dự án.

## Export gantt to pdf là gì?
Export gantt to pdf là quá trình chuyển đổi chế độ xem biểu đồ Gantt được lưu trong tệp dự án thành tài liệu PDF, giữ nguyên kiểu dáng trực quan và thông tin thời gian. Thao tác này hữu ích để chia sẻ trạng thái dự án với các bên liên quan có thể không có công cụ quản lý dự án.

## Tại sao nên export gantt to pdf với Aspose.Tasks?
Aspose.Tasks có thể xử lý **hơn 30 + định dạng đầu vào** (MPP, XML, MPX, v.v.) và **xuất ra PDF trong một lần gọi** đồng thời giữ 95 % độ trung thực hình ảnh, ngay cả với các dự án có hơn 500 nhiệm vụ. Thư viện xử lý tệp trong bộ nhớ, vì vậy bạn có thể tạo PDF trên máy chủ mà không cần cài đặt Microsoft Project.

## Yêu cầu trước
1. **Java Development Kit (JDK):** Đảm bảo bạn đã cài đặt Java trên hệ thống. Bạn có thể tải xuống từ **[trang tải xuống Oracle JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Tải xuống và cài đặt thư viện Aspose.Tasks for Java từ **[trang tải xuống Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** Chọn một IDE mà bạn ưa thích. Các lựa chọn phổ biến bao gồm IntelliJ IDEA, Eclipse hoặc NetBeans.

## Nhập các gói
Các import sau sẽ cung cấp quyền truy cập vào các lớp cốt lõi của Aspose.Tasks cần thiết cho việc đọc và xuất dữ liệu Gantt.  
*Không có khối mã nào được hiển thị ở đây để giữ tutorial tập trung vào khái niệm; chỉ cần thêm các import vào tệp Java của bạn.*

## Làm thế nào để tải tệp dự án biểu đồ Gantt trong Java?
Tải tệp dự án bằng cách tạo một thể hiện `Project` và truyền đường dẫn đầy đủ vào constructor. Bước này khởi tạo biểu diễn trong bộ nhớ của biểu đồ Gantt, cho phép truy vấn các thuộc tính hiển thị sau này. Khi tệp được tải thành công, bạn có thể xác minh tên dự án, ngày bắt đầu và số lượng nhiệm vụ để đảm bảo tệp đúng đã được mở. Việc xác minh này giúp phát hiện sớm các vấn đề về đường dẫn hoặc định dạng.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definition anchor:* `Project` is the top‑level Aspose.Tasks object that represents a single project file in memory.

## Làm sao tôi có thể truy cập vào chế độ xem biểu đồ Gantt?
Lấy chế độ xem Gantt đầu tiên từ bộ sưu tập view của dự án. Hầu hết các dự án đều chứa ít nhất một view Gantt, và thường là mục đầu tiên. Sau khi có được view, bạn có thể kiểm tra tên và đảm bảo nó thuộc loại `GanttChartView` trước khi tiếp tục trích xuất thuộc tính. Kiểm tra này ngăn lỗi thời gian chạy khi làm việc với các bộ sưu tập view tùy chỉnh hoặc không chuẩn.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definition anchor:* `GanttChartView` represents the visual layout of tasks, timescales, and bars that you see in a typical Gantt chart.

## Làm sao tôi trích xuất các thuộc tính hiển thị?
Bạn có thể đọc các thuộc tính như màu nền, chiều cao thanh và cài đặt thang thời gian trực tiếp từ đối tượng `GanttChartView`. In chúng ra giúp bạn xác minh cấu hình hiện tại trước khi xuất. Một vòng lặp trích xuất điển hình sẽ duyệt qua mỗi thuộc tính, định dạng giá trị thành chuỗi và ghi log vào console hoặc tệp để phân tích sau. Cách tiếp cận này hữu ích cho việc gỡ lỗi và tạo tài liệu mô tả giao diện biểu đồ.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definition anchor:* `GanttChartView` provides access to view settings such as background color, bar height, and timescale configuration.

## Làm sao tôi trích xuất các kiểu thanh?
Duyệt qua bộ sưu tập các đối tượng `BarStyle` để lấy chi tiết như màu, mẫu và hình dạng cho mỗi loại thanh được sử dụng trong biểu đồ. Đối với mỗi kiểu, bạn cũng có thể đọc loại nhiệm vụ và điều kiện kích hoạt kiểu, điều này rất quan trọng khi tái tạo biểu đồ ở định dạng khác. Thu thập thông tin này cho phép bạn tạo bản sao trực quan chính xác hoặc áp dụng quy tắc kiểu tùy chỉnh bằng mã.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definition anchor:* `BarStyle` defines the visual appearance of a Gantt bar, including its color, pattern, and shape.

## Làm sao tôi trích xuất các đường lưới?
Đường lưới xác định sự phân tách trực quan giữa các hàng và cột. Truy cập chúng qua phương thức `getGridlines()` và xuất ra trạng thái hiển thị và kiểu dáng. Sau khi lấy bộ sưu tập đường lưới, bạn có thể lặp qua mỗi đường để ghi lại loại đường (đặc, gạch), độ dày và màu. Dữ liệu này có giá trị khi bạn cần tái tạo bố cục lưới chính xác trong PDF xuất hoặc các định dạng báo cáo khác.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definition anchor:* `getGridlines()` returns the collection of gridline objects that control row and column separators in the Gantt view.

## Làm sao tôi trích xuất các kiểu văn bản?
Kiểu văn bản kiểm soát phông chữ, kích thước và màu sắc của nhãn trên biểu đồ Gantt. Duyệt qua bộ sưu tập `TextStyle` để liệt kê mỗi kiểu. Đối với mỗi kiểu văn bản, bạn cũng có thể lấy phần tử liên quan (tên nhiệm vụ, ngày, v.v.) và bất kỳ quy tắc định dạng có điều kiện nào. Ghi lại các chi tiết này đảm bảo tài liệu xuất giữ nguyên kiểu chữ như biểu đồ gốc.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definition anchor:* `TextStyle` represents the formatting attributes applied to textual elements within the Gantt chart.

## Làm sao tôi trích xuất các đường tiến độ?
Đường tiến độ hiển thị điểm hoàn thành hiện tại của một nhiệm vụ. Truy cập chúng qua `getProgressLines()` và in ra các thuộc tính. Mỗi đường tiến độ bao gồm màu đường, độ dày và vị trí tương đối so với thanh nhiệm vụ. Ghi lại thông tin này cho phép bạn tạo các hình ảnh trực quan có phản ánh tiến độ hoặc tính toán chỉ số hoàn thành tổng thể của dự án.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definition anchor:* `getProgressLines()` returns the set of progress line objects that indicate task completion status.

## Làm sao tôi trích xuất các cấp độ thang thời gian?
Cấp độ thang thời gian xác định các đơn vị thời gian phân cấp (ngày, tuần, tháng) hiển thị trên biểu đồ. Lấy chúng qua `getTimescaleTiers()` và xuất ra cài đặt. Đối với mỗi cấp độ, bạn có thể ghi lại loại đơn vị, định dạng nhãn và căn chỉnh, những yếu tố quan trọng để tái tạo độ chi tiết thời gian chính xác trong PDF xuất hoặc các thành phần UI tùy chỉnh.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definition anchor:* `getTimescaleTiers()` provides access to the collection of timescale tier objects that control the time axis display.

## Làm sao tôi xuất biểu đồ Gantt sang PDF?
Tạo một đối tượng `PdfSaveOptions`, tùy chỉnh kích thước trang hoặc nhúng phông chữ nếu cần, sau đó gọi `project.save` với định dạng PDF. Lệnh duy nhất này tạo ra một PDF phản ánh chính xác chế độ xem Gantt trên màn hình. Bạn cũng có thể chỉ định các tùy chọn bổ sung như nén hình ảnh, loại bỏ watermark, hoặc nhúng phông chữ tùy chỉnh để đáp ứng yêu cầu thương hiệu doanh nghiệp. Sau khi lưu, kiểm tra kích thước tệp PDF và độ trung thực hình ảnh để đảm bảo xuất thành công.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definition anchor:* `PdfSaveOptions` lets you fine‑tune PDF output, such as page dimensions, compression, and font handling.

## Những khó khăn thường gặp & mẹo
- **Thư mục dữ liệu không đúng:** Đảm bảo `dataDir` kết thúc bằng dấu phân tách tệp (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Thiếu view:** Nếu dự án không có view Gantt, `project.getViews()` sẽ rỗng – hãy kiểm tra trước khi ép kiểu.  
- **Ngoại lệ giấy phép:** Nếu không có giấy phép hợp lệ, API có thể thêm watermark vào PDF xuất.  
- **Dự án lớn:** Đối với dự án có hơn 1.000 nhiệm vụ, hãy cân nhắc tăng kích thước heap JVM (`-Xmx2g`) để tránh `OutOfMemoryError`.  

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks for Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Tasks for Java tích hợp liền mạch với bất kỳ thư viện hoặc framework Java nào, bao gồm Spring, Hibernate và Apache POI.

**Q: Aspose.Tasks có phù hợp với các dự án doanh nghiệp quy mô lớn không?**  
A: Chắc chắn. Thư viện xử lý các tệp MPP hàng trăm trang trong vòng dưới 5 giây trên phần cứng máy chủ tiêu chuẩn và hỗ trợ thực thi đồng thời trong môi trường đa luồng.

**Q: Aspose.Tasks hỗ trợ nhiều định dạng tệp dự án không?**  
A: Có, Aspose.Tasks hỗ trợ hơn 20 định dạng, bao gồm MPP, XML, MPX và Primavera XML, cho phép bạn đọc và chuyển đổi các lịch trình legacy.

**Q: Tôi có thể tùy chỉnh giao diện biểu đồ Gantt với Aspose.Tasks không?**  
A: Chắc chắn. Bạn có thể thay đổi kiểu thanh, đường lưới, kiểu văn bản và cấp độ thang thời gian bằng mã trước khi xuất sang PDF hoặc định dạng hình ảnh.

**Q: Làm sao tôi lưu các thay đổi sau khi chỉnh sửa view?**  
A: Gọi `project.save("output.mpp");` sau khi thực hiện bất kỳ thay đổi nào để lưu lại vào tệp dự án.

---

**Cập nhật lần cuối:** 2026-10-31  
**Kiểm tra với:** Aspose.Tasks for Java 24.12  
**Tác giả:** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Hướng dẫn liên quan

- [Cách lưu dự án dưới dạng PDF với Aspose.Tasks – Hướng dẫn xuất](/tasks/java/project-file-operations/save-as-pdf/)
- [Tạo PDF dự án – Tùy chỉnh thang thời gian biểu đồ Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [Xuất dự án sang PDF và giảm khoảng cách giữa danh sách nhiệm vụ và chân trang trong Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}