---
title: Kelola Tugas Orang Tua dan Anak di Aspose.Tasks
linktitle: Kelola Tugas Orang Tua dan Anak di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Tingkatkan efisiensi manajemen proyek dengan Aspose.Tasks untuk Java. Belajar mengelola tugas orang tua dan anak selangkah demi selangkah. Mulai sekarang!
weight: 24
url: /id/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola Tugas Orang Tua dan Anak di Aspose.Tasks

## Perkenalan
Dalam bidang manajemen proyek, pengorganisasian tugas yang efektif sangatlah penting. Aspose.Tasks untuk Java memberikan solusi tangguh untuk mengelola tugas induk dan anak secara efisien. Dalam tutorial ini, kami akan memandu Anda melalui proses penggunaan Aspose.Tasks untuk Java untuk menyederhanakan tugas proyek Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar pemrograman Java.
-  Aspose.Tasks untuk perpustakaan Java diinstal. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/tasks/java/).
- Lingkungan Pengembangan Terpadu Java (IDE) yang disiapkan di sistem Anda.
## Paket Impor
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda. Paket-paket ini memfasilitasi integrasi yang lancar dengan fungsi Aspose.Tasks untuk Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Langkah 1: Tetapkan Tanggal Mulai Proyek
Mulailah dengan menetapkan tanggal mulai proyek dan parameter relevan lainnya.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Kode tambahan untuk impor paket dapat ditambahkan di sini
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Langkah 2: Tambahkan Tugas Induk (Tugas 1)
Buat tugas induk bernama "Tugas 1" dan konfigurasikan propertinya.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Langkah 3: Tambahkan Tugas Induk (Tugas 2) dengan Tugas Anak
Sekarang, tambahkan tugas induk lainnya bernama "Tugas 2" dan sertakan tugas anak (Tugas 3 dan Tugas 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Tambahkan tugas anak ke Tugas 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Konfigurasi tambahan untuk Tugas 3 dan Tugas 4 dapat ditambahkan di sini
```
## Langkah 4: Konfigurasikan Tugas Anak
Tentukan tanggal mulai, durasi, dan batasan untuk Tugas 3 dan Tugas 4.
```java
// Konfigurasikan Tugas 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Konfigurasikan Tugas 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Langkah 5: Perbarui Persentase Penyelesaian Tugas
Sesuaikan persentase penyelesaian untuk Tugas 3 dan Tugas 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Langkah 6: Simpan Proyek
Terakhir, simpan proyek dengan perubahan yang diterapkan.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Panduan langkah demi langkah ini menunjukkan cara mengelola tugas orang tua dan anak secara efektif menggunakan Aspose.Tasks untuk Java. Bereksperimenlah dengan konfigurasi berbeda untuk memenuhi kebutuhan proyek Anda.
## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk Java memberdayakan pengembang untuk menangani tugas proyek secara efisien, memastikan pengorganisasian dan pelacakan yang lancar. Terapkan langkah-langkah yang diuraikan untuk meningkatkan kemampuan manajemen proyek Anda.
## FAQ
### Apakah Aspose.Tasks untuk Java kompatibel dengan format file proyek yang berbeda?
Ya, Aspose.Tasks untuk Java mendukung berbagai format file proyek, termasuk MPP dan XML.
### Bisakah saya mengkustomisasi properti tugas di luar apa yang dibahas dalam tutorial ini?
Sangat! Aspose.Tasks untuk Java menyediakan opsi penyesuaian yang luas untuk properti tugas.
### Apakah ada forum komunitas untuk Aspose.Tasks tempat saya dapat mencari dukungan?
 Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan masyarakat.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi komprehensif untuk Aspose.Tasks untuk Java?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
