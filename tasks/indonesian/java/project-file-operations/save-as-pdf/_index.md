---
date: 2025-12-20
description: Pelajari cara mengekspor PDF di Aspose.Tasks untuk Java, panduan sederhana
  untuk mengonversi MPP ke PDF dan menyimpan file proyek Anda secara efisien.
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengekspor PDF di Aspose.Tasks – Simpan Sebagai PDF
url: /id/java/project-file-operations/save-as-pdf/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekspor PDF di Aspose.Tasks – Simpan Sebagai PDF

## Pendahuluan
Dalam tutorial ini, kami akan menunjukkan **cara mengekspor PDF** di Aspose.Tasks untuk Java, membimbing Anda melalui proses menyimpan sebuah proyek sebagai PDF. Dengan Aspose.Tasks, Anda dapat dengan efisien **mengonversi MPP ke PDF**, memastikan kompatibilitas dan kemudahan berbagi antar tim dan pemangku kepentingan. Mari kita selami langkah‑langkahnya sehingga Anda dapat dengan cepat mendapatkan PDF yang dapat dicetak dari file proyek apa pun.

## Jawaban Cepat
- **Apa arti “export PDF” dalam Aspose.Tasks?** Itu berarti mengonversi file proyek (misalnya MPP) menjadi dokumen PDF yang mempertahankan tata letak visual.  
- **Versi perpustakaan mana yang diperlukan?** Versi Aspose.Tasks untuk Java apa pun yang mendukung `PdfSaveOptions` (disarankan menggunakan rilis terbaru).  
- **Apakah saya memerlukan lisensi untuk konversi ini?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyesuaikan tampilan PDF?** Ya – Anda dapat mengatur timescale, legenda, dan `PdfSaveOptions` lainnya.  
- **Apakah konversi cepat untuk proyek besar?** Biasanya dalam hitungan detik; kinerja tergantung pada ukuran proyek dan opsi yang dipilih.

## Apa itu “cara mengekspor pdf” dalam konteks Aspose.Tasks?
Mengekspor PDF dengan Aspose.Tasks berarti mengambil file proyek (seperti `.mpp`, `.xml`, atau `.xlsx`) dan menghasilkan PDF yang mencerminkan diagram Gantt, tampilan penggunaan tugas, atau format presentasi lain yang Anda konfigurasikan. Ini berguna untuk pelaporan, dokumentasi, atau berbagi tampilan hanya‑baca dengan pemangku kepentingan non‑teknis.

## Mengapa Mengekspor File Proyek ke PDF?
- **Keterbacaan universal:** PDF dapat dibuka di perangkat apa pun tanpa memerlukan perangkat lunak proyek asli.  
- **Presentasi profesional:** Mempertahankan format, warna, dan tata letak untuk laporan yang ditujukan kepada klien.  
- **Distribusi mudah:** Berbagi melalui email, intranet, atau penyimpanan cloud tanpa kekhawatiran kontrol versi.  
- **Kepatuhan & pengarsipan:** PDF ideal untuk penyimpanan jangka panjang dan kepatuhan regulasi.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Java Development Kit (JDK):** JDK 8 atau yang lebih baru terpasang di mesin Anda.  
2. **Perpustakaan Aspose.Tasks untuk Java:** Unduh perpustakaan dari situs resmi [here](https://releases.aspose.com/tasks/java/).  
3. **File Proyek:** Miliki file proyek yang sudah ada (misalnya `HomeMovePlan.mpp`) yang siap untuk dikonversi.

## Impor Paket
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Baca File Proyek Input
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Ganti `"Your Data Directory"` dengan path absolut tempat file `.mpp` Anda berada. Ini memuat proyek ke memori sehingga Anda dapat memanipulasi atau mengekspornya.

### Langkah 2: Simpan Proyek sebagai PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Baris di atas melakukan operasi **menyimpan proyek sebagai PDF** yang sederhana, membuat `Project5.pdf` di folder yang sama.

### Langkah 3: Sesuaikan Konten ke Ukuran Sel (Opsi Simpan PDF Lanjutan)
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

### Langkah 4: Sembunyikan Legenda (Output Lebih Bersih)
```java
o.setLegendOnEachPage(false);
```
Menonaktifkan legenda dapat membuat PDF lebih ringkas, terutama untuk proyek besar.

### Langkah 5: Simpan Proyek dengan Opsi yang Diterapkan
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Langkah akhir ini menulis PDF menggunakan opsi khusus yang didefinisikan di atas, menghasilkan dokumen bersih dengan skala bulan tanpa legenda per‑halaman.

## Masalah Umum & Tips
- **File tidak ditemukan:** Pastikan `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) dan mengarah ke direktori yang benar.  
- **Halaman kosong:** Verifikasi bahwa `PresentationFormat` yang dipilih cocok dengan tampilan yang Anda harapkan (misalnya Gantt, Task Usage).  
- **File besar memerlukan waktu lebih lama:** Pertimbangkan mengatur `o.setFitContent(false)` untuk proyek yang sangat besar guna mengurangi waktu pemrosesan.  

## Pertanyaan yang Sering Diajukan

**T: Apakah Aspose.Tasks kompatibel dengan semua versi Java?**  
J: Ya, Aspose.Tasks mendukung versi Java mulai dari JDK 6 ke atas.

**T: Bisakah saya menyesuaikan tampilan output PDF?**  
J: Tentu saja! Aspose.Tasks menyediakan banyak **pdf save options**—seperti skala waktu, visibilitas legenda, dan format presentasi—untuk menyesuaikan PDF sesuai kebutuhan Anda.

**T: Apakah Aspose.Tasks mendukung format file lain untuk konversi?**  
J: Ya, Anda dapat mengonversi antara MPP, XML, XLSX, dan banyak format lainnya, menjadikannya alat serbaguna untuk **convert mpp to pdf** dan transformasi lainnya.

**T: Apakah ada versi percobaan yang tersedia untuk Aspose.Tasks?**  
J: Ya, Anda dapat memperoleh versi percobaan gratis Aspose.Tasks dari [here](https://releases.aspose.com/).

**T: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks?**  
J: Untuk dukungan dan bantuan, kunjungi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) resmi.

## Kesimpulan
Dengan mengikuti panduan ini, Anda kini mengetahui **cara mengekspor PDF** dari proyek Java mana pun menggunakan Aspose.Tasks, mulai dari penyimpanan satu baris sederhana hingga penyesuaian lanjutan dengan `PdfSaveOptions`. Gunakan teknik ini untuk menghasilkan PDF yang rapi dan dapat dibagikan untuk pelaporan, presentasi kepada klien, atau keperluan pengarsipan.

---

**Terakhir Diperbarui:** 2025-12-20  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}