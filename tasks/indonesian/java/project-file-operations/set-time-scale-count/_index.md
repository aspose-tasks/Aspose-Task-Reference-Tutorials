---
date: 2026-03-29
description: Pelajari cara membuat file PDF proyek sambil menyesuaikan jumlah skala
  waktu diagram Gantt menggunakan Aspose.Tasks untuk Java. Panduan ini menunjukkan
  langkah demi langkah cara mengekspor Gantt ke PDF dengan kontrol penuh.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Buat PDF Proyek – Sesuaikan Skala Waktu Gantt
url: /id/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat PDF Proyek – Sesuaikan Skala Waktu Gantt Chart

## Pendahuluan
Jika Anda perlu **membuat PDF proyek** yang mencerminkan Gantt chart yang disetel dengan sempurna, mengontrol jumlah skala waktu adalah kuncinya. Dengan Aspose.Tasks for Java Anda dapat secara programatis mengatur tingkat skala waktu bawah dan tengah, menyembunyikan tanda centang, dan kemudian **menyimpan proyek sebagai PDF** untuk distribusi mudah. Dalam tutorial ini kami akan membahas semua yang Anda perlukan—dari menyiapkan lingkungan pengembangan hingga menghasilkan PDF yang halus yang menampilkan tampilan Gantt yang disesuaikan.

## Jawaban Cepat
- **Apa arti “customize Gantt chart”?** Menyesuaikan tingkat skala waktu, warna, dan tata letak agar sesuai dengan kebutuhan pelaporan Anda.  
- **Metode API mana yang mengatur jumlah tier bawah?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Bisakah saya menghasilkan PDF langsung dari proyek?** Ya—gunakan `project.save(..., SaveFileFormat.Pdf)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Diperlukan lisensi komersial; versi percobaan gratis tersedia.  
- **Versi Java mana yang didukung?** Java 8 atau lebih tinggi bekerja dengan perpustakaan Aspose.Tasks terbaru.

## Apa itu “customize Gantt chart” dalam Aspose.Tasks?
Menyesuaikan Gantt chart berarti mengubah komponen visualnya secara programatis—seperti interval skala waktu, tanda centang, dan batang tugas—sehingga chart sesuai dengan cara Anda ingin **mengelola visualisasi proyek**. Dengan mengubah jumlah skala waktu, Anda mengontrol berapa hari, minggu, atau bulan yang diwakili setiap segmen, membuat chart lebih jelas untuk berbagai audiens.

## Mengapa membuat PDF proyek dengan Gantt chart yang disesuaikan?
- **Output siap untuk pemangku kepentingan:** PDF dapat dilihat secara universal, memastikan semua orang melihat tata letak jadwal yang sama.  
- **Ramah cetak:** Kontrol yang tepat atas tingkat skala waktu mencegah cetakan yang penuh atau ambigu.  
- **Otomatisasi:** Integrasikan pembuatan PDF ke dalam pipeline CI atau layanan pelaporan untuk tanpa usaha manual.  

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Environment** – JDK 8 atau yang lebih baru terpasang.  
2. **Aspose.Tasks for Java Library** – Unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – Familiaritas dengan sintaks Java dan konsep berorientasi objek.

## Impor Paket
Import the necessary classes into your Java project:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Atur Direktori Data
Define where your project files will be read from and written to:

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan path absolut di mesin Anda.

### Langkah 2: Buat Instance Proyek Baru
Instantiate a fresh `Project` object that will hold all tasks and view settings:

```java
Project project = new Project();
```

### Langkah 3: Konfigurasikan Tampilan Gantt Chart
Create a `GanttChartView` object—this is where you’ll **menghasilkan kode Gantt view Java** to control the chart appearance:

```java
GanttChartView view = new GanttChartView();
```

### Langkah 4: Atur Jumlah Skala Waktu untuk Tier Bawah
Adjust the bottom tier to show two intervals and hide the tick marks:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Langkah 5: Atur Jumlah Skala Waktu untuk Tier Tengah
Apply the same configuration to the middle tier:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Langkah 6: Tambahkan Tampilan yang Disesuaikan ke Proyek
Attach the view you just configured to the `Project` instance:

```java
project.getViews().add(view);
```

### Langkah 7: Tambahkan Tugas Contoh (Data Uji)
Create a couple of tasks with specific durations to illustrate the customized Gantt chart:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Langkah 8: Simpan Proyek sebagai PDF
Finally, export the project—including your **customized Gantt chart**—to a PDF file:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

PDF yang dihasilkan menunjukkan bagaimana tier skala waktu bawah dan tengah telah **disesuaikan**, memberikan pemangku kepentingan tampilan jadwal yang jelas dan dapat dicetak.

## Masalah Umum & Pemecahan Masalah
- **PDF kosong** – Pastikan path `dataDir` diakhiri dengan pemisah file (`/` atau `\`) dan direktori tersebut ada.  
- **Tanda centang masih muncul** – Verifikasi bahwa `setShowTicks(false)` dipanggil pada kedua tier.  
- **Durasi tidak diterapkan** – Pastikan Anda menggunakan `TimeUnitType.Hour` (atau unit yang sesuai) saat membuat durasi.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah Aspose.Tasks for Java menangani file proyek berskala besar?**  
A: Ya, perpustakaan ini dioptimalkan untuk pemrosesan berperforma tinggi dari data proyek yang luas.

**Q: Apakah Aspose.Tasks for Java kompatibel dengan berbagai IDE Java?**  
A: Tentu – ia bekerja mulus dengan Eclipse, IntelliJ IDEA, NetBeans, dan IDE populer lainnya.

**Q: Bisakah saya menyesuaikan tampilan Gantt chart selain pengaturan skala waktu?**  
A: Ya, Aspose.Tasks menyediakan opsi styling yang luas seperti warna bar, font, dan garis kisi.

**Q: Apakah ada versi percobaan tersedia untuk Aspose.Tasks for Java?**  
A: Ya, Anda dapat memperoleh versi percobaan gratis dari [here](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks for Java?**  
A: Anda dapat menemukan dukungan dan bantuan di forum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Bagaimana cara mengubah warna latar belakang Gantt chart secara programatis?**  
A: Gunakan metode `view.getGanttChartProperties().setBackgroundColor(Color)` setelah mengimpor `java.awt.Color`.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda telah belajar cara **membuat PDF proyek** dengan skala waktu Gantt chart yang sepenuhnya disesuaikan, meningkatkan **visualisasi proyek**, dan **menyimpan proyek sebagai PDF** menggunakan Aspose.Tasks for Java. Pendekatan ini memberi Anda kontrol penuh atas output visual, memudahkan berbagi jadwal yang jelas dan profesional dengan tim atau klien Anda.

---

**Terakhir Diperbarui:** 2026-03-29  
**Diuji Dengan:** Aspose.Tasks for Java (latest)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}