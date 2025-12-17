---
date: 2025-12-17
description: Pelajari cara mengekspor proyek ke PDF, mengurangi celah footer, dan
  menyimpan proyek sebagai gambar menggunakan Aspose.Tasks untuk Java. Optimalkan
  tata letak MS Project Anda dengan mudah.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ekspor Proyek ke PDF dan Kurangi Jarak antara Daftar Tugas dan Footer di Aspose.Tasks
url: /id/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekspor Proyek ke PDF dan Kurangi Jarak Antara Daftar Tugas dan Footer di Aspose.Tasks

## Introduction  
Dalam tutorial ini Anda akan menemukan **cara mengekspor proyek ke PDF** sekaligus mengurangi ruang yang tidak diinginkan antara daftar tugas dan footer dalam file Microsoft Project. Pada akhir panduan Anda akan dapat menghasilkan PDF bersih, gambar PNG, dan halaman HTML dengan tata letak yang kompak menggunakan Aspose.Tasks untuk Java. Mari kita jalani proses langkah demi langkah.

## Quick Answers  
- **Apa arti “export project to PDF”?** Itu mengonversi file MPP menjadi dokumen PDF yang mempertahankan tugas, garis waktu, dan pemformatan.  
- **Mengapa mengurangi jarak footer?** Jarak yang lebih kecil menghasilkan laporan yang lebih rapat dan tampak lebih profesional, terutama untuk dokumen yang dicetak atau ditampilkan di web.  
- **Bisakah saya juga menyimpan proyek sebagai gambar?** Ya – Aspose.Tasks mendukung PNG, JPEG, dan format gambar lainnya.  
- **Apakah saya memerlukan lisensi khusus?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Versi Java apa yang diperlukan?** Java 8 atau yang lebih tinggi bekerja dengan pustaka Aspose.Tasks saat ini.

## What is “export project to PDF”?  
Mengekspor proyek ke PDF mengubah struktur internal MPP menjadi dokumen portabel yang dapat dibuka di perangkat apa pun tanpa memerlukan Microsoft Project. Ini ideal untuk berbagi laporan status, pembaruan pemangku kepentingan, atau mengarsipkan rencana proyek.

## Why Reduce Footer Gap?  
Jarak footer default dapat menambah ruang putih yang tidak perlu, menyebabkan masalah paginasi dan tampilan yang tidak seimbang. Mengurangi jarak memastikan konten Anda memanfaatkan halaman secara efisien, membuat PDF atau gambar akhir lebih mudah dibaca.

## How to Reduce Gap Between Tasks List and Footer?  
Aspose.Tasks menyediakan opsi `setReduceFooterGap(true)` untuk operasi penyimpanan gambar, PDF, dan HTML. Mengaktifkan flag ini memberi tahu mesin untuk memampatkan ruang antara baris tugas terakhir dan footer halaman.

## Save Project as Image with Aspose.Tasks  
Jika Anda memerlukan snapshot visual jadwal Anda, Anda dapat **menyimpan proyek sebagai gambar** (PNG) sambil menerapkan pengaturan pengurangan jarak yang sama.

## Java Project Export to PDF  
Bagian-bagian berikut memandu alur kerja **ekspor proyek java** lengkap, mulai dari memuat file MPP hingga menyimpannya dalam tiga format berbeda.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK) – versi 8 atau lebih baru.  
2. Aspose.Tasks for Java Library – unduh dari [di sini](https://releases.aspose.com/tasks/java/).  

## Import Packages
Sebelum masuk ke bagian kode, mari impor paket yang diperlukan:
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

## Step 1: Provide the Path to Your Data Directory
```java
String dataDir = "Your Data Directory";
```
Pastikan untuk mengganti `"Your Data Directory"` dengan jalur ke direktori data Anda yang berisi file Microsoft Project (`HomeMovePlan.mpp` dalam contoh ini).

## Step 2: Read the MPP File
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Baris kode ini membaca file Microsoft Project bernama `HomeMovePlan.mpp`.

## Step 3: Set ImageSaveOptions (Save Project as Image)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Konfigurasikan opsi penyimpanan gambar, mengatur `ReduceFooterGap` ke `true` untuk mengurangi jarak antara daftar tugas dan footer.

## Step 4: Save as Image
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Simpan proyek sebagai gambar dengan opsi yang telah dikonfigurasi.

## Step 5: Set PdfSaveOptions (Export Project to PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Tentukan opsi penyimpanan PDF, pastikan `ReduceFooterGap` diatur ke `true`.

## Step 6: Save as PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Simpan proyek sebagai PDF dengan opsi yang telah dikonfigurasi.

## Step 7: Set HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Tentukan opsi penyimpanan HTML, mengatur `ReduceFooterGap` ke `true`.

## Step 8: Save as HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Simpan proyek sebagai file HTML dengan opsi yang telah dikonfigurasi.

## Conclusion  
Kesimpulannya, mengurangi jarak antara daftar tugas dan footer dalam file Microsoft Project adalah proses yang sederhana dengan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah yang dijelaskan dalam tutorial ini, Anda dapat dengan efisien **mengekspor proyek ke PDF**, menyimpannya sebagai gambar, atau menghasilkan HTML sambil menjaga tata letak tetap rapat dan profesional.

## FAQ's

### Q: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?

A: Aspose.Tasks mendukung format Microsoft Project 2003‑2019, memastikan kompatibilitas di berbagai versi.

### Q: Bisakah saya menyesuaikan tampilan footer dalam dokumen proyek saya?

A: Ya, Aspose.Tasks menyediakan opsi luas untuk menyesuaikan tampilan footer, termasuk mengurangi jarak dan mengatur penempatan konten.

### Q: Apakah Aspose.Tasks mendukung penyimpanan proyek dalam format selain PNG, PDF, dan HTML?

A: Ya, Aspose.Tasks mendukung berbagai format, termasuk XLSX, XML, dan MPP, serta lainnya.

### Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks?

A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks dari [di sini](https://releases.aspose.com/).

### Q: Di mana saya dapat mendapatkan dukungan jika saya mengalami masalah saat menggunakan Aspose.Tasks?

A: Anda dapat mendapatkan bantuan dari forum komunitas Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

## Frequently Asked Questions (Additional)

**Q: Bagaimana pengurangan jarak footer memengaruhi paginasi?**  
A: Itu meminimalkan ruang kosong di bagian bawah setiap halaman, memungkinkan lebih banyak tugas muat dalam satu halaman dan mengurangi total jumlah halaman.

**Q: Bisakah saya menerapkan pengaturan pengurangan jarak hanya pada satu halaman?**  
A: Ya, dengan mengatur `setRenderToSinglePage(true)` dalam `ImageSaveOptions` Anda dapat mengontrol paginasi sambil tetap mengurangi jarak.

**Q: Apakah opsi `setReduceFooterGap` tersedia untuk format output lain?**  
A: Saat ini opsi tersebut didukung untuk ekspor PNG, PDF, dan HTML. Untuk format lain Anda mungkin perlu menyesuaikan tata letak secara manual.

**Q: Bagaimana jika proyek saya berisi bidang khusus—apakah mereka tetap dipertahankan?**  
A: Semua bidang khusus dipertahankan selama ekspor; penyesuaian tata letak hanya memengaruhi spasi, bukan data.

**Q: Apakah pustaka ini menangani proyek besar secara efisien?**  
A: Aspose.Tasks melakukan streaming data dan dapat memproses file MPP berukuran besar; namun, pastikan memori yang cukup saat mengekspor ke gambar beresolusi tinggi.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}