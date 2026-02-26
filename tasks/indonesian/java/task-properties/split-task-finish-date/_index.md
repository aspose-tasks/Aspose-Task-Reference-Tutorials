---
date: 2026-02-26
description: Pelajari cara memisahkan tanggal selesai tugas dan mengelola jadwal proyek
  menggunakan Aspose.Tasks untuk Java. Panduan ini menunjukkan cara memisahkan tugas
  secara efisien.
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Kelola Garis Waktu Proyek – Tanggal Selesai Tugas Terpisah di Aspose.Tasks
url: /id/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tanggal Selesai Tugas Split di Aspose.Tasks

## Introduction
Secara efektif **mengelola jadwal proyek** adalah fondasi keberhasilan penyampaian proyek. Ketika durasi sebuah tugas berubah, tanggal selesai harus dihitung ulang agar jadwal tetap akurat. Pada tutorial ini kami akan menunjukkan **cara memisahkan tanggal selesai tugas** dengan Aspose.Tasks untuk Java, memberi Anda kontrol yang tepat atas timeline proyek Anda.

## Quick Answers
- **Apa yang dicapai dengan memisahkan tanggal selesai tugas?** Ini memungkinkan Anda menghitung tanggal akhir untuk durasi apa pun, membantu menyesuaikan jadwal secara cepat.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk Java (dapat diunduh dari situs resmi).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya menggunakan ini dengan kalender proyek apa pun?** Ya, API menggunakan kalender proyek untuk menghormati hari kerja dan hari libur.  
- **Berapa banyak baris kode yang dibutuhkan?** Kurang dari sepuluh baris untuk mendapatkan tanggal selesai untuk durasi apa pun.

## What is “manage project timelines” in the context of Aspose.Tasks?
Mengelola jadwal proyek berarti menjaga setiap tanggal mulai dan selesai tugas tetap sinkron dengan jadwal keseluruhan, dengan mempertimbangkan kalender, sumber daya, dan ketergantungan tugas. Perhitungan tanggal selesai yang akurat sangat penting untuk proyeksi realistis dan kepercayaan pemangku kepentingan.

## Why split a task’s finish date?
- **Fleksibilitas:** Lihat dengan cepat bagaimana alokasi jam kerja yang berbeda memengaruhi penyampaian.  
- **Penilaian risiko:** Evaluasi skenario “what‑if” tanpa mengubah rencana asli.  
- **Perencanaan sumber daya:** Sesuaikan durasi tugas dengan kapasitas tim dan batasan kalender.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar pemrograman Java.  
- Perpustakaan Aspose.Tasks untuk Java terpasang. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/tasks/java/).  
- Lingkungan pengembangan Java yang sudah disiapkan.

## Import Packages
Mulailah dengan menyertakan paket yang diperlukan dalam proyek Java Anda:
```java
import com.aspose.tasks.*;
```

## Step 1: Find a Split Task
Temukan tugas yang ingin Anda split di dalam proyek:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## Step 2: Find the Project Calendar
Ambil kalender proyek untuk perhitungan tanggal yang akurat:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## Step 3: Calculate Task Finish Date with Different Durations
Sekarang, hitung tanggal selesai tugas untuk berbagai durasi.

### Step 3.1: Duration of 8 Hours
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*Ulangi kode di atas untuk durasi yang berbeda, sesuaikan jamnya sesuai kebutuhan, untuk melihat bagaimana setiap perubahan memengaruhi tanggal selesai.*

## Common Issues and Solutions
- **Referensi kalender yang tidak tepat:** Pastikan Anda mengambil kalender proyek (`project.get(Prj.CALENDAR)`) bukan membuat yang baru.  
- **UID tugas yang salah:** UID harus cocok dengan tugas yang memang ada; jika tidak, `getByUid` mengembalikan `null` dan menyebabkan `NullPointerException`.  
- **Perbedaan zona waktu:** API bekerja dengan zona waktu kalender; periksa zona default sistem Anda jika hasil tampak tidak tepat.

## Conclusion
Menguasai seni **mengelola jadwal proyek** dengan memisahkan tanggal selesai tugas sangat penting untuk manajemen proyek yang efektif. Aspose.Tasks untuk Java menyederhanakan proses ini, memungkinkan Anda menyelaraskan jadwal dengan mudah.

## FAQs
### Q1: How can I download Aspose.Tasks for Java?
A1: Anda dapat mengunduhnya [di sini](https://releases.aspose.com/tasks/java/).

### Q2: Where can I find documentation for Aspose.Tasks?
A2: Lihat dokumentasi [di sini](https://reference.aspose.com/tasks/java/).

### Q3: How do I get a temporary license for Aspose.Tasks?
A3: Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Q4: Where can I seek support for Aspose.Tasks?
A4: Kunjungi forum dukungan [di sini](https://forum.aspose.com/c/tasks/15).

### Q5: Can I purchase Aspose.Tasks?
A5: Ya, Anda dapat membelinya [di sini](https://purchase.aspose.com/buy).

## Additional Frequently Asked Questions

**Q: Can I use this technique with a custom calendar?**  
A: Tentu saja. Ganti `project.get(Prj.CALENDAR)` dengan instance `Calendar` khusus Anda.

**Q: Does the method consider non‑working days?**  
A: Ya, definisi waktu kerja kalender diterapkan saat menghitung tanggal selesai.

**Q: Is there a way to retrieve the finish date for fractional hours (e.g., 3.5 hours)?**  
A: Kirim nilai `double` seperti `3.5d` ke `getTaskFinishDateFromDuration`; API menangani durasi pecahan.

**Q: How do I format the output date?**  
A: Gunakan `java.time.format.DateTimeFormatter` pada objek `Date` yang dikembalikan untuk menampilkannya dalam format pilihan Anda.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}