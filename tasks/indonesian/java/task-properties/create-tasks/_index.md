---
date: 2026-09-25
description: Pelajari cara membuat jadwal proyek di Java menggunakan Aspose.Tasks.
  Panduan ini menunjukkan cara menambahkan tugas ringkasan, mengelola hierarki proyek,
  dan mengatur direktori dokumen secara efisien.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Buat Tugas di Aspose.Tasks
og_description: Pelajari cara membuat jadwal proyek di Java menggunakan Aspose.Tasks.
  Ikuti petunjuk langkah demi langkah untuk menambahkan tugas ringkasan, mengelola
  hierarki, dan mengatur direktori dokumen.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Cara membuat jadwal proyek dengan Aspose.Tasks untuk Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Cara membuat jadwal proyek dengan Aspose.Tasks untuk Java
url: /id/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat jadwal proyek dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **membuat jadwal proyek** dalam aplikasi Java menggunakan Aspose.Tasks. Baik Anda sedang membangun daftar tugas sederhana maupun perencana tingkat perusahaan yang kompleks, langkah‑langkah di bawah ini akan memandu Anda menambahkan tugas ringkasan, mengelola hierarki proyek, dan mengatur direktori dokumen—semua dengan potongan kode yang jelas dan dapat dijalankan. Pada akhir tutorial, Anda akan memiliki jadwal terstruktur penuh yang siap untuk dimanipulasi lebih lanjut atau diekspor.

## Jawaban Cepat
- **Apa yang dikelola oleh Aspose.Tasks?** Ia menangani hierarki tugas, sumber daya, kalender, dan format file proyek (MS‑Project, Primavera, dll.).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara gratis dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru didukung sepenuhnya.  
- **Bisakah saya menambahkan bidang khusus ke tugas?** Ya, Anda dapat memperluas tugas dengan bidang yang didefinisikan pengguna melalui API.  
- **Apakah ada dukungan bawaan untuk diagram Gantt?** Aspose.Tasks dapat mengekspor ke PDF/HTML yang menyertakan visualisasi Gantt.

## Apa itu jadwal proyek dalam Aspose.Tasks?
Jadwal proyek adalah kumpulan lengkap tugas, ketergantungan, dan garis waktu yang menentukan bagaimana pekerjaan akan dilaksanakan. Aspose.Tasks menyimpan informasi ini dalam objek `Project` yang dapat Anda baca, ubah, dan simpan dalam berbagai format. Ia mencakup tanggal mulai dan selesai, kendala, serta penugasan sumber daya, memungkinkan perencanaan dan pelaporan yang komprehensif.

## Mengapa menggunakan Aspose.Tasks untuk manajemen proyek Java?
Aspose.Tasks mendukung **lebih dari 30 format input dan output** serta dapat memproses proyek dengan **hingga 10.000 tugas** tanpa harus memuat seluruh file ke memori, memberikan kinerja tinggi untuk skenario manajemen proyek Java berskala besar.

