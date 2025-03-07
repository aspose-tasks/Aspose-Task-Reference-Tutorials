---
title: Buat Tautan Tugas Lintas Proyek di Aspose.Tasks
linktitle: Buat Tautan Tugas Lintas Proyek di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Tingkatkan kolaborasi proyek dengan Aspose.Tasks untuk Java. Pelajari cara membuat tautan tugas lintas proyek langkah demi langkah. Tingkatkan efisiensi sekarang!
weight: 10
url: /id/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Tautan Tugas Lintas Proyek di Aspose.Tasks

## Perkenalan
Dalam dunia manajemen proyek yang dinamis, efisiensi dan kolaborasi adalah yang terpenting. Aspose.Tasks untuk Java memberikan solusi tangguh untuk meningkatkan kemampuan manajemen proyek Anda. Dalam tutorial ini, kita akan mempelajari proses pembuatan tautan tugas lintas proyek menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah ini akan membekali Anda dengan keterampilan untuk menghubungkan tugas-tugas di berbagai proyek dengan lancar, mendorong peningkatan koordinasi dan alur kerja yang efisien.
## Prasyarat
Sebelum kita memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan kerja tentang pemrograman Java.
-  Aspose.Tasks untuk Java diinstal. Anda dapat mengunduhnya dari[Aspose.Tasks untuk halaman rilis Java](https://releases.aspose.com/tasks/java/).
- Pemahaman dasar tentang manajemen proyek dan ketergantungan tugas.
## Paket Impor
Untuk memulai prosesnya, mari impor paket yang diperlukan di lingkungan Java Anda. Ini memastikan bahwa Anda memiliki akses ke fungsi Aspose.Tasks untuk Java. Gunakan cuplikan kode berikut:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Sekarang, mari kita pecahkan kode di atas menjadi langkah-langkah yang dapat dipahami:
## Langkah 1: Siapkan Lingkungan Anda
Sebelum mendalami kodenya, pastikan Anda telah menginstal Java, dan pustaka Aspose.Tasks untuk Java telah ditambahkan dengan benar ke proyek Anda.
## Langkah 2: Buat Instans Proyek
Inisialisasi proyek baru menggunakan perpustakaan Aspose.Tasks:
```java
Project project = new Project();
```
## Langkah 3: Tambahkan Tugas Ringkasan
Buat tugas ringkasan untuk mengatur dan mengelola tugas terkait:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## Langkah 4: Tambahkan Tugas Eksternal
Untuk membuat tautan ke tugas dari proyek lain, tambahkan tugas eksternal ke tugas ringkasan:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## Langkah 5: Tambahkan Tugas Lokal
Tambahkan tugas lokal ke tugas ringkasan. Ini akan menjadi tugas yang ditautkan ke tugas eksternal:
```java
Task t = summary.getChildren().add("Task");
```
## Langkah 6: Buat Tautan Tugas
Tetapkan hubungan tugas antara tugas eksternal dan tugas lokal:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Langkah 7: Tampilkan Hasil
Terakhir, tampilkan hasil konversi:
```java
System.out.println("Process completed Successfully");
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara membuat tautan tugas lintas proyek menggunakan Aspose.Tasks untuk Java. Fungsionalitas ini meningkatkan kolaborasi dan koordinasi dalam manajemen proyek, memastikan integrasi yang mulus antar tugas dalam berbagai proyek.
## FAQ
### Bisakah saya menautkan tugas dari beberapa proyek eksternal dalam tugas ringkasan yang sama?
Ya, Anda dapat menautkan tugas dari proyek eksternal yang berbeda dalam tugas ringkasan yang sama, dengan mengikuti proses serupa.
### Apa yang terjadi jika tugas eksternal dalam proyek tertaut diubah?
Modifikasi apa pun pada tugas eksternal akan tercermin dalam tugas tertaut di proyek Anda saat ini.
### Apakah mungkin membuat tautan antar tugas dalam format file berbeda?
Ya, Aspose.Tasks untuk Java mendukung penautan tugas antar proyek dalam berbagai format file.
### Bisakah saya membatalkan tautan tugas setelah tugas tersebut ditautkan ke seluruh proyek?
Ya, Anda dapat membatalkan tautan tugas dengan menghapus tautan tugas menggunakan metode Aspose.Tasks yang sesuai.
### Apakah ada batasan jumlah tugas yang dapat dihubungkan antar proyek?
Jumlah tugas yang dapat ditautkan bergantung pada kemampuan dan batasan lisensi Aspose.Tasks Anda.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
