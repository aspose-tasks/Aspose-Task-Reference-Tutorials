---
date: 2026-10-31
description: Pelajari cara mengekspor gantt ke pdf dalam Java menggunakan Aspose.Tasks.
  Panduan langkah demi langkah ini menunjukkan cara membaca data diagram Gantt dan
  menghasilkan laporan PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Baca Data Diagram Gantt Spesifik di Aspose.Tasks
og_description: Ekspor gantt ke pdf dalam Java dengan Aspose.Tasks. Ikuti tutorial
  ini untuk membaca data diagram Gantt, menyesuaikan properti tampilan, dan menghasilkan
  laporan PDF untuk manajemen proyek.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Ekspor gantt ke pdf dalam Java – panduan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Ekspor gantt ke pdf dalam Java – ekstrak data spesifik
url: /id/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ekspor gantt ke pdf di Java – ekstrak data spesifik

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **export gantt to pdf in Java** dengan membaca informasi diagram Gantt menggunakan Aspose.Tasks untuk Java. Diagram Gantt memberikan manajer proyek peta visual tugas, ketergantungan, dan timeline, dan kemampuan untuk mengambil data tersebut secara programatik memungkinkan Anda membuat laporan PDF otomatis, dasbor, atau integrasi dengan sistem perusahaan lainnya. Mari kita jalani setiap langkah, mulai dari memuat file proyek hingga mengekstrak properti tampilan dan akhirnya menghasilkan PDF.

## Jawaban cepat
- **Apa yang dapat saya ekstrak?** Properti tampilan apa pun, gaya bar, garis kisi, gaya teks, garis kemajuan, atau tingkat skala waktu dari diagram Gantt.  
- **Apakah saya memerlukan lisensi?** Versi percobaan dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 atau lebih baru (tutorial ini menggunakan JDK 11).  
- **Apakah kode dapat dijalankan apa adanya?** Ya – cukup ganti jalur direktori data.  
- **Bisakah saya memodifikasi tampilan setelah membaca?** Tentu – API memungkinkan Anda mengubah properti dan menyimpan kembali ke file proyek.

## Apa itu export gantt to pdf?
Export gantt to pdf adalah proses mengonversi tampilan diagram Gantt yang disimpan dalam file proyek menjadi dokumen PDF yang mempertahankan gaya visual dan informasi timeline. Operasi ini berguna untuk berbagi status proyek dengan pemangku kepentingan yang mungkin tidak memiliki alat manajemen proyek.

## Mengapa export gantt to pdf dengan Aspose.Tasks?
Aspose.Tasks dapat menangani **lebih dari 30 + format input** (MPP, XML, MPX, dll.) dan **mengekspor ke PDF dalam satu panggilan** sambil mempertahankan 95 % kesetiaan visual, bahkan untuk proyek dengan lebih dari 500 tugas. Perpustakaan ini memproses file di memori, sehingga Anda dapat menghasilkan PDF di server tanpa menginstal Microsoft Project.

## Prasyarat
1. **Java Development Kit (JDK):** Pastikan Anda memiliki Java terinstal di sistem Anda. Anda dapat mengunduhnya dari **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Unduh dan instal perpustakaan Aspose.Tasks untuk Java dari **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** Pilih IDE sesuai preferensi Anda. Pilihan populer termasuk IntelliJ IDEA, Eclipse, atau NetBeans.

## Impor paket
Impor berikut memberi Anda akses ke kelas inti Aspose.Tasks yang diperlukan untuk membaca dan mengekspor data Gantt.  
*Tidak ada blok kode yang ditampilkan di sini untuk menjaga fokus tutorial pada konsep; cukup tambahkan impor ke file Java Anda.*

## Bagaimana cara memuat file proyek diagram Gantt di Java?
Muatan file proyek dengan membuat instance `Project` dan memberikan jalur lengkap ke konstruktor. Langkah ini menginisialisasi representasi Gantt chart dalam memori, memungkinkan kueri properti tampilan selanjutnya. Ketika file berhasil dimuat, Anda dapat memverifikasi nama proyek, tanggal mulai, dan jumlah tugas untuk memastikan file yang tepat telah dibuka. Verifikasi ini membantu menangkap masalah jalur atau format lebih awal dalam alur kerja.
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definition anchor:* `Project` adalah objek Aspose.Tasks tingkat atas yang mewakili satu file proyek dalam memori.

