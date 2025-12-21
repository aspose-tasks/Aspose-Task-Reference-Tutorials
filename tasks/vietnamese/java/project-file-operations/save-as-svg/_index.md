---
date: 2025-12-21
description: Học cách tạo SVG từ tệp MPP trong Java và lưu dự án dưới dạng SVG bằng
  thư viện Aspose.Tasks. Hướng dẫn từng bước kèm ví dụ mã.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cách tạo SVG từ MPP trong Java bằng Aspose.Tasks
url: /vi/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo SVG từ MPP trong Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **tạo SVG từ các tệp MPP** bằng Aspose.Tasks for Java. Việc chuyển đổi tệp Microsoft Project (MPP) sang đồ họa vector có thể mở rộng (SVG) cho phép bạn nhúng các sơ đồ chất lượng cao, không phụ thuộc vào độ phân giải trực tiếp vào các trang web, báo cáo hoặc bảng điều khiển. Chúng tôi sẽ hướng dẫn cài đặt cần thiết, hiển thị đoạn mã chính xác bạn cần, và giải thích từng bước để bạn tự tin **lưu dự án dưới dạng SVG** trong các ứng dụng của mình.

## Trả lời nhanh
- **“tạo SVG từ MPP” có nghĩa là gì?**  
  Nó chuyển đổi một tệp Microsoft Project (.mpp) thành hình ảnh SVG có thể hiển thị trên bất kỳ trình duyệt nào mà không mất chất lượng.  
- **Thư viện nào thực hiện việc chuyển đổi?**  
  Aspose.Tasks for Java cung cấp phương thức `save` một dòng để thực hiện chuyển đổi.  
- **Tôi có cần giấy phép không?**  
  Cần giấy phép tạm thời cho mục đích thương mại; bản dùng thử miễn phí có sẵn.  
- **Các điều kiện tiên quyết là gì?**  
  Java JDK 8+ và file JAR Aspose.Tasks for Java.  
- **Quá trình chuyển đổi mất bao lâu?**  
  Thông thường dưới một giây đối với các tệp dự án tiêu chuẩn.

## “tạo SVG từ MPP” là gì?
Tạo SVG từ tệp MPP có nghĩa là xuất biểu diễn trực quan của lịch trình dự án — các công việc, thời gian và nguồn lực — sang định dạng Scalable Vector Graphics. SVG dựa trên XML, nhẹ và mở rộng hoàn hảo trên các màn hình độ phân giải cao.

## Tại sao nên dùng Aspose.Tasks để lưu dự án dưới dạng SVG?
- **Không cần cài đặt Microsoft Project** – thư viện hoạt động độc lập.  
- **Độ chính xác cao** – biểu đồ, thanh Gantt và các mốc thời gian giữ nguyên phong cách.  
- **Đa nền tảng** – chạy mã trên Windows, Linux hoặc macOS.  
- **Dễ tích hợp** – lời gọi API một dòng phù hợp tự nhiên vào các pipeline Java hiện có.

## Điều kiện tiên quyết
- **Java Development Kit (JDK)** – phiên bản 8 trở lên. Tải về từ trang web Oracle.  
- **Aspose.Tasks for Java** – lấy thư viện từ trang tải chính thức **[tại đây](https://releases.aspose.com/tasks/java/)**.  

## Nhập gói
Đầu tiên, nhập các lớp bạn sẽ cần. Khối import không thay đổi.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Bước 1: Xác định thư mục dữ liệu
Chỉ định vị trí tệp MPP nguồn và nơi SVG sẽ được ghi.

```java
String dataDir = "Your Data Directory";
```

> **Mẹo:** Sử dụng đường dẫn tuyệt đối hoặc đường dẫn tương đối so với thư mục resources của dự án để tránh `FileNotFoundException`.

## Bước 2: Tải tệp MPP
Tạo một thể hiện `Project` bằng cách tải tệp Microsoft Project hiện có.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Dòng này đọc *HomeMovePlan.mpp* từ thư mục bạn đã định nghĩa ở trên.

## Bước 3: Lưu dự án dưới dạng SVG
Bây giờ bạn có thể **lưu dự án dưới dạng SVG** chỉ với một lệnh duy nhất.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

Phương thức này ghi `project5.svg` vào cùng thư mục. SVG kết quả có thể mở trong bất kỳ trình duyệt hiện đại nào hoặc nhúng trực tiếp vào HTML.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| **Không tìm thấy tệp** | Đường dẫn `dataDir` không đúng | Kiểm tra chuỗi thư mục kết thúc bằng dấu phân cách (`/` hoặc `\\`). |
| **SVG đầu ra trống** | Dự án được tải mà không có view | Đảm bảo tệp MPP chứa view biểu đồ Gantt trước khi lưu. |
| **Ngoại lệ giấy phép** | Chưa áp dụng giấy phép hợp lệ | Áp dụng giấy phép tạm thời bằng `License.setLicense("path/to/license.xml")` trước khi gọi `save`. |

## Câu hỏi thường gặp

**H: Aspose.Tasks for Java có tương thích với mọi phiên bản tệp Microsoft Project không?**  
Đ: Có, nó hỗ trợ các định dạng MPP, MPT và XML từ các phiên bản cũ đến mới nhất của Project.

**H: Tôi có thể tùy chỉnh giao diện của SVG đầu ra không?**  
Đ: Chắc chắn. Sử dụng `SvgOptions` để đặt phông chữ, màu sắc và các tùy chọn bố cục trước khi gọi `save`.

**H: Aspose.Tasks for Java có yêu cầu giấy phép cho mục đích thương mại không?**  
Đ: Có, cần giấy phép hợp lệ cho môi trường sản xuất. Bạn có thể lấy giấy phép tạm thời **[tại đây](https://purchase.aspose.com/temporary-license/)**.

**H: Tôi có thể dùng thử Aspose.Tasks for Java trước khi mua không?**  
Đ: Có, bản dùng thử miễn phí có sẵn **[tại đây](https://purchase.aspose.com/buy)**.

**H: Tôi có thể nhận hỗ trợ cho Aspose.Tasks for Java ở đâu?**  
Đ: Truy cập diễn đàn cộng đồng **[tại đây](https://forum.aspose.com/c/tasks/15)** để đặt câu hỏi và chia sẻ phản hồi.

## Kết luận
Bạn đã biết cách **tạo SVG từ các tệp MPP** trong Java và hiệu quả **lưu dự án dưới dạng SVG** bằng Aspose.Tasks. Khả năng này cho phép bạn tích hợp các hình ảnh dự án phong phú vào các cổng thông tin web, bảng điều khiển báo cáo, hoặc bất kỳ nơi nào cần đồ họa mở rộng. Thử nghiệm với `SvgOptions` để tinh chỉnh đầu ra, và bạn sẽ có một công cụ mạnh mẽ trong bộ công cụ phát triển của mình.

---

**Cập nhật lần cuối:** 2025-12-21  
**Đã kiểm tra với:** Aspose.Tasks for Java 24.10  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}