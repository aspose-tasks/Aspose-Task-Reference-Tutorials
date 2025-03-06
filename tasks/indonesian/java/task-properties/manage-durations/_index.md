---
title: Kelola Durasi Tugas di Aspose.Tasks
linktitle: Kelola Durasi Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi Aspose.Tasks untuk Java dan pelajari cara mengelola durasi tugas dengan mudah. Ikuti panduan langkah demi langkah kami untuk perencanaan dan pelaksanaan proyek yang efektif.
type: docs
weight: 20
url: /id/java/task-properties/manage-durations/
---
## Perkenalan
Aspose.Tasks untuk Java memberikan solusi tangguh untuk mengelola tugas dan durasi proyek secara efisien. Dalam tutorial ini, kita akan mempelajari cara mengelola durasi tugas menggunakan Aspose.Tasks, memandu Anda melalui setiap langkah. Baik Anda seorang pengembang berpengalaman atau pemula, panduan ini akan membantu Anda memahami pentingnya bekerja dengan durasi tugas dalam proyek Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
-  Java Development Kit (JDK): Pastikan Anda telah menginstal Java di mesin Anda. Anda dapat mengunduhnya[Di Sini](https://www.oracle.com/java/technologies/javase-downloads.html).
- Perpustakaan Aspose.Tasks: Unduh dan sertakan perpustakaan Aspose.Tasks dalam proyek Anda. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/tasks/java/).
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk bekerja dengan Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Langkah 1: Siapkan Proyek Anda
```java
// Buat proyek baru
Project project = new Project();
```
## Langkah 2: Tambahkan Tugas Baru
```java
// Tambahkan tugas baru ke proyek
Task task = project.getRootTask().getChildren().add("Task");
```
## Langkah 3: Dapatkan dan Konversi Durasi Tugas
```java
// Dapatkan durasi tugas dalam hari (satuan waktu default)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Ubah durasi menjadi satuan waktu jam
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Langkah 4: Perbarui Durasi Tugas menjadi 1 Minggu
```java
// Tingkatkan durasi tugas menjadi 1 minggu
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Langkah 5: Kurangi Durasi Tugas
```java
// Kurangi durasi tugas
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Dengan mengikuti langkah-langkah ini, Anda telah berhasil mengelola durasi tugas di proyek Aspose.Tasks untuk Java Anda.
## Kesimpulan
Dalam tutorial ini, kami telah membahas dasar-dasar mengelola durasi tugas menggunakan Aspose.Tasks untuk Java. Sekarang, Anda dapat dengan percaya diri menggabungkan teknik ini ke dalam proyek Anda untuk manajemen durasi tugas yang efektif.
## FAQ
### Apakah Aspose.Tasks kompatibel dengan semua versi Java?
Aspose.Tasks kompatibel dengan Java 6 dan versi yang lebih baru.
### Bisakah saya menggunakan Aspose.Tasks untuk proyek komersial?
 Ya, Anda dapat menggunakan Aspose.Tasks untuk proyek pribadi dan komersial. Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk rincian perizinan.
### Di mana saya dapat menemukan dukungan dan sumber daya tambahan?
 Mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk tujuan pengujian?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk pengujian dan evaluasi.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/) untuk menjelajahi Aspose.Tugas sebelum melakukan pembelian.