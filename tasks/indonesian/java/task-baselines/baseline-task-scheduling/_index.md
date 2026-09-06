---
date: 2026-08-29
description: Pelajari cara membaca data baseline dan schedule tasks menggunakan Aspose.Tasks
  untuk Java, sehingga Anda dapat membandingkan kemajuan yang direncanakan dengan
  yang sebenarnya secara efisien.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Baseline Task Scheduling di Aspose.Tasks
og_description: Pelajari cara membaca data baseline dan schedule tasks menggunakan
  Aspose.Tasks untuk Java, memungkinkan perbandingan yang tepat antara kemajuan yang
  direncanakan dan yang sebenarnya.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Cara membaca baseline dan schedule tasks dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Cara membaca baseline dan schedule tasks dengan Aspose.Tasks
url: /id/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membaca baseline dan menjadwalkan tugas dengan Aspose.Tasks

Dalam panduan ini Anda akan menemukan **cara membaca informasi baseline** dan menjadwalkan tugas secara programatis menggunakan Aspose.Tasks untuk Java. Pada akhir tutorial, Anda akan dapat menangkap rencana proyek asli, membandingkannya dengan kemajuan aktual, dan menghasilkan laporan variasi—semua tanpa perlu menginstal Microsoft Project.

## Pengantar baseline manajemen proyek

Mengelola **baseline manajemen proyek** adalah fondasi dari manajemen proyek yang efektif. Ini memungkinkan Anda menangkap rencana asli dan kemudian membandingkan **rencana vs kemajuan aktual** sehingga Anda dapat mengidentifikasi variasi lebih awal. Dalam tutorial ini, kami akan menjelaskan cara menjadwalkan baseline tugas menggunakan Aspose.Tasks untuk Java, memberi Anda alat untuk **mengelola baseline proyek** dengan percaya diri dan menjaga proyek Anda tetap pada jalurnya.

## Jawaban Cepat
- **Apa yang diwakili oleh baseline manajemen proyek?**  
  Itu mencatat jadwal, biaya, dan ruang lingkup yang disetujui pada awal proyek, menyediakan referensi untuk analisis variasi.  
- **Perpustakaan mana yang menangani penjadwalan baseline di Java?**  
  Aspose.Tasks untuk Java menawarkan API pure‑Java yang mendukung lebih dari 45 format input dan output serta proyek hingga 100 000 tugas.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?**  
  Versi percobaan gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk penggunaan produksi.  
- **Apa saja prasyarat utama?**  
  Java Development Kit (JDK) 11+ dan perpustakaan Aspose.Tasks untuk Java.  
- **Bisakah saya melihat tanggal baseline setelah menetapkannya?**  
  Ya—gunakan objek `TaskBaseline` untuk membaca nilai start, finish, dan duration.

## Apa itu baseline manajemen proyek?

Baseline manajemen proyek mencatat jadwal, anggaran, dan ruang lingkup yang disetujui pada awal pelaksanaan. Ini berfungsi sebagai titik referensi untuk mengukur kinerja dan mengidentifikasi penyimpangan sepanjang siklus hidup proyek. Baseline mencakup tanggal mulai dan selesai yang direncanakan, total biaya, serta detail ruang lingkup, memberikan gambaran komprehensif untuk perbandingan di masa mendatang.

## Mengapa menggunakan Aspose.Tasks untuk penjadwalan baseline?

Aspose.Tasks menyediakan API pure‑Java yang berfungsi tanpa perlu menginstal Microsoft Project. Ia mendukung **lebih dari 45 format input dan output**, dapat memproses proyek dengan **hingga 100 000 tugas** dalam mode hemat memori, dan menawarkan metode bawaan untuk membaca serta menulis data baseline—mempermudah pelaporan otomatis dan integrasi.

