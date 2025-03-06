---
title: Perbarui File MPP di Aspose.Tasks
linktitle: Perbarui File MPP di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara memperbarui file MPP dengan lancar menggunakan Aspose.Tasks untuk Java. Ikuti panduan langkah demi langkah kami untuk manipulasi file proyek yang efisien.
weight: 19
url: /id/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Perbarui File MPP di Aspose.Tasks

## Perkenalan
Dalam bidang manajemen proyek, penanganan dan pemutakhiran file proyek merupakan tugas yang krusial. Aspose.Tasks untuk Java memberikan solusi ampuh bagi pengembang Java untuk memanipulasi file Microsoft Project dengan lancar. Dalam tutorial ini, kita akan mempelajari cara memperbarui file MPP menggunakan Aspose.Tasks untuk Java.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki hal berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda.
2.  Aspose.Tasks for Java: Unduh dan instal Aspose.Tasks for Java dari[Unduh Halaman](https://releases.aspose.com/tasks/java/).
3. Pengetahuan Dasar Java: Keakraban dengan bahasa pemrograman Java diperlukan untuk mengikuti contoh-contoh.

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan ke proyek Java Anda untuk memanfaatkan fungsi Aspose.Tasks secara efektif.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Baris kode ini mengimpor semua kelas dan metode penting dari perpustakaan Aspose.Tasks, memungkinkan Anda bekerja dengan file Microsoft Project dengan mudah.

Sekarang, mari kita uraikan proses memperbarui file MPP menggunakan Aspose.Tasks untuk Java menjadi langkah-langkah yang dapat dikelola.
## Langkah 2: Tentukan Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur sebenarnya di mana file MPP Anda berada.
## Langkah 3: Baca Proyek yang Ada
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Kode ini membaca file proyek MPP yang ada bernama`SampleMSP2010.mpp` dari direktori data yang ditentukan.
## Langkah 4: Buat Tugas Baru
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Di sini, kami menambahkan tugas baru bernama "Task1" ke tugas utama proyek.
## Langkah 5: Tetapkan Tanggal Mulai dan Selesai
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Baris kode ini menetapkan tanggal mulai dan tanggal selesai untuk tugas yang baru dibuat.
## Langkah 6: Simpan Proyek
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Terakhir, langkah ini menyimpan proyek yang diperbarui dengan tugas yang baru ditambahkan ke file MPP baru bernama`AfterLinking.mpp`.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara memperbarui file MPP menggunakan Aspose.Tasks untuk Java. Dengan mengikuti panduan langkah demi langkah, Anda dapat memanipulasi file Microsoft Project secara efisien dalam aplikasi Java Anda.
## FAQ
### T: Dapatkah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?
J: Ya, Aspose.Tasks untuk Java menyediakan fitur tangguh untuk menangani struktur proyek yang kompleks secara efisien.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat mengunduh uji coba gratis dari[situs web](https://releases.aspose.com/).
### T: Apakah Aspose.Tasks untuk Java mendukung versi file Microsoft Project yang berbeda?
J: Tentu saja, Aspose.Tasks untuk Java mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.
### T: Bisakah saya mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 J: Ya, lisensi sementara tersedia untuk tujuan pengujian. Anda dapat memperolehnya dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat mencari bantuan atau dukungan mengenai Aspose.Tasks untuk Java?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
