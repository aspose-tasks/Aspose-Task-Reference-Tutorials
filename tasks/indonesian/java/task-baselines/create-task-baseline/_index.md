---
date: 2026-08-29
description: Pelajari cara menambahkan task ke project dalam Java, membuat task list,
  dan menetapkan baseline tanpa Microsoft Project menggunakan Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Membuat Task Baseline di Aspose.Tasks
og_description: Pelajari cara menambahkan task ke project dalam Java dan menetapkan
  baseline menggunakan Aspose.Tasks. Panduan ini menampilkan kode langkah‑demi‑langkah
  tanpa memerlukan Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Cara menambahkan task ke project dalam Java dan menetapkan baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Cara menambahkan task ke project dalam Java dan menetapkan baseline
url: /id/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menambahkan tugas ke proyek di Java dan menetapkan baseline

## Pendahuluan
Dalam tutorial ini Anda akan **menambahkan tugas ke proyek** secara programatis, menghasilkan baseline tugas Microsoft Project, dan menyimpan file—semua tanpa pernah membuka Microsoft Project. Aspose.Tasks for Java memberi Anda API pure‑Java yang bekerja di platform apa pun, menjadikannya sempurna untuk pipeline build otomatis, layanan pelaporan, atau solusi sisi server apa pun yang perlu memanipulasi file .mpp.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Tasks?** Ia menyediakan API Java untuk membuat, membaca, dan mengedit file Microsoft Project tanpa memerlukan Microsoft Project.  
- **Apakah saya perlu menginstal Microsoft Project?** Tidak, perpustakaan ini bekerja sepenuhnya secara independen.  
- **Versi Java mana yang diperlukan?** JDK 8 atau lebih tinggi.  
- **Bisakah saya menetapkan baseline untuk satu tugas?** Ya – panggil `setBaseline` pada daftar yang hanya berisi tugas yang Anda inginkan.  
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi komersial menghapus batas evaluasi dan membuka semua fitur.

## Apa itu baseline tugas?
Baseline tugas menangkap tanggal mulai, tanggal selesai, dan upaya kerja yang direncanakan awal untuk sebuah tugas pada saat jadwal pertama kali disimpan. Snapshot ini berfungsi sebagai titik referensi, memungkinkan manajer proyek membandingkan kemajuan dan biaya aktual dengan rencana awal, serta menghitung varians untuk analisis kinerja.

## Mengapa menggunakan Aspose.Tasks untuk menambahkan tugas ke proyek di Java?
Anda dapat membuat, memodifikasi, dan menetapkan baseline tugas tanpa instalasi desktop apa pun, yang memungkinkan alur kerja sepenuhnya otomatis. Aspose.Tasks mendukung **lebih dari 50 format input dan output** dan dapat menangani proyek dengan **ratusan tugas** sambil menjaga penggunaan memori di bawah 200 MB, menjadikannya ideal untuk layanan cloud dan pipeline CI/CD.

