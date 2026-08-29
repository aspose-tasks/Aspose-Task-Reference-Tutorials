---
date: 2026-08-29
description: Pelajari cara mengatur baseline duration dan melacak project progress
  menggunakan Aspose.Tasks for Java. Panduan langkah demi langkah ini membantu Anda
  mengelola task baselines secara efisien.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Cara Mengatur Baseline Duration di Aspose.Tasks for Java
og_description: Pelajari cara mengatur baseline duration dan melacak project progress
  menggunakan Aspose.Tasks for Java. Ikuti panduan terperinci ini untuk mengelola
  task baselines secara efisien.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Cara mengatur baseline duration untuk melacak project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Cara mengatur baseline duration untuk melacak project progress
url: /id/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur durasi baseline untuk melacak kemajuan proyek

## Pendahuluan
Tracking project progress starts with a solid baseline. In this tutorial you’ll discover **how to set baseline duration** for tasks in Microsoft Project files using the Aspose.Tasks library for Java, and understand why establishing a baseline early helps you monitor schedule drift, cost variance, and resource overallocation throughout the life of the project.

## Jawaban Cepat
- **Apa arti “set baseline”?** Itu mencatat tanggal mulai, selesai, dan durasi asli suatu tugas sehingga Anda dapat membandingkan perubahan di masa mendatang.  
- **Kelas Aspose.Tasks mana yang membuat proyek?** Kelas `Project` – Anda juga akan belajar cara **membuat instance proyek** dengan benar.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Lisensi evaluasi gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengambil baseline interim?** Ya, Aspose.Tasks memungkinkan Anda menanyakan baseline interim dan biaya tetapnya.  
- **Versi Java apa yang diperlukan?** Java 8 atau yang lebih baru disarankan.  
- **Bagaimana ini membantu saya melacak kemajuan proyek?** Setelah baseline diatur, Anda dapat langsung membandingkan tanggal aktual dengan rencana asli menggunakan fitur pelaporan bawaan.

## Apa itu baseline tugas dan mengapa mengaturnya?
Baseline tugas menangkap jadwal yang direncanakan (tanggal mulai, tanggal selesai, dan durasi) pada titik waktu tertentu. Dengan mengatur baseline Anda membuat titik referensi yang memudahkan untuk mengidentifikasi penyimpangan jadwal, pembengkakan biaya, dan alokasi sumber daya berlebih seiring proyek berkembang.

## Mengapa menggunakan Aspose.Tasks untuk manajemen baseline?
Aspose.Tasks menyediakan **kompatibilitas .mpp penuh** – Anda dapat membaca dan menulis file Microsoft Project asli tanpa perlu menginstal Microsoft Office. API memberikan akses programatik ke **lebih dari 50 format input dan output**, mendukung **baseline interim 1‑10**, dan dapat menangani **proyek dengan ratusan halaman** tanpa memuat seluruh file ke memori, yang penting untuk pemrosesan batch berperforma tinggi.

