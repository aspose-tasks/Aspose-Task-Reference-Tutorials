---
date: 2026-08-29
description: Tìm hiểu cách thêm task vào project trong Java, tạo task list, và thiết
  lập baseline mà không cần Microsoft Project bằng cách sử dụng Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Tạo Task Baseline trong Aspose.Tasks
og_description: Tìm hiểu cách thêm task vào project trong Java và thiết lập baseline
  bằng Aspose.Tasks. Hướng dẫn này trình bày mã step‑by‑step mà không cần Microsoft
  Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Cách thêm task vào project trong Java và thiết lập baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Cách thêm task vào project trong Java và thiết lập baseline
url: /vi/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm nhiệm vụ vào dự án trong Java và thiết lập baseline

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **thêm nhiệm vụ vào dự án** một cách lập trình, tạo một baseline cho nhiệm vụ Microsoft Project, và lưu tệp—tất cả mà không cần mở Microsoft Project. Aspose.Tasks for Java cung cấp một API thuần Java hoạt động trên bất kỳ nền tảng nào, khiến nó hoàn hảo cho các pipeline xây dựng tự động, dịch vụ báo cáo, hoặc bất kỳ giải pháp phía máy chủ nào cần thao tác với các tệp .mpp.

## Câu trả lời nhanh
- **Aspose.Tasks làm gì?** Nó cung cấp một API Java để tạo, đọc và chỉnh sửa các tệp Microsoft Project mà không cần Microsoft Project.  
- **Có cần cài đặt Microsoft Project không?** Không, thư viện hoạt động hoàn toàn độc lập.  
- **Yêu cầu phiên bản Java nào?** JDK 8 hoặc cao hơn.  
- **Tôi có thể thiết lập baseline cho một nhiệm vụ duy nhất không?** Có – gọi `setBaseline` trên một danh sách chỉ chứa các nhiệm vụ bạn muốn.  
- **Cần giấy phép cho môi trường sản xuất không?** Có, giấy phép thương mại loại bỏ giới hạn đánh giá và mở khóa tất cả các tính năng.

## Baseline nhiệm vụ là gì?
Baseline nhiệm vụ ghi lại ngày bắt đầu, ngày kết thúc và khối lượng công việc dự kiến ban đầu cho một nhiệm vụ tại thời điểm lịch trình được lưu lần đầu. Bức ảnh chụp này hoạt động như một điểm tham chiếu, cho phép các nhà quản lý dự án so sánh tiến độ và chi phí thực tế với kế hoạch ban đầu, và tính toán các sai lệch để phân tích hiệu suất.

