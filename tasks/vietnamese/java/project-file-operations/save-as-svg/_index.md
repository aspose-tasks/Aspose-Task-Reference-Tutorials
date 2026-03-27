---
date: 2026-03-27
description: Tìm hiểu cách xuất MPP sang SVG trong Java với Aspose.Tasks. Hướng dẫn
  từng bước, ví dụ mã và mẹo để lưu dự án dưới dạng SVG nhanh chóng.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách xuất MPP sang SVG trong Java bằng Aspose.Tasks
url: /vi/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách xuất MPP sang SVG trong Java

## Xuất MPP sang SVG – Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **xuất MPP sang SVG** bằng cách sử dụng Aspose.Tasks cho Java. Chuyển đổi tệp Microsoft Project (MPP) sang hình ảnh Scalable Vector Graphics (SVG) cho phép bạn nhúng các sơ đồ chất lượng cao, không phụ thuộc vào độ phân giải trực tiếp vào các trang web, báo cáo hoặc bảng điều khiển. Chúng tôi sẽ hướng dẫn qua các bước thiết lập cần thiết, hiển thị mã chính xác bạn cần, và giải thích từng bước để bạn có thể tự tin **lưu dự án dưới dạng SVG** trong các ứng dụng của mình.

## Câu trả lời nhanh
- **Ý nghĩa của “export MPP to SVG” là gì?**  
  Nó chuyển đổi tệp Microsoft Project (.mpp) thành một hình ảnh SVG có thể hiển thị trên bất kỳ trình duyệt nào mà không mất chất lượng.  
- **Thư viện nào thực hiện việc chuyển đổi?**  
  Aspose.Tasks cho Java cung cấp phương thức `save` một dòng để thực hiện việc chuyển đổi.  
- **Tôi có cần giấy phép không?**  
  Cần một giấy phép tạm thời cho việc sử dụng thương mại; bản dùng thử miễn phí có sẵn.  
- **Các điều kiện tiên quyết là gì?**  
  Java JDK 8+ và file JAR Aspose.Tasks cho Java.  
- **Quá trình chuyển đổi mất bao lâu?**  
  Thông thường dưới một giây cho các tệp dự án tiêu chuẩn.

## “export MPP to SVG” là gì?
Xuất MPP sang SVG có nghĩa là lấy biểu diễn trực quan của lịch trình dự án—các công việc, thời gian và tài nguyên—và ghi nó thành một tệp SVG. SVG dựa trên XML, nhẹ và mở rộng hoàn hảo trên các màn hình độ phân giải cao.

## Tại sao nên xuất MPP sang SVG với Aspose.Tasks?
- **Không cần cài đặt Microsoft Project** – thư viện hoạt động độc lập.  
- **Độ trung thực đầy đủ** – biểu đồ, thanh Gantt và các mốc thời gian giữ nguyên kiểu dáng.  
- **Đa nền tảng** – chạy mã trên Windows, Linux hoặc macOS.  
- **API một dòng** – một lệnh duy nhất lưu dự án dưới dạng SVG, tích hợp tự nhiên vào các pipeline Java hiện có.

## Điều kiện tiên quyết
- **Java Development Kit (JDK)** – phiên bản 8 trở lên. Tải xuống từ trang web Oracle.  
- **Aspose.Tasks cho Java** – lấy thư viện từ trang tải xuống chính thức **[here](https://releases.aspose.com/tasks/java/)**.  

## Nhập các gói
Đầu tiên, nhập các lớp bạn sẽ cần. Khối import sẽ không thay đổi.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Bước 1: Xác định Thư mục Dữ liệu
Xác định vị trí tệp MPP nguồn của bạn và nơi SVG sẽ được ghi.

```java
String dataDir = "Your Data Directory";
```

> **Mẹo chuyên nghiệp:** Sử dụng đường dẫn tuyệt đối hoặc đường dẫn tương đối so với thư mục resources của dự án để tránh `FileNotFoundException`.

## Bước 2: Tải tệp MPP
Tạo một thể hiện `Project` bằng cách tải tệp Microsoft Project hiện có.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Dòng này đọc *HomeMovePlan.mpp* từ thư mục bạn đã định nghĩa ở trên.

## Bước 3: Lưu Dự án dưới dạng SVG
Bây giờ bạn có thể **xuất MPP sang SVG** bằng một lệnh duy nhất.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Phương thức này ghi `project5.svg` vào cùng thư mục. SVG kết quả có thể mở trong bất kỳ trình duyệt hiện đại nào hoặc nhúng trực tiếp vào HTML.

## Các trường hợp sử dụng phổ biến
- **Bảng điều khiển dự án** – nhúng biểu đồ Gantt trực tiếp trong các cổng thông tin web mà không cần khách hàng cài đặt Microsoft Project.  
- **Báo cáo tự động** – tạo hình ảnh SVG ngay lập tức cho các báo cáo PDF hoặc HTML.  
- **Hợp tác đa đội** – chia sẻ lịch trình trực quan với các bên liên quan chỉ cần một trình duyệt để xem.

## Các vấn đề thường gặp và giải pháp
| Issue | Reason | Fix |
|-------|--------|-----|
| **Không tìm thấy tệp** | Đường dẫn `dataDir` không đúng | Kiểm tra chuỗi thư mục kết thúc bằng dấu phân tách (`/` hoặc `\\`). |
| **Kết quả SVG trống** | Dự án được tải mà không có chế độ xem | Đảm bảo tệp MPP chứa chế độ xem biểu đồ Gantt trước khi lưu. |
| **Ngoại lệ giấy phép** | Chưa áp dụng giấy phép hợp lệ | Áp dụng giấy phép tạm thời bằng cách sử dụng `License.setLicense("path/to/license.xml")` trước khi gọi `save`. |

## Câu hỏi thường gặp

**Q: Aspose.Tasks cho Java có tương thích với tất cả các phiên bản tệp Microsoft Project không?**  
A: Có, nó hỗ trợ các định dạng MPP, MPT và XML từ các phiên bản cũ đến các bản phát hành Project mới nhất.

**Q: Tôi có thể tùy chỉnh giao diện của đầu ra SVG không?**  
A: Chắc chắn. Sử dụng `SvgOptions` để đặt phông chữ, màu sắc và các tùy chọn bố cục trước khi gọi `save`.

**Q: Aspose.Tasks cho Java có yêu cầu giấy phép cho việc sử dụng thương mại không?**  
A: Có, cần một giấy phép hợp lệ cho môi trường sản xuất. Bạn có thể lấy giấy phép tạm thời **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: Tôi có thể dùng thử Aspose.Tasks cho Java trước khi mua không?**  
A: Có, bản dùng thử miễn phí có sẵn **[here](https://purchase.aspose.com/buy)**.

**Q: Tôi có thể nhận hỗ trợ cho Aspose.Tasks cho Java ở đâu?**  
A: Truy cập diễn đàn cộng đồng **[here](https://forum.aspose.com/c/tasks/15)** để đặt câu hỏi và chia sẻ phản hồi.

## Kết luận
Bây giờ bạn đã biết cách **xuất MPP sang SVG** trong Java và hiệu quả **lưu dự án dưới dạng SVG** bằng Aspose.Tasks. Khả năng này cho phép bạn tích hợp các hình ảnh dự án phong phú vào các cổng thông tin web, bảng điều khiển báo cáo, hoặc bất kỳ nơi nào cần đồ họa có thể mở rộng. Hãy thử nghiệm với `SvgOptions` để tinh chỉnh đầu ra, và bạn sẽ có một công cụ mạnh mẽ trong bộ công cụ phát triển của mình.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}