## Prasyarat
1. **Lingkungan Pengembangan Java** – JDK 8+ terinstal dan terkonfigurasi.  
2. **Aspose.Tasks untuk Java** – unduh pustaka dari [halaman unduhan Aspose.Tasks untuk Java](https://releases.aspose.com/tasks/java/).  
3. **IDE atau alat build** – Maven, Gradle, atau IDE apa pun yang Anda sukai.

## Impor paket
Impor berikut membawa kelas inti Aspose.Tasks yang diperlukan untuk bekerja dengan proyek, tugas, baseline, dan data berfase waktu.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Langkah 1: buat instance proyek
Kelas `Project` mewakili file Microsoft Project dalam memori dan merupakan titik masuk untuk semua operasi.

```java
Project project = new Project();
```

## Langkah 2: buat baseline tugas
`TaskBaseline` menyimpan tanggal mulai, selesai, dan durasi yang direncanakan untuk tugas tertentu.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Langkah 3: tampilkan informasi baseline tugas
Metode `getBaselines()` mengembalikan koleksi baseline yang terkait dengan sebuah tugas.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Langkah 4: periksa baseline interim dan biaya tetap
`BaselineType` mengenumerasi baseline utama dan interim (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Langkah 5: cetak data berfase waktu
`TimephasedData` mewakili potongan informasi jadwal untuk interval waktu tertentu.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Dengan mengikuti langkah-langkah ini, Anda dapat **mengatur durasi baseline** untuk tugas apa pun dan mengambil informasi baseline terperinci menggunakan Aspose.Tasks untuk Java, memberi Anda cara yang dapat diandalkan untuk **melacak kemajuan proyek** sepanjang siklus hidup proyek.

## Masalah umum dan solusi
- **Baseline tidak muncul di MS Project:** Pastikan Anda memanggil `project.setBaseline(BaselineType.Baseline)` **setelah** menambahkan tugas.  
- **NullPointerException pada `getBaselines()`:** Verifikasi bahwa tugas telah ditambahkan ke proyek sebelum mengatur baseline.  
- **Ketidaksesuaian satuan waktu:** Gunakan `TimeUnitType` untuk memformat durasi dengan benar, terutama saat bekerja dengan kalender khusus.

## FAQ
### Apa itu baseline tugas di MS Project?
Baseline tugas di MS Project adalah cuplikan jadwal awal yang direncanakan untuk sebuah tugas, termasuk tanggal mulai, tanggal selesai, dan durasinya.

### Mengapa mengelola baseline tugas penting?
Mengelola baseline tugas membantu membandingkan jadwal yang direncanakan dengan kemajuan aktual proyek, memfasilitasi pelacakan dan pengambilan keputusan yang lebih baik.

### Bisakah saya memodifikasi baseline tugas setelah diatur?
Ya, Anda dapat memodifikasi baseline tugas di MS Project untuk mencerminkan perubahan dalam rencana proyek. Namun, penting untuk mendokumentasikan setiap penyimpangan dari baseline asli.

### Apakah Aspose.Tasks mendukung fungsionalitas manajemen proyek lainnya?
Ya, Aspose.Tasks menawarkan berbagai fitur untuk manajemen proyek, termasuk penjadwalan tugas, alokasi sumber daya, dan pembuatan diagram Gantt.

### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?
Anda dapat menemukan dukungan untuk Aspose.Tasks di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), tempat Anda dapat mengajukan pertanyaan dan berinteraksi dengan pengguna lain.

## Pertanyaan tambahan yang sering diajukan
**Q: Apakah saya perlu memanggil `setBaseline` untuk setiap tugas secara terpisah?**  
A: Tidak. Memanggil `project.setBaseline(BaselineType.Baseline)` merekam baseline untuk semua tugas dalam proyek sekaligus.

**Q: Bagaimana saya dapat mengatur baseline interim untuk tugas tertentu?**  
A: Gunakan `project.setBaseline(BaselineType.Baseline1)` (atau Baseline2‑Baseline10) setelah memperbarui jadwal tugas.

**Q: Apakah memungkinkan mengekspor data baseline ke CSV?**  
A: Ya. Iterasi melalui `task.getBaselines()` dan tulis bidang yang diinginkan ke file CSV menggunakan I/O Java standar.

**Q: Bisakah saya membaca file .mpp yang sudah ada dan sudah berisi baseline?**  
A: Tentu saja. Muat file dengan `new Project("myproject.mpp")` dan kemudian akses baseline masing‑masing tugas seperti yang ditunjukkan di atas.

**Q: Apakah Aspose.Tasks menangani file multi‑proyek?**  
A: Aspose.Tasks bekerja dengan file .mpp satu‑proyek. Untuk skenario multi‑proyek, gabungkan proyek secara programatik.

---

**Terakhir Diperbarui:** 2026-08-29  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Daftar Tugas Java – Baseline MS Project menggunakan Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Buat Proyek MPP Java – Ubah Progres Tugas dengan Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Baseline Manajemen Proyek – Penjadwalan Tugas dengan Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}