## Tại sao nên sử dụng Aspose.Tasks để thêm nhiệm vụ vào dự án trong Java?
Bạn có thể tạo, sửa đổi và thiết lập baseline cho các nhiệm vụ mà không cần cài đặt bất kỳ phần mềm máy tính để bàn nào, cho phép quy trình làm việc hoàn toàn tự động. Aspose.Tasks hỗ trợ **hơn 50 định dạng nhập và xuất** và có thể xử lý các dự án với **hàng trăm nhiệm vụ** trong khi giữ mức sử dụng bộ nhớ dưới 200 MB, làm cho nó trở nên lý tưởng cho các dịch vụ đám mây và pipeline CI/CD.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – cài đặt JDK 8 hoặc mới hơn.  
2. **Aspose.Tasks for Java** – tải xuống thư viện từ [download link](https://releases.aspose.com/tasks/java/).  

## Nhập các gói
Để bắt đầu làm việc với Aspose.Tasks trong dự án Java của bạn, nhập các gói cần thiết:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Bước 1: tạo đối tượng dự án
Lớp `Project` là đối tượng cấp cao nhất của Aspose.Tasks đại diện cho một tệp Microsoft Project trong bộ nhớ. Khi khởi tạo, nó cung cấp cho bạn một dự án trống mà bạn có thể điền các nhiệm vụ, nguồn lực và lịch.
```java
Project project = new Project();
```
Ở đây chúng ta khởi tạo một đối tượng `Project` mới – đối tượng này đại diện cho tệp MS Project sẽ chứa danh sách nhiệm vụ của chúng ta.

## Bước 2: thêm một nhiệm vụ vào dự án
Lớp `Task` đại diện cho một công việc cá nhân trong lịch trình dự án. Mỗi `Task` có thể có thời lượng, ngày bắt đầu và phân công nguồn lực riêng.
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Bằng cách sử dụng `getRootTask()` chúng ta truy cập vào gốc của cây dự án và **thêm nhiệm vụ vào Microsoft Project**. Chuỗi `"Task"` là tên nhiệm vụ; bạn có thể thay thế bằng bất kỳ mô tả nào bạn cần.

## Bước 3: thiết lập baseline cho các nhiệm vụ được chỉ định
`BaselineType` là một kiểu liệt kê xác định vị trí baseline nào (Baseline, Baseline1 … Baseline10) bạn muốn ghi. Bằng cách truyền một danh sách các nhiệm vụ, bạn có thể thiết lập baseline chỉ cho các mục bạn chọn.
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Để **thiết lập baseline mà không cần MS Project**, tạo một danh sách các nhiệm vụ bạn muốn thiết lập baseline (ở đây là `myList`) và truyền nó vào `setBaseline`. Điền `myList` với các nhiệm vụ bạn đã thêm nếu bạn chỉ cần một baseline chọn lọc.

## Bước 4: thiết lập baseline cho toàn bộ dự án
`setBaseline` ghi các giá trị baseline đã chọn vào mọi nhiệm vụ trong dự án.  
Nếu bạn muốn thiết lập baseline cho toàn bộ dự án trong một lần gọi, chỉ cần gọi `setBaseline` với `BaselineType` mong muốn.
```java
project.setBaseline(BaselineType.Baseline);
```
Lệnh này ghi các giá trị baseline đã chọn cho **mọi nhiệm vụ** trong dự án, đảm bảo một bức ảnh chụp đầy đủ của lịch trình ban đầu.

## Cách thêm nhiệm vụ vào Microsoft Project bằng Aspose.Tasks
`add()` tạo một nhiệm vụ con mới dưới nhiệm vụ cha được chỉ định và trả về đối tượng `Task` vừa tạo.  
Bạn thêm một nhiệm vụ bằng cách gọi `add()` trên một đối tượng `Task` cha (thường là nhiệm vụ gốc). Phương thức này trả về một thể hiện `Task` mới mà bạn có thể cấu hình thêm—thời lượng, ngày bắt đầu, nguồn lực, hoặc các trường tùy chỉnh—trước khi lưu tệp dự án.

## Cách thiết lập baseline mà không cần MS Project
Aspose.Tasks cho phép tạo baseline hoàn toàn bằng mã. Chọn một `BaselineType` (ví dụ, `BaselineType.Baseline`) và gọi `setBaseline`. Bạn có thể lặp lại với `Baseline1`‑`Baseline10` để giữ nhiều baseline phiên bản, tất cả mà không mở Microsoft Project.

## Các vấn đề thường gặp và giải pháp
- **Baseline không hiển thị:** Đảm bảo bạn gọi `project.save("output.mpp")` sau khi thiết lập baseline (bước lưu đã được bỏ qua ở đây để ngắn gọn).  
- **Danh sách nhiệm vụ trống:** Xác nhận rằng bạn đang thêm nhiệm vụ vào đúng cha (`getRootTask()` hoặc một sub‑task).  
- **Lỗi không khớp phiên bản:** Sử dụng JAR Aspose.Tasks mới nhất để đảm bảo tương thích với các định dạng .mpp mới hơn.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java mà không cần cài đặt Microsoft Project không?**  
A: Có, Aspose.Tasks hoạt động độc lập và không yêu cầu Microsoft Project trên máy chủ.

**Q: Aspose.Tasks cho Java có tương thích với các phiên bản khác nhau của Microsoft Project không?**  
A: Chắc chắn. Thư viện hỗ trợ các tệp Project từ năm 2007 đến các bản phát hành mới nhất năm 2024.

**Q: Tôi có thể thao tác tài nguyên dự án bằng Aspose.Tasks cho Java không?**  
A: Có, bạn có thể thêm, cập nhật và xóa tài nguyên một cách lập trình, giống như các nhiệm vụ.

**Q: Aspose.Tasks cho Java có hỗ trợ thiết lập phụ thuộc nhiệm vụ không?**  
A: Có, bạn có thể định nghĩa các mối quan hệ tiền nhiệm‑hậu nhiệm bằng lớp `TaskLink`.

**Q: Có hỗ trợ kỹ thuật cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể nhận trợ giúp qua [support forum](https://forum.aspose.com/c/tasks/15), nơi nhân viên Aspose và cộng đồng trả lời các câu hỏi.

## Kết luận
Bằng cách thực hiện các bước này, bạn đã học cách **thêm nhiệm vụ vào dự án** trong Java, tạo danh sách nhiệm vụ, và **thiết lập baseline mà không cần MS Project** bằng Aspose.Tasks. Cách tiếp cận này giúp đơn giản hoá tự động hoá dự án, loại bỏ nhu cầu cài đặt Project trên máy tính để bàn, và cung cấp cho bạn quyền kiểm soát lập trình đầy đủ đối với mọi khía cạnh của lịch trình.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Hướng dẫn liên quan

- [Cách tạo dự án aspose.tasks – Đặt thuộc tính nhiệm vụ mới](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Cách đặt thời lượng baseline trong Aspose.Tasks cho Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Tạo nhiệm vụ Aspose Java – Thuộc tính nhiệm vụ](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}