## Prasyarat
- **Java Development Kit (JDK)** – instal JDK 11 atau yang lebih baru. Anda dapat mengunduhnya dari [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – unduh rilis terbaru dari [download page](https://releases.aspose.com/tasks/java/) dan tambahkan JAR ke classpath proyek Anda.

## Impor paket
Kelas `Project`, `Task`, dan `TaskBaseline` berada di namespace `com.aspose.tasks`. Impor mereka di bagian atas file sumber Anda:

Kelas `Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file proyek dalam memori. Ia menyediakan akses ke tugas, sumber daya, dan koleksi baseline.

## Cara membaca baseline?
Muat proyek, lalu kueri koleksi `TaskBaseline` untuk setiap tugas. Objek `TaskBaseline` mengembalikan nilai start, finish, dan duration baseline yang ditangkap ketika Anda memanggil `setBaseline`. Pendekatan langsung ini memungkinkan Anda membaca nilai baseline tanpa harus mem-parsing file XML atau biner.

## Langkah 1: buat instance proyek baru
Kelas `Project` mewakili seluruh file proyek dalam memori.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Langkah 2: definisikan tugas dan tetapkan baseline
`Task` mewakili item kerja individu, dan `setBaseline` menangkap jadwal saat ini sebagai baseline.
```java
Project project = new Project();
```

## Langkah 3: akses informasi baseline
`TaskBaseline` menyimpan nilai start, finish, dan duration yang disimpan untuk sebuah baseline.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Langkah 4: tampilkan durasi baseline
`Duration` mewakili panjang waktu untuk sebuah tugas atau baseline.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Langkah 5: tampilkan tanggal mulai baseline
`Start` adalah tanggal mulai yang dijadwalkan untuk baseline.
```java
System.out.println(baseline.getDuration().toString());
```

## Langkah 6: tampilkan tanggal selesai baseline
`Finish` adalah tanggal selesai yang dijadwalkan untuk baseline.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Masalah umum dan solusi
- **Baseline tidak ditetapkan:** Pastikan Anda memanggil `project.setBaseline(BaselineType.Baseline)` **setelah** menambahkan tugas; jika tidak, koleksi baseline akan kosong.  
- **Nilai null:** Jika `task.getBaselines()` mengembalikan daftar kosong, pastikan tugas telah ditambahkan ke hierarki proyek sebelum menetapkan baseline.  
- **Format tanggal:** Metode `getStart()` dan `getFinish()` mengembalikan objek `java.util.Date`. Gunakan `SimpleDateFormat` jika Anda memerlukan format tampilan khusus.

## Pertanyaan yang sering diajukan

**Q: Bagaimana cara membuat instance proyek baru di Aspose.Tasks?**  
A: Instansiasikan kelas `Project` (`Project project = new Project();`). Ini membuat file proyek baru yang siap untuk tugas dan baseline.

**Q: Apa perbedaan antara `BaselineType.Baseline` dan tipe baseline lainnya?**  
A: `BaselineType.Baseline` mengacu pada baseline utama (Baseline 1). Aspose.Tasks juga mendukung Baseline 2‑10 untuk snapshot tambahan.

**Q: Bisakah saya mengekspor data baseline ke Excel atau CSV?**  
A: Ya, Anda dapat mengiterasi objek `TaskBaseline` dan menulis nilai-nilai tersebut ke file CSV menggunakan I/O standar Java.

**Q: Apakah menetapkan baseline memengaruhi tanggal tugas yang ada?**  
A: Menetapkan baseline menangkap tanggal saat ini tetapi tidak mengubah jadwal aktif tugas. Anda masih dapat menyesuaikan tanggal start/finish setelah baseline ditetapkan.

**Q: Apakah memungkinkan membandingkan beberapa baseline secara programatis?**  
A: Tentu saja. Ambil setiap baseline melalui `task.getBaselines().get(index)` dan bandingkan properti `Start`, `Finish`, serta `Duration` mereka.

---

**Terakhir Diperbarui:** 2026-08-29  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Tutorial Terkait

- [Buat Daftar Tugas Java – Baseline MS Project menggunakan Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Cara Menetapkan Durasi Baseline di Aspose.Tasks untuk Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Buat Proyek MPP Java – Ubah Progres Tugas dengan Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}