## Prasyarat
1. **Java Development Kit (JDK)** – instal JDK 8 atau yang lebih baru.  
2. **Aspose.Tasks for Java** – unduh perpustakaan dari [tautan unduhan](https://releases.aspose.com/tasks/java/).  

## Impor paket
Untuk mulai bekerja dengan Aspose.Tasks dalam proyek Java Anda, impor paket yang diperlukan:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Langkah 1: buat objek proyek
Kelas `Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili file Microsoft Project dalam memori. Menginstansiasinya memberi Anda proyek kosong yang dapat Anda isi dengan tugas, sumber daya, dan kalender.

```java
Project project = new Project();
```
Di sini kami menginstansiasi objek `Project` baru – ini mewakili file MS Project yang akan menyimpan daftar tugas kami.

## Langkah 2: tambahkan tugas ke proyek
Kelas `Task` mewakili item kerja individu dalam jadwal proyek. Setiap `Task` dapat memiliki durasi, tanggal mulai, dan penugasan sumber daya masing‑masing.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Dengan menggunakan `getRootTask()` kami mengakses akar hierarki proyek dan **menambahkan tugas ke Microsoft Project**. String `"Task"` adalah nama tugas; Anda dapat menggantinya dengan deskripsi apa pun yang Anda perlukan.

## Langkah 3: tetapkan baseline untuk tugas tertentu
`BaselineType` adalah enumerasi yang menentukan slot baseline mana (Baseline, Baseline1 … Baseline10) yang ingin Anda tulis. Dengan memberikan daftar tugas, Anda dapat menetapkan baseline hanya pada item yang Anda pilih.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Untuk **menetapkan baseline tanpa MS Project**, buat daftar tugas yang ingin Anda beri baseline (di sini `myList`) dan berikan ke `setBaseline`. Isi `myList` dengan tugas yang Anda tambahkan jika Anda hanya memerlukan baseline selektif.

## Langkah 4: tetapkan baseline untuk seluruh proyek
`setBaseline` menulis nilai baseline yang dipilih ke setiap tugas dalam proyek.  
Jika Anda lebih suka menetapkan baseline seluruh proyek dalam satu panggilan, cukup panggil `setBaseline` dengan `BaselineType` yang diinginkan.

```java
project.setBaseline(BaselineType.Baseline);
```
Pemanggilan ini menulis nilai baseline yang dipilih untuk **setiap tugas** dalam proyek, memastikan snapshot lengkap dari jadwal asli.

## Cara menambahkan tugas ke Microsoft Project menggunakan Aspose.Tasks
`add()` membuat tugas anak baru di bawah tugas induk yang ditentukan dan mengembalikan objek `Task` yang baru dibuat.  
Anda menambahkan tugas dengan memanggil `add()` pada objek `Task` induk (biasanya tugas akar). Metode ini mengembalikan instance `Task` baru yang dapat Anda konfigurasikan lebih lanjut—durasi, tanggal mulai, sumber daya, atau bidang khusus—sebelum menyimpan file proyek.

## Cara menetapkan baseline tanpa MS Project
Aspose.Tasks memungkinkan pembuatan baseline sepenuhnya melalui kode. Pilih `BaselineType` (misalnya, `BaselineType.Baseline`) dan panggil `setBaseline`. Anda dapat mengulangi ini dengan `Baseline1`‑`Baseline10` untuk menyimpan beberapa baseline revisi, semuanya tanpa membuka Microsoft Project.

## Masalah umum dan solusinya
- **Baseline tidak muncul:** Pastikan Anda memanggil `project.save("output.mpp")` setelah menetapkan baseline (langkah penyimpanan dihilangkan di sini untuk singkat).  
- **Daftar tugas muncul kosong:** Verifikasi bahwa Anda menambahkan tugas ke induk yang tepat (`getRootTask()` atau sub‑task).  
- **Kesalahan ketidaksesuaian versi:** Gunakan JAR Aspose.Tasks terbaru untuk menjamin kompatibilitas dengan format .mpp yang lebih baru.

## Pertanyaan yang sering diajukan

**T: Bisakah saya menggunakan Aspose.Tasks untuk Java tanpa Microsoft Project terinstal?**  
J: Ya, Aspose.Tasks bekerja secara independen dan tidak memerlukan Microsoft Project pada mesin host.

**T: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi Microsoft Project?**  
J: Tentu saja. Perpustakaan ini mendukung file Project dari 2007 hingga rilis terbaru 2024.

**T: Bisakah saya memanipulasi sumber daya proyek menggunakan Aspose.Tasks untuk Java?**  
J: Ya, Anda dapat menambah, memperbarui, dan menghapus sumber daya secara programatis, sama seperti tugas.

**T: Apakah Aspose.Tasks untuk Java mendukung penetapan ketergantungan tugas?**  
J: Ya, Anda dapat mendefinisikan hubungan predecessor‑successor menggunakan kelas `TaskLink`.

**T: Apakah dukungan teknis tersedia untuk Aspose.Tasks untuk Java?**  
J: Ya, Anda dapat mendapatkan bantuan melalui [forum dukungan](https://forum.aspose.com/c/tasks/15), di mana staf Aspose dan komunitas menjawab pertanyaan.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda telah belajar cara **menambahkan tugas ke proyek** di Java, membuat daftar tugas, dan **menetapkan baseline tanpa MS Project** menggunakan Aspose.Tasks. Pendekatan ini menyederhanakan otomatisasi proyek, menghilangkan kebutuhan instalasi Project desktop, dan memberi Anda kontrol programatik penuh atas setiap aspek jadwal Anda.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutorial Terkait

- [Cara Membuat Proyek aspose.tasks – Menetapkan Atribut Tugas Baru](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Cara Menetapkan Durasi Baseline di Aspose.Tasks untuk Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Buat Tugas Aspose Java – Properti Tugas](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}