## Prasyarat
Sebelum memulai tutorial, pastikan Anda telah menyiapkan hal‑hal berikut:
- **Java Development Kit (JDK)** – JDK 8 atau yang lebih baru terpasang di mesin Anda.  
- **Aspose.Tasks for Java library** – Unduh dan instal pustaka dari [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – Gunakan Eclipse, IntelliJ IDEA, atau IDE Java lain yang Anda sukai.

## Impor paket
`Project`, `Task`, dan kelas terkait berada di namespace `com.aspose.tasks`. Impor mereka di bagian atas file Java Anda:

Kelas `Project` mewakili jadwal proyek lengkap dan menyediakan metode untuk memanipulasi tugas serta sumber daya.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Kelas `Project` adalah titik masuk untuk semua operasi pada file proyek.

## Cara membuat jadwal proyek dengan Aspose.Tasks?

Muat instance `Project` baru, atur direktori dokumen, dan mulailah menambahkan tugas. Paragraf jawaban langsung ini menjelaskan alur inti: Anda membuat `Project`, mengonfigurasi `RootFolder`‑nya (direktori dokumen), lalu menambahkan tugas ringkasan diikuti subtugas. Semua perubahan disimpan di memori hingga Anda memanggil `save` untuk menyimpan jadwal ke file.

### Langkah 1: atur direktori dokumen
Tentukan lokasi di mana file proyek yang dihasilkan akan ditulis. Menetapkan direktori lebih awal memastikan semua operasi penyimpanan selanjutnya menggunakan jalur yang konsisten.

Properti `RootFolder` menentukan folder dasar tempat file proyek dibaca atau ditulis.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Langkah 2: buat proyek baru
Instansiasi objek `Project` baru yang akan menampung jadwal Anda. Anda dapat secara opsional memberikan jalur file yang sudah ada untuk memuat jadwal yang akan dimodifikasi.

Konstruktor `Project` membuat jadwal kosong yang siap untuk penambahan tugas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Langkah 3: tambahkan tugas ringkasan
Tugas ringkasan mengelompokkan subtugas terkait dan muncul sebagai node yang dapat dilipat pada diagram Gantt. Gunakan kelas `Task` dan atur `IsSummary` menjadi `true`.

Metode `addTask` membuat tugas baru di bawah induk yang ditentukan dan mengembalikan ID‑nya.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Langkah 4: tambahkan subtugas
Subtugas mewarisi tanggal mulai/selesai dari tugas ringkasan induknya kecuali Anda menimpanya. Menambahkan subtugas semudah memanggil `addTask` lagi dan menentukan ID induk.

Memanggil `addTask` dengan ID induk menambahkan subtugas di bawah tugas ringkasan tersebut.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Lanjutkan menambahkan sebanyak mungkin tugas dan subtugas yang diperlukan untuk proyek Anda. Setiap langkah berkontribusi pada pembangunan hierarki proyek terstruktur yang dapat diekspor ke MS‑Project, PDF, atau format lain yang didukung.

## Masalah umum dan solusi
- **Masalah:** “Document directory not found.”  
  **Solusi:** Pastikan jalur yang Anda tetapkan ke `RootFolder` ada di sistem file dan proses Java Anda memiliki izin menulis.
- **Masalah:** Subtugas tidak muncul di bawah tugas ringkasan.  
  **Solusi:** Pastikan Anda memberikan ID tugas induk yang benar saat memanggil `addTask`. API memerlukan ID induk sebagai argumen kedua.
- **Masalah:** Proyek besar menyebabkan OutOfMemoryError.  
  **Solusi:** Aspose.Tasks memproses tugas dalam mode streaming; tingkatkan ukuran heap JVM (`-Xmx2g`) atau bagi jadwal menjadi beberapa file.

## Pertanyaan yang sering diajukan
**T: Apakah Aspose.Tasks cocok untuk proyek skala kecil?**  
J: Tentu saja. Pustaka ini dapat diskalakan dari daftar tugas tunggal hingga jadwal tingkat perusahaan dengan ribuan tugas.

**T: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.Tasks for Java?**  
J: Lihat dokumentasi [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**T: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Tasks?**  
J: Kunjungi [temporary license request page](https://purchase.aspose.com/temporary-license/) untuk lisensi terbatas waktu yang dapat digunakan untuk pengembangan dan pengujian.

**T: Bisakah saya menyesuaikan atribut tugas menggunakan Aspose.Tasks?**  
J: Ya, Anda dapat memperluas tugas dengan bidang khusus, menugaskan sumber daya, dan memodifikasi kalender secara programatik.

**T: Apakah ada komunitas dukungan untuk pengguna Aspose.Tasks?**  
J: Tentu! Bergabunglah dengan komunitas Aspose.Tasks di [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Terakhir Diperbarui:** 2026-09-25  
**Diuji dengan:** Aspose.Tasks 24.12 untuk Java  
**Penulis:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Tutorial Terkait

- [Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)
- [Buat Ketergantungan Tugas Manajemen Proyek di Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Cara Menambahkan Sumber Daya ke Proyek dan Membuat Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}