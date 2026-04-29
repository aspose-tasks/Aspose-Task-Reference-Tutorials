---
date: 2026-01-18
description: Tìm hiểu cách tạo danh sách công việc bằng Java và thêm công việc vào
  Microsoft Project, thiết lập baseline mà không cần MS Project bằng Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tạo danh sách công việc Java – Baseline MS Project bằng Aspose.Tasks
url: /vi/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Danh Sách Nhiệm Vụ Java – Baseline Dự Án MS với Aspose.Tasks

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **tạo danh sách nhiệm vụ Java** bằng cách tạo baseline nhiệm vụ Microsoft Project sử dụng Aspose.Tasks cho Java. Aspose.Tasks cho phép bạn làm việc với các tệp Project mà không cần cài đặt Microsoft Project, vì vậy bạn có thể **thêm nhiệm vụ vào Microsoft Project**, thao tác tài nguyên, và thậm chí **đặt baseline mà không cần MS Project**—tất cả từ mã Java thuần.

## Trả Lời Nhanh
- **Aspose.Tasks làm gì?** Cung cấp một API Java để tạo, đọc và chỉnh sửa các tệp Microsoft Project mà không cần MS Project.  
- **Có cần cài đặt Microsoft Project không?** Không, Aspose.Tasks hoạt động độc lập.  
- **Yêu cầu phiên bản Java nào?** JDK 8 trở lên.  
- **Có thể đặt baseline cho một nhiệm vụ duy nhất không?** Có, sử dụng `setBaseline` với một danh sách nhiệm vụ.  
- **Cần giấy phép cho môi trường sản xuất không?** Có, giấy phép thương mại loại bỏ các giới hạn đánh giá.

## Baseline Nhiệm Vụ là gì?
Baseline nhiệm vụ ghi lại các giá trị bắt đầu, kết thúc và công việc dự kiến ban đầu của một nhiệm vụ. Nó đóng vai trò là điểm tham chiếu để so sánh tiến độ thực tế với kế hoạch gốc.

## Tại sao nên dùng Aspose.Tasks để tạo danh sách nhiệm vụ Java?
- **Không phụ thuộc vào MS Project** – lý tưởng cho tự động hoá phía máy chủ.  
- **Kiểm soát toàn diện** các nhiệm vụ, tài nguyên và lịch làm việc qua mã Java.  
- **Tương thích đa phiên bản** với các tệp Project 2007‑2024.

## Yêu Cầu Trước
1. **Java Development Kit (JDK)** – cài đặt JDK 8 hoặc mới hơn.  
2. **Aspose.Tasks for Java** – tải thư viện từ [download link](https://releases.aspose.com/tasks/java/).  

## Nhập Gói
Để bắt đầu làm việc với Aspose.Tasks trong dự án Java của bạn, nhập các gói cần thiết:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Bước 1: Tạo Đối Tượng Project
```java
Project project = new Project();
```
Ở đây chúng ta khởi tạo một đối tượng `Project` mới – đại diện cho tệp MS Project sẽ chứa danh sách nhiệm vụ của chúng ta.

## Bước 2: Thêm Nhiệm Vụ vào Project
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Sử dụng `getRootTask()` chúng ta truy cập vào gốc của cấu trúc dự án và **thêm nhiệm vụ vào Microsoft Project**. Chuỗi `"Task"` là tên nhiệm vụ; bạn có thể thay thế bằng bất kỳ mô tả nào bạn cần.

## Bước 3: Đặt Baseline cho Các Nhiệm Vụ Được Chỉ Định
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Để **đặt baseline mà không cần MS Project**, tạo một danh sách các nhiệm vụ bạn muốn baseline (ở đây là `myList`) và truyền nó vào `setBaseline`. Điền `myList` với các nhiệm vụ bạn đã thêm nếu chỉ cần baseline cho một phần chọn lọc.

## Bước 4: Đặt Baseline cho Toàn Bộ Dự Án
```java
project.setBaseline(BaselineType.Baseline);
```
Nếu bạn muốn baseline toàn bộ dự án trong một lần gọi, chỉ cần gọi `setBaseline` với `BaselineType` mong muốn.

## Cách thêm nhiệm vụ vào Microsoft Project bằng Aspose.Tasks
Ngoài nhiệm vụ đơn được minh họa ở trên, bạn có thể thêm nhiều nhiệm vụ, nhiệm vụ con và gán tài nguyên. Mỗi lần gọi `add()` sẽ trả về một đối tượng `Task` mà bạn có thể cấu hình thêm (thời lượng, ngày bắt đầu, v.v.).

## Cách đặt baseline mà không cần MS Project
Aspose.Tasks cho phép tạo baseline hoàn toàn bằng mã. Bạn có thể đặt các loại baseline khác nhau (Baseline, Baseline1‑Baseline10) bằng cách thay đổi enum `BaselineType`, cho phép theo dõi nhiều phiên bản baseline mà không bao giờ mở MS Project.

## Các Vấn Đề Thường Gặp và Giải Pháp
- **Baseline không hiển thị:** Đảm bảo bạn gọi `project.save("output.mpp")` sau khi đặt baseline (bước lưu đã được bỏ qua ở đây để ngắn gọn).  
- **Danh sách nhiệm vụ trống:** Kiểm tra xem bạn có đang thêm nhiệm vụ vào đúng cha (`getRootTask()` hoặc một nhiệm vụ con) không.  
- **Lỗi không tương thích phiên bản:** Sử dụng JAR Aspose.Tasks mới nhất để đảm bảo tương thích với các định dạng .mpp mới hơn.

## Câu Hỏi Thường Gặp

**Q: Tôi có thể sử dụng Aspose.Tasks cho Java mà không cần cài đặt Microsoft Project không?**  
A: Có, Aspose.Tasks hoạt động độc lập và không yêu cầu Microsoft Project trên máy chủ.

**Q: Aspose.Tasks cho Java có tương thích với các phiên bản khác nhau của Microsoft Project không?**  
A: Hoàn toàn. Thư viện hỗ trợ các tệp Project từ 2007 đến các phiên bản mới nhất năm 2024.

**Q: Tôi có thể thao tác tài nguyên dự án bằng Aspose.Tasks cho Java không?**  
A: Có, bạn có thể thêm, cập nhật và xóa tài nguyên thông qua mã, giống như với các nhiệm vụ.

**Q: Aspose.Tasks cho Java có hỗ trợ thiết lập phụ thuộc giữa các nhiệm vụ không?**  
A: Có, bạn có thể định nghĩa quan hệ tiền nhiệm‑hậu nhiệm bằng lớp `TaskLink`.

**Q: Có hỗ trợ kỹ thuật cho Aspose.Tasks cho Java không?**  
A: Có, bạn có thể nhận trợ giúp qua [support forum](https://forum.aspose.com/c/tasks/15), nơi nhân viên Aspose và cộng đồng trả lời các câu hỏi.

## Kết Luận
Bằng cách làm theo các bước trên, bạn đã học được cách **tạo danh sách nhiệm vụ Java**, **thêm nhiệm vụ vào Microsoft Project**, và **đặt baseline mà không cần MS Project** sử dụng Aspose.Tasks. Cách tiếp cận này giúp tự động hoá dự án hiệu quả, loại bỏ nhu cầu cài đặt Project trên máy tính để bàn, và cung cấp cho bạn quyền kiểm soát lập trình đầy đủ đối với dữ liệu dự án.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

---