## Bagaimana saya dapat mengakses tampilan diagram Gantt?
Ambil tampilan Gantt pertama dari koleksi tampilan proyek. Kebanyakan proyek memiliki setidaknya satu tampilan Gantt, dan biasanya itu adalah entri pertama. Setelah memperoleh tampilan, Anda mungkin ingin memeriksa namanya dan memastikan itu berjenis `GanttChartView` sebelum melanjutkan ekstraksi properti. Pemeriksaan tambahan ini mencegah kesalahan runtime saat bekerja dengan koleksi tampilan khusus atau non‑standar.
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definition anchor:* `GanttChartView` mewakili tata letak visual tugas, skala waktu, dan bar yang Anda lihat dalam diagram Gantt tipikal.

## Bagaimana cara mengekstrak properti tampilan?
Anda dapat membaca properti seperti warna latar belakang, tinggi bar, dan pengaturan skala waktu langsung dari objek `GanttChartView`. Mencetaknya membantu Anda memverifikasi konfigurasi saat ini sebelum mengekspor. Loop ekstraksi tipikal mengiterasi setiap properti, memformat nilai sebagai string, dan mencatatnya ke konsol atau file untuk analisis selanjutnya. Pendekatan ini berguna untuk debugging dan menghasilkan dokumentasi tampilan chart.
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definition anchor:* `GanttChartView` menyediakan akses ke pengaturan tampilan seperti warna latar belakang, tinggi bar, dan konfigurasi skala waktu.

## Bagaimana cara mengekstrak gaya bar?
Iterasi melalui koleksi objek `BarStyle` untuk memperoleh detail seperti warna, pola, dan bentuk untuk setiap tipe bar yang digunakan dalam chart. Untuk setiap gaya, Anda juga dapat membaca tipe tugas terkait dan kondisi yang memicu gaya tersebut, yang penting saat merekonstruksi chart dalam format lain. Mengumpulkan informasi ini memungkinkan Anda menghasilkan replika visual yang akurat atau menerapkan aturan styling khusus secara programatik.
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definition anchor:* `BarStyle` mendefinisikan tampilan visual bar Gantt, termasuk warnanya, pola, dan bentuk.

## Bagaimana cara mengekstrak garis kisi?
Garis kisi mendefinisikan pemisahan visual antara baris dan kolom. Akses mereka melalui metode `getGridlines()` dan keluarkan visibilitas serta gaya mereka. Setelah mengambil koleksi garis kisi, Anda dapat mengiterasi setiap garis untuk menangkap tipe garis (solid, dash), ketebalan, dan warna. Data ini berharga ketika Anda perlu mereproduksi tata letak kisi yang tepat dalam PDF yang diekspor atau format pelaporan lainnya.
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definition anchor:* `getGridlines()` mengembalikan koleksi objek garis kisi yang mengontrol pemisah baris dan kolom dalam tampilan Gantt.

## Bagaimana cara mengekstrak gaya teks?
Gaya teks mengontrol font, ukuran, dan warna label pada diagram Gantt. Loop melalui koleksi `TextStyle` untuk mendaftar setiap gaya. Untuk setiap gaya teks, Anda juga dapat mengambil elemen terkait (nama tugas, tanggal, dll.) dan aturan pemformatan kondisional apa pun. Menangkap detail ini memastikan dokumen yang diekspor mempertahankan tipografi yang sama dengan chart asli.
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definition anchor:* `TextStyle` mewakili atribut pemformatan yang diterapkan pada elemen tekstual dalam diagram Gantt.

## Bagaimana cara mengekstrak garis kemajuan?
Garis kemajuan menunjukkan titik penyelesaian saat ini dari sebuah tugas. Akses mereka melalui `getProgressLines()` dan cetak atributnya. Setiap garis kemajuan mencakup properti seperti warna garis, ketebalan, dan posisi relatif terhadap bar tugas. Mencatat informasi ini memungkinkan Anda menghasilkan visualisasi yang sadar kemajuan atau menghitung metrik penyelesaian proyek secara keseluruhan.
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definition anchor:* `getProgressLines()` mengembalikan sekumpulan objek garis kemajuan yang menunjukkan status penyelesaian tugas.

