---
title: Mengurangi Kesenjangan Antara Daftar Tugas dan Footer di Aspose.Tasks
linktitle: Mengurangi Kesenjangan Antara Daftar Tugas dan Footer di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengurangi kesenjangan antara daftar tugas dan footer MS Project menggunakan Aspose.Tasks untuk Java. Optimalkan tata letak dokumen proyek dengan mudah.
type: docs
weight: 10
url: /id/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengurangi kesenjangan antara daftar tugas dan footer di file Microsoft Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda akan dapat mengoptimalkan tata letak dokumen proyek Anda dengan mudah.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks untuk Perpustakaan Java: Unduh dan sertakan perpustakaan Aspose.Tasks untuk Java dalam proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
Sebelum masuk ke bagian pengkodean, mari impor paket yang diperlukan:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Langkah 1: Berikan Jalur ke Direktori Data Anda
```java
String dataDir = "Your Data Directory";
```
 Pastikan untuk mengganti`"Your Data Directory"` dengan jalur ke direktori data aktual tempat file Microsoft Project Anda (`HomeMovePlan.mpp` dalam contoh ini) berada.
## Langkah 2: Baca File MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Baris kode ini membaca nama file Microsoft Project`HomeMovePlan.mpp`.
## Langkah 3: Atur ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Konfigurasikan opsi penyimpanan gambar, pengaturan`ReduceFooterGap` ke`true` untuk mengurangi kesenjangan antara daftar tugas dan footer.
## Langkah 4: Simpan sebagai Gambar
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Simpan proyek sebagai gambar dengan opsi yang dikonfigurasi.
## Langkah 5: Setel PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Tentukan opsi penyimpanan PDF, pastikan untuk mengaturnya`ReduceFooterGap` ke`true`.
## Langkah 6: Simpan sebagai PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Simpan proyek sebagai PDF dengan opsi yang dikonfigurasi.
## Langkah 7: Tetapkan HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // disetel ke benar
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Tentukan opsi penyimpanan HTML, pengaturan`ReduceFooterGap` ke`true`.
## Langkah 8: Simpan sebagai HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Simpan proyek sebagai file HTML dengan opsi yang dikonfigurasi.

## Kesimpulan
Kesimpulannya, mengurangi kesenjangan antara daftar tugas dan footer di file Microsoft Project adalah proses yang mudah dengan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengoptimalkan tata letak dokumen proyek Anda secara efisien.

## FAQ

### T: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?

J: Aspose.Tasks mendukung format Microsoft Project 2003-2019, memastikan kompatibilitas di berbagai versi.

### T: Bisakah saya mengkustomisasi tampilan footer di dokumen proyek saya?

J: Ya, Aspose.Tasks menyediakan opsi luas untuk menyesuaikan tampilan footer, termasuk mengurangi kesenjangan dan menyesuaikan penempatan konten.

### T: Apakah Aspose.Tasks mendukung penyimpanan proyek dalam format selain PNG, PDF, dan HTML?

J: Ya, Aspose.Tasks mendukung berbagai format, antara lain XLSX, XML, dan MPP.

### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?

 J: Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### T: Di mana saya bisa mendapatkan dukungan jika saya mengalami masalah apa pun saat menggunakan Aspose.Tasks?

 A: Anda bisa mendapatkan bantuan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).