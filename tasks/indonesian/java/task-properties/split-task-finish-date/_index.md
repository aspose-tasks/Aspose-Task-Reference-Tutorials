---
title: Pisahkan Tanggal Selesai Tugas di Aspose.Tasks
linktitle: Pisahkan Tanggal Selesai Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara membagi tanggal penyelesaian tugas dengan mudah menggunakan Aspose.Tasks untuk Java. Tingkatkan manajemen proyek dengan jadwal yang akurat.
type: docs
weight: 28
url: /id/java/task-properties/split-task-finish-date/
---
## Perkenalan
Dalam manajemen proyek, memahami jadwal tugas sangat penting untuk keberhasilan penyelesaian proyek. Aspose.Tasks untuk Java menyediakan fitur canggih untuk memanipulasi tugas proyek secara efisien. Dalam tutorial ini, kita akan mempelajari pembagian tanggal penyelesaian tugas menggunakan Aspose.Tasks, membantu Anda mengelola jadwal proyek secara efektif.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang pemrograman Java.
-  Aspose.Tasks untuk perpustakaan Java diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/java/).
- Lingkungan pengembangan Java telah disiapkan.
## Paket Impor
Mulailah dengan memasukkan paket-paket yang diperlukan dalam proyek Java Anda:
```java
import com.aspose.tasks.*;
```
## Langkah 1: Temukan Tugas Terpisah
Temukan tugas yang ingin Anda bagi dalam proyek:
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Baca proyek
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Langkah 2: Temukan Kalender Proyek
Ambil kalender proyek untuk perhitungan tanggal yang akurat:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Langkah 3: Hitung Tanggal Selesai Tugas dengan Durasi Berbeda
Sekarang, hitung tanggal selesai tugas untuk berbagai durasi:
## Langkah 3.1: Durasi 8 Jam
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Ulangi kode di atas untuk durasi yang berbeda, sesuaikan jamnya.
## Kesimpulan
Menguasai seni memanipulasi tanggal penyelesaian tugas sangat penting untuk manajemen proyek yang efektif. Aspose.Tasks untuk Java menyederhanakan proses ini, memungkinkan Anda menyederhanakan jadwal proyek Anda dengan mudah.
## FAQ
### Q1: Bagaimana cara mengunduh Aspose.Tasks untuk Java?
 A1: Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/java/).
### Q2: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks?
 A2: Lihat dokumentasi[Di Sini](https://reference.aspose.com/tasks/java/).
### Q3: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?
 A3: Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Q4: Di mana saya dapat mencari dukungan untuk Aspose.Tasks?
 A4: Kunjungi forum dukungan[Di Sini](https://forum.aspose.com/c/tasks/15).
### Q5: Bisakah saya membeli Aspose.Tasks?
 A5: Ya, Anda bisa membelinya[Di Sini](https://purchase.aspose.com/buy).