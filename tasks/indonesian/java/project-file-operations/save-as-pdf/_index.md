---
date: 2026-03-27
description: Pelajari cara menyimpan proyek sebagai PDF menggunakan Aspose.Tasks untuk
  Java, panduan sederhana untuk mengonversi MPP ke PDF dan mengekspor file proyek
  secara efisien.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menyimpan Proyek sebagai PDF dengan Aspose.Tasks – Panduan Ekspor
url: /id/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menyimpan Proyek sebagai PDF dengan Aspise.Tasks – Panduan Ekspor

## Introduction
Dalam tutorial ini, Anda akan menemukan **cara menyimpan proyek sebagai pdf** menggunakan Aspose.Tasks untuk Java. Kami akan memandu Anda melalui semua hal mulai dari konversi satu baris hingga penyesuaian PDF lanjutan, sehingga Anda dapat mengubah MPP (atau format lain yang didukung) menjadi dokumen PDF yang rapi dan dapat dibagikan. Baik Anda membutuhkan laporan cetak cepat atau diagram Gantt yang sepenuhnya bergaya, langkah‑langkah ini akan membantu Anda mencapainya dengan cepat.

## Quick Answers
- **Apa arti “export PDF” dalam Aspose.Tasks?** Itu berarti mengonversi file proyek (misalnya MPP) menjadi dokumen PDF yang mempertahankan tata letak visual.  
- **Versi perpustakaan mana yang dibutuhkan?** Versi Aspose.Tasks untuk Java apa pun yang mendukung `PdfSaveOptions` (disarankan menggunakan rilis terbaru).  
- **Apakah saya memerlukan lisensi untuk konversi ini?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyesuaikan tampilan PDF?** Ya – Anda dapat mengatur timescale, legenda, dan `PdfSaveOptions` lainnya.  
- **Apakah konversi cepat untuk proyek besar?** Biasanya dalam hitungan detik; kinerja tergantung pada ukuran proyek dan opsi yang dipilih.

## What is “save project as pdf” in the context of Aspose.Tasks?
Menyimpan proyek sebagai PDF dengan Aspose.Tasks berarti mengambil file proyek (seperti `.mpp`, `.xml`, atau `.xlsx`) dan menghasilkan PDF yang mencerminkan diagram Gantt, tampilan penggunaan tugas, atau format presentasi lain yang Anda konfigurasikan. Ini berguna untuk pelaporan, dokumentasi, atau berbagi tampilan hanya‑baca dengan pemangku kepentingan non‑teknis.

## Why Export Gantt Chart to PDF?
- **Keterbacaan universal:** PDF dapat dibuka di perangkat apa pun tanpa memerlukan perangkat lunak proyek asli.  
- **Presentasi profesional:** Mempertahankan warna, font, dan tata letak untuk laporan yang ditujukan kepada klien.  
- **Distribusi mudah:** Bagikan melalui email, intranet, atau penyimpanan cloud tanpa kekhawatiran kontrol versi.  
- **Kepatuhan & arsip:** PDF ideal untuk penyimpanan jangka panjang dan kepatuhan regulasi.

## Prerequisites
Sebelum Anda memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Java Development Kit (JDK):** JDK 8 atau yang lebih baru terpasang di mesin Anda.  
2. **Aspose.Tasks for Java Library:** Unduh perpustakaan dari situs resmi [here](https://releases.aspose.com/tasks/java/).  
3. **File Proyek:** Miliki file proyek yang sudah ada (misalnya `HomeMovePlan.mpp`) siap untuk konversi.

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Step‑by‑Step Guide

### Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Ganti `"Your Data Directory"` dengan jalur absolut tempat file `.mpp` Anda berada. Ini memuat proyek ke memori sehingga Anda dapat memanipulasi atau mengekspornya.

### Step 2: Save the Project as PDF (Basic Conversion)
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Baris di atas melakukan operasi **save project as pdf** yang sederhana, menghasilkan `Project5.pdf` di folder yang sama.

### Step 3: Fit Contents to Cell Size (Advanced PDF Save Options)
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Di sini kami menunjukkan penggunaan **pdf save options** untuk mengontrol tata letak:
- `setFitContent(true)` memaksa konten menyesuaikan lebar sel.  
- `setTimescale(Timescale.Months)` mengubah skala waktu menjadi bulan.  
- `setPresentationFormat(PresentationFormat.TaskUsage)` memilih tampilan Task Usage.

### Step 4: Hide Legends (Cleaner Output)
```java
o.setLegendOnEachPage(false);
```
Menonaktifkan legenda dapat membuat PDF lebih ringkas, terutama untuk proyek besar.

### Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Langkah akhir ini menulis PDF menggunakan opsi khusus yang telah didefinisikan di atas, menghasilkan dokumen berskala bulan yang bersih tanpa legenda per‑halaman.

## Export Gantt Chart to PDF – Custom Styling
Jika Anda ingin mengekspor hanya diagram Gantt dengan tampilan tertentu, atur `PresentationFormat` ke `GanttChart` dan sesuaikan opsi tambahan seperti `setBarColor` atau `setShowCriticalTasks`. Pendekatan ini memungkinkan Anda **export gantt chart to pdf** dengan kontrol penuh atas elemen visual.

## Common Issues & Tips
- **File not found:** Pastikan `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) dan mengarah ke direktori yang benar.  
- **Blank pages:** Verifikasi bahwa `PresentationFormat` yang dipilih sesuai dengan tampilan yang Anda harapkan (mis., Gantt, Task Usage).  
- **Large files take longer:** Pertimbangkan mengatur `o.setFitContent(false)` untuk proyek yang sangat besar guna mengurangi waktu pemrosesan.  

## Frequently Asked Questions

**Q: Apakah Aspose.Tasks kompatibel dengan semua versi Java?**  
A: Ya, Aspose.Tasks mendukung versi Java mulai dari JDK 6 ke atas.

**Q: Bisakah saya menyesuaikan tampilan output PDF?**  
A: Tentu! Aspose.Tasks menyediakan banyak **pdf save options**—seperti timescale, visibilitas legenda, dan format presentasi—untuk menyesuaikan PDF sesuai kebutuhan Anda.

**Q: Apakah Aspose.Tasks mendukung format file lain untuk konversi?**  
A: Ya, Anda dapat mengonversi antara MPP, XML, XLSX, dan banyak format lainnya, menjadikannya alat serbaguna untuk **convert mpp to pdf** dan transformasi lainnya.

**Q: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks?**  
A: Ya, Anda dapat mendapatkan percobaan gratis Aspose.Tasks dari [here](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks?**  
A: Untuk dukungan dan bantuan, kunjungi forum resmi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Dengan mengikuti panduan ini, Anda kini tahu **cara menyimpan proyek sebagai pdf** dari proyek Java mana pun menggunakan Aspose.Tasks, mulai dari penyimpanan satu baris sederhana hingga penyesuaian lanjutan dengan `PdfSaveOptions`. Gunakan teknik ini untuk menghasilkan PDF yang rapi dan dapat dibagikan untuk pelaporan, presentasi klien, atau keperluan arsip.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}