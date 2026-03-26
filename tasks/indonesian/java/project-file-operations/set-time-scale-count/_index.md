---
date: 2025-12-21
description: Pelajari cara menyesuaikan tampilan diagram Gantt, mengelola visualisasi
  proyek, dan menyimpan proyek sebagai PDF menggunakan Aspose.Tasks untuk Java. Sesuaikan
  jumlah skala waktu dengan mudah.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Sesuaikan Diagram Gantt – Menguasai Hitungan Skala Waktu MS Project di Aspose.Tasks
url: /id/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sesuaikan Diagram Gantt – Menguasai Hitungan Skala Waktu MS Project di Aspose.Tasks

## Introduction
Jika Anda perlu **menyesuaikan tampilan diagram Gantt** di Microsoft Project, mengontrol hitungan skala waktu merupakan teknik kunci. Dengan Aspose.Tasks untuk Java Anda dapat secara programatis mengatur tingkat skala waktu bawah dan tengah, menyempurnakan visibilitas tanda centang, dan kemudian **menyimpan proyek sebagai PDF** untuk dibagikan kepada pemangku kepentingan. Tutorial ini memandu Anda melalui seluruh proses—dari menyiapkan lingkungan hingga menghasilkan PDF yang dipoles yang mencerminkan tampilan Gantt yang telah disesuaikan.

## Quick Answers
- **Apa arti “menyesuaikan diagram Gantt”?** Menyesuaikan tingkat skala waktu, warna, dan tata letak agar sesuai dengan kebutuhan pelaporan Anda.  
- **Metode API mana yang mengatur hitungan tingkat bawah?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Bisakah saya menghasilkan PDF langsung dari proyek?** Ya—gunakan `project.save(..., SaveFileFormat.Pdf)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Lisensi komersial diperlukan; versi percobaan tersedia.  
- **Versi Java mana yang didukung?** Java 8 atau lebih tinggi bekerja dengan pustaka Aspose.Tasks terbaru.

## What is “customize Gantt chart” in Aspose.Tasks?
Menyesuaikan diagram Gantt berarti mengubah komponen visualnya secara programatis—seperti interval skala waktu, tanda centang, dan batang tugas—sehingga diagram tersebut selaras dengan cara Anda **mengelola visualisasi proyek**. Dengan mengubah hitungan skala waktu, Anda mengontrol berapa hari, minggu, atau bulan yang diwakili setiap segmen, membuat diagram lebih jelas untuk berbagai audiens.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Lingkungan Pengembangan Java** – JDK 8 atau yang lebih baru terpasang.  
2. **Pustaka Aspose.Tasks untuk Java** – Unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. **Pengetahuan Dasar Java** – Familiaritas dengan sintaks Java dan konsep berorientasi objek.

## Import Packages
Impor kelas yang diperlukan ke dalam proyek Java Anda:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step‑by‑Step Guide

### Step 1: Set Data Directory
Tentukan di mana file proyek Anda akan dibaca dan ditulis:

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan jalur absolut di mesin Anda.

### Step 2: Create a New Project Instance
Instansiasi objek `Project` baru yang akan menampung semua tugas dan pengaturan tampilan:

```java
Project project = new Project();
```

### Step 3: Configure the Gantt Chart View
Buat objek `GanttChartView`—ini tempat Anda akan **menghasilkan kode Java tampilan Gantt** untuk mengontrol penampilan diagram:

```java
GanttChartView view = new GanttChartView();
```

### Step 4: Set Time Scale Count for the Bottom Tier
Sesuaikan tingkat bawah agar menampilkan dua interval dan sembunyikan tanda centang:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Step 5: Set Time Scale Count for the Middle Tier
Terapkan konfigurasi yang sama pada tingkat tengah:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Step 6: Add the Customized View to the Project
Lampirkan tampilan yang baru saja Anda konfigurasikan ke instance `Project`:

```java
project.getViews().add(view);
```

### Step 7: Add Sample Tasks (Test Data)
Buat beberapa tugas dengan durasi tertentu untuk mengilustrasikan diagram Gantt yang telah disesuaikan:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Step 8: Save the Project as a PDF
Akhirnya, ekspor proyek—termasuk **diagram Gantt yang telah disesuaikan**—ke file PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

PDF yang dihasilkan memperlihatkan bagaimana tingkat skala waktu bawah dan tengah telah **disesuaikan**, memberikan pemangku kepentingan tampilan jadwal yang jelas dan dapat dicetak.

## Common Issues & Troubleshooting
- **PDF kosong** – Pastikan jalur `dataDir` diakhiri dengan pemisah file (`/` atau `\`) dan bahwa direktori tersebut ada.  
- **Tanda centang masih muncul** – Verifikasi bahwa `setShowTicks(false)` dipanggil pada kedua tingkat.  
- **Durasi tidak diterapkan** – Pastikan Anda menggunakan `TimeUnitType.Hour` (atau unit yang sesuai) saat membuat durasi.

## Frequently Asked Questions

**Q: Bisakah Aspose.Tasks untuk Java menangani file proyek berskala besar?**  
A: Ya, pustaka ini dioptimalkan untuk pemrosesan berperforma tinggi pada data proyek yang ekstensif.

**Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai IDE Java?**  
A: Tentu – ia bekerja mulus dengan Eclipse, IntelliJ IDEA, NetBeans, dan IDE populer lainnya.

**Q: Bisakah saya menyesuaikan tampilan diagram Gantt selain pengaturan skala waktu?**  
A: Ya, Aspose.Tasks menyediakan opsi styling yang luas seperti warna batang, font, dan garis kisi.

**Q: Apakah tersedia versi percobaan untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat memperoleh versi percobaan gratis dari [here](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat menemukan dukungan dan bantuan di forum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Bagaimana cara mengubah warna latar belakang diagram Gantt secara programatis?**  
A: Gunakan metode `view.getGanttChartProperties().setBackgroundColor(Color)` setelah mengimpor `java.awt.Color`.

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda telah belajar cara **menyesuaikan tingkat skala waktu diagram Gantt**, meningkatkan **visualisasi proyek**, dan **menyimpan proyek sebagai PDF** menggunakan Aspose.Tasks untuk Java. Pendekatan ini memberi Anda kontrol penuh atas output visual, memudahkan berbagi jadwal yang jelas dan profesional dengan tim atau klien Anda.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks untuk Java 24.12 (terbaru pada saat penulisan)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}