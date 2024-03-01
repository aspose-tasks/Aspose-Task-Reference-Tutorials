---
title: Render Penggunaan Sumber Daya dan Tampilan Lembar di Aspose.Tasks
linktitle: Render Penggunaan Sumber Daya dan Tampilan Lembar di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara merender tampilan Penggunaan Sumber Daya Proyek MS dan Lembar di Aspose.Tasks untuk Java. Ikuti panduan langkah demi langkah kami untuk menghasilkan laporan PDF terperinci dengan mudah.
type: docs
weight: 16
url: /id/java/resource-management/render-resource-usage-sheet-view/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Tasks untuk Java untuk merender tampilan Penggunaan Sumber Daya Proyek MS dan Lembar. Aspose.Tasks adalah pustaka Java canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project tanpa perlu menginstal Microsoft Project.
## Prasyarat
Sebelum kita mulai, pastikan Anda telah menginstal dan menyiapkan prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java Development Kit di sistem Anda. Anda dapat mengunduh dan menginstal JDK versi terbaru dari situs web Oracle.
2.  Aspose.Tasks for Java: Unduh dan instal perpustakaan Aspose.Tasks for Java dari[Unduh Halaman](https://releases.aspose.com/tasks/java/).

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Langkah 1: Baca Proyek Sumber
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
// Baca Proyek sumber
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
Pada langkah ini, kami menentukan jalur ke file Proyek sumber (`ResourceUsageView.mpp` ) dan gunakan`Project` kelas untuk membacanya.
## Langkah 2: Tentukan SaveOptions dengan Pengaturan Skala Waktu yang Diperlukan
```java
// Tentukan SaveOptions dengan pengaturan TimeScale yang diperlukan sebagai Hari
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Di sini, kami mendefinisikan`SaveOptions` dengan yang diperlukan`TimeScale` pengaturan. Dalam contoh ini, kami menetapkan`TimeScale` ke hari.
## Langkah 3: Atur Format Presentasi ke ResourceUsage
```java
// Atur format Presentasi ke ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Kami mengatur format presentasi menjadi`ResourceUsage`, menunjukkan bahwa kita ingin merender tampilan Penggunaan Sumber Daya.
## Langkah 4: Simpan Proyek
```java
// Simpan Proyek
project.save(dataDir + days, options);
```
Terakhir, kami menyimpan Proyek dengan opsi yang ditentukan. Dalam contoh ini, file keluaran akan disimpan sebagai`result_days.pdf`.
## Langkah 5: Render Tampilan untuk Pengaturan Skala Waktu Lainnya
Ulangi Langkah 2 hingga 4 untuk merender tampilan dengan pengaturan Skala Waktu yang berbeda (ThirdsOfMonths dan Months).
```java
// Atur pengaturan Skala Waktu ke ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Simpan Proyek
project.save(thirds, options);
// Atur pengaturan Skala Waktu ke Bulan
options.setTimescale(Timescale.Months);
// Simpan proyek
project.save(dataDir + months, options);
```
 Pastikan untuk mengubah`Timescale` pengaturan yang sesuai untuk setiap tampilan.

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara menggunakan Aspose.Tasks untuk Java untuk merender tampilan Penggunaan Sumber Daya Proyek MS dan Lembar. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat secara efisien menghasilkan tampilan ini dalam format PDF, memfasilitasi visualisasi dan analisis data proyek Anda yang lebih baik.
## FAQ
### Bisakah Aspose.Tasks merender tampilan lain selain Penggunaan Sumber Daya dan Lembar?
Aspose.Tasks mendukung rendering berbagai tampilan seperti tampilan Gantt Chart, Penggunaan Tugas, dan Kalender, antara lain.
### Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?
Ya, Aspose.Tasks mendukung berbagai format file Microsoft Project, termasuk format MPP, MPT, dan XML.
### Bisakah saya menyesuaikan tampilan tampilan yang dirender menggunakan Aspose.Tasks?
Sangat! Aspose.Tasks menyediakan opsi ekstensif untuk menyesuaikan tampilan dan tata letak tampilan yang diberikan agar sesuai dengan kebutuhan spesifik Anda.
### Apakah Aspose.Tasks memerlukan Microsoft Project untuk diinstal pada sistem?
Tidak, Aspose.Tasks adalah perpustakaan mandiri dan tidak memerlukan instalasi Microsoft Project agar dapat berfungsi.
### Apakah dukungan teknis tersedia untuk pengguna Aspose.Tasks?
 Ya, pengguna Aspose.Tasks dapat memanfaatkan dukungan teknis melalui[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).