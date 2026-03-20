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

# Ekspor ke PDF dan Kurangi Jarak Antara Daftar Tugas dan Footer di Aspose.Tasks

## Perkenalan
Dalam tutorial ini Anda akan menemukan **cara mengekspor proyek ke PDF** sekaligus mengurangi ruang yang tidak diinginkan antara daftar tugas dan footer dalam file Microsoft Project. Pada akhir panduan Anda akan dapat menghasilkan PDF bersih, gambar PNG, dan halaman HTML dengan tata letak yang kompak menggunakan Aspose.Tasks untuk Java. Mari kita jalani proses langkah demi langkah.

## Jawaban Cepat
- **Apa arti “ekspor proyek ke PDF”?** Itu mengubah file MPP menjadi dokumen PDF yang mempertahankan tugas, garis waktu, dan pemformatan.
- **Mengapa mengurangi jarak footer?** Jarak yang lebih kecil menghasilkan laporan yang lebih rapat dan tampak lebih profesional, terutama untuk dokumen yang dicetak atau ditampilkan di web.
- ** meminta saya juga menyimpan proyek sebagai gambar?** Ya – Aspose.Tasks mendukung PNG, JPEG, dan format gambar lainnya.
- **Apakah saya memerlukan lisensi khusus?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.
- **Versi Java apa yang diperlukan?** Java8 atau yang lebih tinggi bekerja dengan pustaka Aspose.Tasks saat ini.

## Apa itu “ekspor proyek ke PDF”?
Mengekspor proyek ke PDF mengubah struktur internal MPP menjadi dokumen portabel yang dapat dibuka di perangkat apa pun tanpa memerlukan Microsoft Project. Ini ideal untuk berbagi laporan status, pembaruan pemangku kepentingan, atau mengarsipkan rencana proyek.

## Mengapa Mengurangi Kesenjangan Footer?
Jarak footer default dapat menambah ruang putih yang tidak perlu, menyebabkan masalah paginasi dan tampilan yang tidak seimbang. Memperluas jarak memastikan konten Anda memanfaatkan halaman secara efisien, membuat PDF atau gambar akhir lebih mudah dibaca.

## Bagaimana Cara Mengurangi Kesenjangan Antara Daftar Tugas dan Footer?
Aspose.Tasks menyediakan opsi `setReduceFooterGap(true)` untuk operasi penyimpanan gambar, PDF, dan HTML. Mengaktifkan flag ini memberi tahu mesin untuk memampatkan ruang antara baris tugas terakhir dan footer halaman.

## Simpan Proyek sebagai Gambar dengan Aspose.Tasks
Jika Anda memerlukan jadwal visual snapshot, Anda dapat **menyimpan proyek sebagai gambar** (PNG) sambil menerapkan pengaturan pengurangan jarak yang sama.

## Ekspor Proyek Java ke PDF
Bagian-bagian berikut memandu alur kerja **ekspor proyek java** lengkap, mulai dari memuat file MPP hingga menyimpannya dalam tiga format berbeda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK) – versi8 atau lebih baru.
2. Aspose.Tasks untuk Java Library – unduh dari [di sini](https://releases.aspose.com/tasks/java/).

## Impor Paket
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

## Langkah 1: Berikan Jalur ke Direktori Data Anda
```java
String dataDir = "Your Data Directory";
```
Pastikan untuk mengganti `"Your Data Directory"` dengan jalur ke direktori data Anda yang berisi file Microsoft Project (`HomeMovePlan.mpp` dalam contoh ini).

## Langkah 2: Baca File MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Baris kode ini membaca file Microsoft Project bernama `HomeMovePlan.mpp`.

## Langkah 3: Atur ImageSaveOptions (Simpan Proyek sebagai Gambar)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Konfigurasikan opsi penyimpanan gambar, mengatur `ReduceFooterGap` ke `true` untuk mengurangi jarak antara daftar tugas dan footer.

## Langkah 4: Simpan sebagai Gambar
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Simpan proyek sebagai gambar dengan opsi yang telah dikonfigurasi.

## Langkah 5: Atur PdfSaveOptions (Ekspor Proyek ke PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Tentukan opsi penyimpanan PDF, pastikan `ReduceFooterGap` diatur ke `true`.

## Langkah 6: Simpan sebagai PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Simpan proyek sebagai PDF dengan opsi yang telah dikonfigurasi.

## Langkah 7: Atur HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Tentukan opsi penyimpanan HTML, mengatur `ReduceFooterGap` ke `true`.

## Langkah 8: Simpan sebagai HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Simpan proyek sebagai file HTML dengan opsi yang telah dikonfigurasi.

## Kesimpulan
Kesimpulannya, mengurangi jarak antara daftar tugas dan footer dalam file Microsoft Project adalah proses yang sederhana dengan Aspose.Tasks untuk Java. Dengan mengikuti langkah‑langkah yang dijelaskan dalam tutorial ini, Anda dapat dengan efisien **mengekspor proyek ke PDF**, menyimpan sebagai gambar, atau menghasilkan HTML sambil menjaga tata letak tetap rapat dan profesional.

## Pertanyaan Umum (Tambahan)

**Q: Bagaimana pengurangan jarak footer mempengaruhi paginasi?**
A: Itu meminimalkan ruang kosong di bagian bawah setiap halaman, memungkinkan lebih banyak tugas memuat dalam satu halaman dan mengurangi jumlah total halaman.

**Q: Bisakah saya menerapkan pengaturan pengurangan jarak hanya pada satu halaman?**
A: Ya, dengan mengatur `setRenderToSinglePage(true)` dalam `ImageSaveOptions` Anda dapat mengontrol paginasi sambil tetap mengurangi jarak.

**Q: Apakah opsi `setReduceFooterGap` tersedia untuk format output lain?**
A: Saat ini opsi tersebut didukung untuk mengekspor PNG, PDF, dan HTML. Untuk format lain Anda mungkin perlu menyesuaikan tata letak secara manual.

**Q: Bagaimana jika proyek saya berisi bidang khusus—apakah mereka tetap dipertahankan?**
A: Semua bidang khusus dipertahankan selama ekspor; Penyesuaian tata letak hanya mempengaruhi spasi, bukan data.

**Q: Apakah perpustakaan ini menangani proyek besar secara efisien?**
A: Aspose.Tasks melakukan streaming data dan dapat memproses file MPP berukuran besar; Namun, pastikan memori yang cukup saat mengekspor ke gambar beresolusi tinggi.

---

**Terakhir Diperbarui:** 17-12-2025
**Diuji Dengan:** Aspose.Tasks 24.11 untuk Java
**Penulis:** Beranggapan 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}