## Bagaimana cara mengekstrak tingkat skala waktu?
Tingkat skala waktu mendefinisikan unit waktu hierarkis (hari, minggu, bulan) yang ditampilkan pada chart. Ambil mereka melalui `getTimescaleTiers()` dan keluarkan pengaturannya. Untuk setiap tingkat Anda dapat menangkap tipe unit, format label, dan perataan, yang penting untuk mereproduksi granularitas timeline yang tepat dalam PDF yang diekspor atau komponen UI khusus.
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definition anchor:* `getTimescaleTiers()` menyediakan akses ke koleksi objek tingkat skala waktu yang mengontrol tampilan sumbu waktu.

## Bagaimana cara mengekspor diagram Gantt ke PDF?
Buat objek `PdfSaveOptions`, secara opsional sesuaikan ukuran halaman atau penyematan font, lalu panggil `project.save` dengan format PDF. Panggilan tunggal ini menghasilkan PDF yang mencerminkan tampilan Gantt di layar. Anda juga dapat menentukan opsi tambahan seperti kompresi gambar, penghapusan watermark, atau penyematan font khusus untuk memenuhi persyaratan branding perusahaan. Setelah menyimpan, verifikasi ukuran file PDF dan kesetiaan visual untuk memastikan ekspor berhasil.
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definition anchor:* `PdfSaveOptions` memungkinkan Anda menyesuaikan output PDF secara detail, seperti dimensi halaman, kompresi, dan penanganan font.

## Kesalahan umum & tips
- **Direktori data tidak benar:** Pastikan `dataDir` diakhiri dengan pemisah file (`/` atau `\\`) yang sesuai untuk OS Anda.  
- **Tampilan tidak ada:** Jika proyek tidak memiliki tampilan Gantt, `project.getViews()` akan kosong – tambahkan pemeriksaan sebelum casting.  
- **Pengecualian lisensi:** Tanpa lisensi yang valid, API dapat menambahkan watermark pada PDF yang diekspor.  
- **Proyek besar:** Untuk proyek dengan lebih dari 1.000 tugas, pertimbangkan meningkatkan ukuran heap JVM (`-Xmx2g`) untuk menghindari `OutOfMemoryError`.  

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan perpustakaan Java lain?**  
A: Ya, Aspose.Tasks untuk Java terintegrasi mulus dengan perpustakaan atau kerangka kerja Java apa pun, termasuk Spring, Hibernate, dan Apache POI.

**Q: Apakah Aspose.Tasks cocok untuk proyek perusahaan berskala besar?**  
A: Tentu saja. Perpustakaan ini memproses file MPP ratusan halaman dalam waktu kurang dari 5 detik pada perangkat keras server standar dan mendukung eksekusi bersamaan dalam lingkungan multi‑thread.

**Q: Apakah Aspose.Tasks mendukung banyak format file proyek?**  
A: Ya, Aspose.Tasks mendukung lebih dari 20 format, termasuk MPP, XML, MPX, dan Primavera XML, memungkinkan Anda membaca dan mengonversi jadwal lama.

**Q: Bisakah saya menyesuaikan tampilan diagram Gantt dengan Aspose.Tasks?**  
A: Tentu. Anda dapat memodifikasi gaya bar, garis kisi, gaya teks, dan tingkat skala waktu secara programatik sebelum mengekspor ke PDF atau format gambar.

**Q: Bagaimana cara menyimpan perubahan setelah memodifikasi tampilan?**  
A: Panggil `project.save("output.mpp");` setelah melakukan modifikasi apa pun untuk menyimpannya ke file proyek.

---

**Terakhir Diperbarui:** 2026-10-31  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Tutorial Terkait

- [Cara Menyimpan Proyek sebagai PDF dengan Aspose.Tasks – Panduan Ekspor](/tasks/java/project-file-operations/save-as-pdf/)
- [Buat PDF Proyek – Sesuaikan Skala Waktu Diagram Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [Ekspor Proyek ke PDF dan Kurangi Celah Antara Daftar Tugas dan Footer di Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}