---
date: 2026-01-15
description: Pelajari cara menyimpan proyek sebagai PDF dan merender tampilan Penggunaan
  Sumber Daya serta Lembar MS Project menggunakan Aspose.Tasks untuk Java. Ikuti panduan
  langkah‑demi‑langkah kami untuk mengekspor proyek ke PDF dengan mudah.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Simpan Proyek sebagai PDF – Render Penggunaan Sumber Daya dan Tampilan Lembar
  di Aspose.Tasks
url: /id/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan Proyek sebagai PDF – Render Tampilan Penggunaan Sumber Daya dan Lembar di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan menemukan cara **save project as PDF** sambil merender tampilan Resource Usage dan Sheet dari file Microsoft Project. Baik Anda perlu menghasilkan laporan yang dapat dicetak untuk pemangku kepentingan atau mengonversi file MPP ke format yang dapat dilihat secara universal, Aspose.Tasks for Java membuat prosesnya sederhana—tanpa memerlukan instalasi Microsoft Project.

## Jawaban Cepat
- **Apa yang dilakukan “save project as pdf”?** Ini mengonversi file Project (MPP) menjadi dokumen PDF yang mempertahankan tampilan yang dipilih.  
- **Tampilan mana yang dapat diekspor?** Resource Usage, Sheet, Gantt, Task Usage, dan lainnya.  
- **Apakah saya dapat mengubah skala waktu di PDF?** Ya—opsinya termasuk Days, ThirdsOfMonths, dan Months.  
- **Apakah saya perlu menginstal Microsoft Project?** Tidak, Aspose.Tasks berfungsi secara mandiri.  
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi komersial diperlukan untuk penggunaan non‑trial.

## Apa itu “save project as PDF”?
Menyimpan proyek sebagai PDF membuat representasi statis dengan resolusi tinggi dari tampilan Project yang dipilih. Ini ideal untuk dibagikan kepada klien, pengarsipan, atau pencetakan tanpa mengungkapkan file proyek yang mendasarinya.

## Mengapa menggunakan Aspose.Tasks untuk mengekspor proyek ke PDF?
- **No external dependencies** – works on any platform supporting Java.  
- **Fine‑grained control** – you can select the view, timescale, and layout.  
- **High fidelity** – the PDF mirrors the appearance of the original Project view.  
- **Automation‑ready** – integrate into CI pipelines, reporting services, or batch converters.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi terbaru disarankan.  
2. **Aspose.Tasks for Java** – unduh dari [download page](https://releases.aspose.com/tasks/java/).

## Impor Paket
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Panduan Langkah demi Langkah

### Langkah 1: Baca Proyek Sumber
Muat file MPP yang ingin Anda konversi.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Langkah 2: Tentukan SaveOptions dengan Timescale yang Diperlukan (Ekspor Proyek ke PDF)
Konfigurasikan opsi ekspor PDF dan atur timescale yang diinginkan.  
*Di sini kami menggunakan **Days** sebagai contoh.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Langkah 3: Atur Presentation Format ke ResourceUsage
Pilih tampilan yang ingin Anda render. Dalam kasus ini, tampilan **Resource Usage**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Langkah 4: Simpan Proyek (Konversi MPP ke PDF)
Jalankan konversi dan hasilkan file PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Langkah 5: Render Tampilan untuk Pengaturan Timescale Lain (Ubah Timescale PDF)
Ulangi langkah-langkah sebelumnya untuk menghasilkan PDF dengan timescale berbeda seperti **ThirdsOfMonths** dan **Months**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Masalah Umum dan Solusinya
- **File not found errors** – Pastikan bahwa `dataDir` mengarah ke folder yang benar dan nama file MPP cocok persis.  
- **Blank PDF output** – Pastikan `PresentationFormat` cocok dengan tampilan yang berisi data (mis., ResourceUsage).  
- **Incorrect timescale** – Periksa kembali bahwa `options.setTimescale()` dipanggil sebelum setiap `project.save()`.

## Pertanyaan yang Sering Diajukan

### Apakah Aspose.Tasks dapat merender tampilan lain selain Resource Usage dan Sheet?
Aspose.Tasks mendukung perenderan berbagai tampilan seperti Gantt Chart, Task Usage, dan tampilan Kalender, di antara lainnya.

### Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?
Ya, Aspose.Tasks mendukung berbagai format file Microsoft Project, termasuk format MPP, MPT, dan XML.

### Apakah saya dapat menyesuaikan tampilan render menggunakan Aspose.Tasks?
Tentu saja! Aspose.Tasks menyediakan banyak opsi untuk menyesuaikan tampilan dan tata letak tampilan yang dirender sesuai dengan kebutuhan spesifik Anda.

### Apakah Aspose.Tasks memerlukan Microsoft Project terinstal di sistem?
Tidak, Aspose.Tasks adalah pustaka mandiri dan tidak memerlukan Microsoft Project terinstal untuk berfungsi.

### Apakah dukungan teknis tersedia untuk pengguna Aspose.Tasks?
Ya, pengguna Aspose.Tasks dapat memperoleh dukungan teknis melalui [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-15  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose