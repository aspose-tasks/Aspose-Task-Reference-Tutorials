---
date: 2026-05-20
description: Pelajari cara mengekspor proyek ke PDF, mengurangi jarak footer, dan
  menyimpan proyek sebagai gambar menggunakan Aspose.Tasks untuk Java. Optimalkan
  tata letak MS Project Anda dengan mudah.
keywords:
- export project to pdf
- save project as image
- reduce footer gap
- remove white space pdf
- how to reduce footer gap
linktitle: Ekspor Proyek ke PDF dan Kurangi Jarak Antara Daftar Tugas dan Footer di
  Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to export project to PDF, reduce footer gap, and save project
    as image using Aspose.Tasks for Java. Optimize your MS Project layout effortlessly.
  headline: Export Project to PDF and Reduce Gap Between Tasks List and Footer in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It minimizes blank space at the bottom of each page, allowing more tasks
      to fit on a single page and reducing the total page count.
    question: How does reducing the footer gap affect pagination?
  - answer: Yes, by setting `setRenderToSinglePage(true)` in `ImageSaveOptions` you
      can control pagination while still reducing the gap.
    question: Can I apply the same gap‑reduction setting to a single page only?
  - answer: Currently it is supported for PNG, PDF, and HTML exports. For other formats
      you may need to adjust layout manually.
    question: Is the `setReduceFooterGap` option available for other output formats?
  - answer: All custom fields are retained during export; the layout adjustments only
      affect spacing, not data.
    question: What if my project contains custom fields—are they preserved?
  - answer: Aspose.Tasks streams data and can process multi‑hundred‑page MPP files
      without loading the entire file into memory; however, allocate sufficient heap
      space when exporting high‑resolution images.
    question: Does the library handle large projects efficiently?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Ekspor Proyek ke PDF dan Kurangi Jarak Antara Daftar Tugas dan Footer di Aspose.Tasks
url: /id/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekspor Proyek ke PDF dan Kurangi Jarak Antara Daftar Tugas dan Footer di Aspose.Tasks

## Pendahuluan  
Dalam tutorial ini Anda akan menemukan **cara mengekspor proyek ke PDF** sekaligus mengurangi ruang yang tidak diinginkan antara daftar tugas dan footer dalam file Microsoft Project. Pada akhir panduan Anda akan dapat menghasilkan PDF bersih, gambar PNG, dan halaman HTML dengan tata letak yang kompak menggunakan Aspose.Tasks untuk Java. Mari kita jalani proses langkah demi langkah, dan Anda akan melihat mengapa hal ini penting untuk pelaporan profesional.

## Jawaban Cepat  
- **Apa arti “export project to PDF”?** Itu mengonversi file MPP menjadi dokumen PDF yang mempertahankan tugas, garis waktu, dan format.  
- **Mengapa mengurangi jarak footer?** Jarak yang lebih kecil menghasilkan laporan yang lebih rapat dan terlihat lebih profesional, terutama untuk dokumen yang dicetak atau dilihat di web.  
- **Apakah saya juga dapat menyimpan proyek sebagai gambar?** Ya – Aspose.Tasks mendukung format PNG, JPEG, dan format gambar lainnya.  
- **Apakah saya memerlukan lisensi khusus?** Versi percobaan gratis tersedia; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Versi Java mana yang diperlukan?** Java 8 atau yang lebih tinggi bekerja dengan perpustakaan Aspose.Tasks saat ini.  

## Apa itu “export project to PDF”?  
Mengekspor proyek ke PDF mengubah struktur internal MPP menjadi dokumen portabel yang dapat dibuka di perangkat apa pun tanpa memerlukan Microsoft Project. Ini ideal untuk berbagi laporan status, pembaruan pemangku kepentingan, atau mengarsipkan rencana proyek. Dokumen ini mempertahankan tata letak, warna, dan hierarki tugas asli, memastikan PDF terlihat identik dengan file sumber.

## Mengapa Mengurangi Jarak Footer?  
Jarak footer default dapat menambahkan ruang putih yang tidak perlu, menyebabkan masalah paginasi dan tampilan yang tidak seimbang. Mengurangi jarak tersebut memastikan konten Anda memanfaatkan halaman secara efisien, membuat PDF atau gambar akhir lebih mudah dibaca. Tata letak yang lebih rapat juga mengurangi jumlah total halaman, yang dapat menurunkan biaya pencetakan dan meningkatkan navigasi di layar.

## Cara Mengurangi Jarak Antara Daftar Tugas dan Footer?  
`setReduceFooterGap` adalah properti Boolean yang mengontrol spasi footer selama ekspor.  
Aspose.Tasks menyediakan opsi `setReduceFooterGap(true)` untuk operasi penyimpanan gambar, PDF, dan HTML. Mengaktifkan flag ini memberi tahu mesin untuk memampatkan ruang antara baris tugas terakhir dan footer halaman. Ketika diatur ke true, renderer secara otomatis memangkas margin tanpa memotong data tugas apa pun, menghasilkan tata letak halaman yang lebih bersih.

