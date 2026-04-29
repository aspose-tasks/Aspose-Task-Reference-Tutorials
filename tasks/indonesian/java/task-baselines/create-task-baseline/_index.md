---
date: 2026-01-18
description: Pelajari cara membuat daftar tugas Java dan menambahkan tugas ke Microsoft
  Project, menetapkan baseline tanpa MS Project menggunakan Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Buat Daftar Tugas Java – Baseline MS Project menggunakan Aspose.Tasks
url: /id/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Daftar Tugas Java – Baseline MS Project dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini, Anda akan **membuat daftar tugas Java** dengan menghasilkan baseline tugas Microsoft Project menggunakan Aspose.Tasks untuk Java. Aspose.Tasks memungkinkan Anda bekerja dengan file Project tanpa harus menginstal Microsoft Project, sehingga Anda dapat **menambahkan tugas ke Microsoft Project**, memanipulasi sumber daya, dan bahkan **menetapkan baseline tanpa MS Project**—semuanya dari kode Java murni.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Tasks?** Menyediakan API Java untuk membuat, membaca, dan mengedit file Microsoft Project tanpa MS Project.  
- **Apakah saya perlu menginstal Microsoft Project?** Tidak, Aspose.Tasks berfungsi secara mandiri.  
- **Versi Java mana yang diperlukan?** JDK 8 atau lebih tinggi.  
- **Bisakah saya menetapkan baseline untuk satu tugas saja?** Ya, gunakan `setBaseline` dengan daftar tugas.  
- **Apakah lisensi diperlukan untuk produksi?** Ya, lisensi komersial menghapus batas evaluasi.

## Apa Itu Baseline Tugas?
Baseline tugas mencatat nilai awal yang direncanakan untuk tanggal mulai, selesai, dan pekerjaan sebuah tugas. Ini berfungsi sebagai titik referensi untuk membandingkan kemajuan aktual dengan rencana asli.

## Mengapa Menggunakan Aspose.Tasks untuk Membuat Daftar Tugas Java?
- **Tanpa ketergantungan MS Project** – ideal untuk otomatisasi sisi server.  
- **Kontrol penuh** atas tugas, sumber daya, dan kalender melalui kode Java.  
- **Kompatibilitas lintas versi** dengan file Project 2007‑2024.

## Prasyarat
1. **Java Development Kit (JDK)** – instal JDK 8 atau yang lebih baru.  
2. **Aspose.Tasks untuk Java** – unduh pustaka dari [tautan unduhan](https://releases.aspose.com/tasks/java/).  

## Impor Paket
Untuk mulai bekerja dengan Aspose.Tasks dalam proyek Java Anda, impor paket yang diperlukan:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Langkah 1: Buat Objek Project
```java
Project project = new Project();
```
Di sini kami menginstansiasi objek `Project` baru – ini mewakili file MS Project yang akan menampung daftar tugas kami.

## Langkah 2: Tambahkan Tugas ke Project
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Dengan menggunakan `getRootTask()` kami mengakses akar hierarki proyek dan **menambahkan tugas ke Microsoft Project**. String `"Task"` adalah nama tugas; Anda dapat menggantinya dengan deskripsi apa pun yang diperlukan.

## Langkah 3: Tetapkan Baseline untuk Tugas yang Ditentukan
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Untuk **menetapkan baseline tanpa MS Project**, buat daftar tugas yang ingin Anda beri baseline (di sini `myList`) dan berikan ke `setBaseline`. Isi `myList` dengan tugas‑tugas yang Anda tambahkan jika hanya memerlukan baseline selektif.

## Langkah 4: Tetapkan Baseline untuk Seluruh Proyek
```java
project.setBaseline(BaselineType.Baseline);
```
Jika Anda lebih suka memberi baseline seluruh proyek dalam satu panggilan, cukup panggil `setBaseline` dengan `BaselineType` yang diinginkan.

## Cara menambahkan tugas ke Microsoft Project menggunakan Aspose.Tasks
Selain tugas tunggal yang ditunjukkan di atas, Anda dapat menambahkan banyak tugas, sub‑tugas, dan menetapkan sumber daya. Setiap pemanggilan `add()` mengembalikan objek `Task` yang dapat Anda konfigurasi lebih lanjut (durasi, tanggal mulai, dll.).

## Cara menetapkan baseline tanpa MS Project
Aspose.Tasks memungkinkan pembuatan baseline sepenuhnya melalui kode. Anda dapat menetapkan berbagai jenis baseline (Baseline, Baseline1‑Baseline10) dengan mengubah enum `BaselineType`, memungkinkan Anda melacak beberapa baseline revisi tanpa pernah membuka MS Project.

## Masalah Umum dan Solusinya
- **Baseline tidak muncul:** Pastikan Anda memanggil `project.save("output.mpp")` setelah menetapkan baseline (langkah penyimpanan dihilangkan di sini untuk singkat).  
- **Daftar tugas muncul kosong:** Verifikasi bahwa Anda menambahkan tugas ke induk yang tepat (`getRootTask()` atau sub‑tugas).  
- **Kesalahan ketidakcocokan versi:** Gunakan JAR Aspose.Tasks terbaru untuk menjamin kompatibilitas dengan format .mpp yang lebih baru.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Tasks untuk Java tanpa Microsoft Project terinstal?**  
J: Ya, Aspose.Tasks berfungsi secara mandiri dan tidak memerlukan Microsoft Project di mesin host.

**T: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi Microsoft Project?**  
J: Tentu saja. Pustaka ini mendukung file Project dari 2007 hingga rilis terbaru 2024.

**T: Bisakah saya memanipulasi sumber daya proyek menggunakan Aspose.Tasks untuk Java?**  
J: Ya, Anda dapat menambah, memperbarui, dan menghapus sumber daya secara programatik, sama seperti tugas.

**T: Apakah Aspose.Tasks untuk Java mendukung penetapan ketergantungan tugas?**  
J: Ya, Anda dapat mendefinisikan hubungan predecessor‑successor menggunakan kelas `TaskLink`.

**T: Apakah dukungan teknis tersedia untuk Aspose.Tasks untuk Java?**  
J: Ya, Anda dapat mendapatkan bantuan melalui [forum dukungan](https://forum.aspose.com/c/tasks/15), di mana staf Aspose dan komunitas menjawab pertanyaan.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini, Anda telah mempelajari cara **membuat daftar tugas Java**, **menambahkan tugas ke Microsoft Project**, dan **menetapkan baseline tanpa MS Project** menggunakan Aspose.Tasks. Pendekatan ini mempermudah otomatisasi proyek, menghilangkan kebutuhan instalasi Project desktop, dan memberi Anda kontrol penuh secara programatik atas data proyek Anda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-18  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose  

---