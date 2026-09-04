---
date: 2026-06-15
description: Pelajari cara mengonversi mpp ke pdf dan merender tampilan Resource Usage
  dan Sheet menggunakan Aspose.Tasks untuk Java. Ikuti panduan langkah‑demi‑langkah
  kami untuk mengatur timescale dan menghasilkan laporan PDF terperinci dengan mudah.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Konversi MPP ke PDF dan Render Tampilan Resource Usage View – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Konversi MPP ke PDF dan Render Tampilan Resource Usage View – Aspose.Tasks
url: /id/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi MPP ke PDF dan Render Tampilan Penggunaan Sumber Daya – Aspose.Tasks

Dalam tutorial ini Anda akan belajar **cara mengonversi mpp ke pdf** sambil merender tampilan Resource Usage dan Sheet dari file Microsoft Project. Menggunakan Aspose.Tasks untuk Java menghilangkan kebutuhan akan Microsoft Project di server, memberi Anda cara cepat dan andal untuk membuat laporan PDF dari file MPP. Kami juga akan menunjukkan **cara mengatur timescale** sehingga output sesuai dengan kebutuhan pelaporan Anda.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Tasks?** Ia membaca, memodifikasi, dan mengonversi file Microsoft Project (MPP) tanpa memerlukan MS Project terinstal.  
- **Bisakah saya mengonversi MPP ke PDF dalam satu baris kode?** Ya – muat Project, atur SaveOptions, dan panggil `save`.  
- **Skala waktu apa yang didukung?** Days, ThirdsOfMonths, dan Months.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penerapan non‑trial.  
- **Apakah perpustakaan ini kompatibel dengan Java 8+?** Tentu – ia mendukung Java 8 dan versi selanjutnya.

## Apa itu konversi mpp ke pdf?
*Convert mpp to pdf* mengacu pada proses mengambil file Microsoft Project (.mpp) dan menghasilkan versi Portable Document Format (PDF) yang secara akurat mereproduksi tabel, jadwal, diagram, dan alokasi sumber daya proyek. PDF yang dihasilkan dapat dengan mudah dibagikan, dicetak, dan diarsipkan tanpa memerlukan Microsoft Project terinstal pada mesin penerima.

## Mengapa Mengonversi Proyek ke PDF dengan Aspose.Tasks?
Aspose.Tasks mendukung **lebih dari 50 format input dan output** dan dapat merender proyek berukuran ratusan halaman tanpa memuat seluruh file ke memori, mengurangi penggunaan RAM hingga 70 %. Output PDF mempertahankan tabel, diagram, dan alokasi sumber daya, menjadikannya ideal untuk distribusi kepada pemangku kepentingan dan pengarsipan.

## Prasyarat
1. **Java Development Kit (JDK)** – Java 8 atau yang lebih baru terinstal di mesin Anda.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [download page](https://releases.aspose.com/tasks/java/).  

## Cara mengonversi mpp ke pdf menggunakan Aspose.Tasks untuk Java?
Muat file MPP sumber Anda, konfigurasikan timescale yang diinginkan, atur format presentasi ke **ResourceUsage**, dan simpan hasilnya sebagai PDF. Alur end‑to‑end ini hanya memerlukan beberapa panggilan API dan berjalan dalam waktu kurang dari satu detik untuk ukuran proyek tipikal.

### Langkah 1: Baca Proyek Sumber
Kelas `Project` mewakili file Microsoft Project yang dimuat ke memori, memberikan akses ke data dan strukturnya.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Langkah 2: Definisikan SaveOptions dengan Pengaturan TimeScale yang Diperlukan
`SaveOptions` mengonfigurasi cara proyek disimpan, memungkinkan Anda menentukan pengaturan spesifik format seperti timescale.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Langkah 3: Atur Format Presentasi ke ResourceUsage
`PresentationFormat` menentukan tampilan Project (misalnya, ResourceUsage) yang dirender dalam dokumen output.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Langkah 4: Simpan Proyek sebagai PDF
`project.save` menulis proyek ke file menggunakan `SaveOptions` yang diberikan, menghasilkan PDF akhir.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Langkah 5: Render Tampilan untuk Pengaturan TimeScale Lain
Ulangi langkah sebelumnya, mengubah nilai `TimeScale` untuk merender tampilan timescale tambahan.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Langkah 6: Opsional – Mengonversi Beberapa Proyek dalam Batch
Jika Anda perlu **mengonversi proyek ke pdf** untuk banyak file, letakkan logika di atas dalam loop yang mengiterasi direktori berisi file *.mpp*. Pendekatan ini **menyimpan file ms project pdf** secara massal dengan perubahan kode minimal.  
Kode berikut menunjukkan contoh lengkap mengonversi file MPP ke PDF dengan pengaturan yang diinginkan.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Masalah Umum dan Solusinya
- **Font yang hilang di PDF** – Pastikan font yang diperlukan terinstal di server atau sematkan mereka melalui `PdfSaveOptions`.  
- **File proyek besar menyebabkan OutOfMemoryError** – Gunakan `LoadOptions.setLoadAllResources(false)` untuk memuat sumber daya sesuai permintaan.  
- **Rendering timescale yang tidak tepat** – Verifikasi bahwa `options.setTimeScale(TimeScale.Days)` (atau enum lain) sesuai dengan granularitas yang diinginkan.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah Aspose.Tasks merender tampilan lain selain Resource Usage dan Sheet?**  
A: Ya, ia juga mendukung Gantt Chart, Task Usage, Calendar, dan banyak tampilan tambahan.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
A: Tentu – ia menangani format MPP, MPT, dan XML dari Project 2000 hingga Project 2021.

**Q: Bisakah saya menyesuaikan tampilan render?**  
A: Ya, Anda dapat memodifikasi warna, font, dan tata letak kolom melalui `PdfSaveOptions` dan `PresentationOptions`.

**Q: Apakah Aspose.Tasks memerlukan Microsoft Project terinstal?**  
A: Tidak, ini adalah perpustakaan mandiri dan bekerja pada lingkungan apa pun yang kompatibel dengan Java.

**Q: Di mana saya dapat mendapatkan dukungan teknis?**  
A: Dukungan tersedia melalui [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).

---

**Terakhir Diperbarui:** 2026-06-15  
**Diuji Dengan:** Aspose.Tasks 24.12 for Java  
**Penulis:** Aspose

## Tutorial Terkait

- [Render Tampilan Resource Usage dan Sheet di Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Cara Mengekspor PDF di Aspose.Tasks – Save As PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Cara Membuat File MPP dengan Aspose.Tasks untuk Java](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}