## Simpan Proyek sebagai Gambar dengan Aspose.Tasks  
`ImageSaveOptions` mengonfigurasi cara proyek dirender ke file gambar.  
Kelas `ImageSaveOptions` memungkinkan Anda mengekspor snapshot jadwal sebagai PNG, JPEG, atau BMP. Ketika Anda juga mengaktifkan `setReduceFooterGap(true)`, gambar yang dihasilkan mencerminkan tata letak PDF yang kompak, memberikan visual yang bersih untuk presentasi atau dasbor.

## Ekspor Proyek Java ke PDF  
Bagian berikut menjelaskan alur kerja **ekspor proyek java** secara lengkap, mulai dari memuat file MPP hingga menyimpannya dalam tiga format berbeda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK) – versi 8 atau lebih baru.  
2. Aspose.Tasks for Java Library – unduh dari [di sini](https://releases.aspose.com/tasks/java/).  

## Impor Paket  
Sebelum menyelami bagian kode, mari impor paket yang diperlukan:

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
Pastikan untuk mengganti `"Your Data Directory"` dengan jalur ke direktori data Anda yang sebenarnya di mana file Microsoft Project (`HomeMovePlan.mpp` dalam contoh ini) berada.

## Langkah 2: Baca File MPP  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```  
Baris kode ini membaca file Microsoft Project bernama `HomeMovePlan.mpp`.

## Langkah 3: Atur ImageSaveOptions (Simpan Proyek sebagai Gambar)  
`ImageSaveOptions` mengonfigurasi cara proyek dirender ke file gambar.  
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
`PdfSaveOptions` menentukan pengaturan untuk mengekspor proyek ke format PDF.  
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```  
Tentukan opsi penyimpanan PDF, pastikan mengatur `ReduceFooterGap` ke `true`.

## Langkah 6: Simpan sebagai PDF  
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```  
Simpan proyek sebagai PDF dengan opsi yang telah dikonfigurasi.

## Langkah 7: Atur HtmlSaveOptions  
`HtmlSaveOptions` mengontrol konversi proyek ke HTML, termasuk opsi styling dan tata letak.  
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

## Kasus Penggunaan Umum dan Tips  
- **Pelaporan pemangku kepentingan:** Ekspor ke PDF dengan jarak footer yang dikurangi untuk menjaga laporan tetap ringkas dan ramah pencetakan.  
- **Snapshot dasbor:** Gunakan ekspor gambar ketika Anda membutuhkan visual cepat untuk Power BI atau Confluence.  
- **Penerbitan web:** Ekspor HTML mempertahankan interaktivitas dan dapat disematkan langsung ke portal intranet.  
- **Tips pro:** Untuk proyek yang sangat besar, tingkatkan `Resolution` dalam `ImageSaveOptions` menjadi 300 dpi untuk mempertahankan kejelasan sambil tetap mendapatkan manfaat dari pengurangan jarak.  

## Pertanyaan yang Sering Diajukan (Tambahan)

**Q:** Bagaimana pengurangan jarak footer memengaruhi paginasi?  
**A:** Itu meminimalkan ruang kosong di bagian bawah setiap halaman, memungkinkan lebih banyak tugas muat dalam satu halaman dan mengurangi total jumlah halaman.

**Q:** Bisakah saya menerapkan pengaturan pengurangan jarak yang sama hanya pada satu halaman?  
**A:** Ya, dengan mengatur `setRenderToSinglePage(true)` dalam `ImageSaveOptions` Anda dapat mengontrol paginasi sambil tetap mengurangi jarak.

**Q:** Apakah opsi `setReduceFooterGap` tersedia untuk format output lain?  
**A:** Saat ini didukung untuk ekspor PNG, PDF, dan HTML. Untuk format lain Anda mungkin perlu menyesuaikan tata letak secara manual.

**Q:** Bagaimana jika proyek saya berisi bidang khusus—apakah mereka tetap dipertahankan?  
**A:** Semua bidang khusus dipertahankan selama ekspor; penyesuaian tata letak hanya memengaruhi spasi, bukan data.

**Q:** Apakah perpustakaan ini menangani proyek besar secara efisien?  
**A:** Aspose.Tasks melakukan streaming data dan dapat memproses file MPP berjumlah ratusan halaman tanpa memuat seluruh file ke memori; namun, alokasikan ruang heap yang cukup saat mengekspor gambar beresolusi tinggi.

---

**Terakhir Diperbarui:** 2026-05-20  
**Diuji Dengan:** Aspose.Tasks 24.11 for Java  
**Penulis:** Aspose

## Tutorial Terkait

- [Simpan Proyek sebagai Gambar – Format 24bppRgb dengan Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspose.Tasks untuk Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Cara Membuat File MPP – Buat & Simpan Proyek Kosong dalam Format MPP dengan Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}