---
date: 2026-09-30
description: Pelajari cara mengatur kemajuan dalam proyek MPP dengan Java menggunakan
  Aspose.Tasks, sebuah perpustakaan manajemen proyek Java yang kuat. Ikuti panduan
  langkah demi langkah ini.
keywords:
- how to set progress
- java project management library
- Aspose.Tasks Java
- MPP project Java
lastmod: 2026-09-30
linktitle: Ubah Kemajuan Tugas di Aspose.Tasks
og_description: Cara mengatur kemajuan dalam proyek MPP dengan Java menggunakan Aspose.Tasks,
  perpustakaan manajemen proyek Java terkemuka. Dapatkan panduan lengkap code‑free.
og_image_alt: Guide showing how to set task progress in an MPP file using Aspose.Tasks
  for Java
og_title: Cara mengatur kemajuan dalam proyek MPP menggunakan Java – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  headline: How to set progress in an MPP project using Java and Aspose.Tasks
  type: TechArticle
- description: Learn how to set progress in an MPP project with Java using Aspose.Tasks,
    a robust java project management library. Follow this step‑by‑step guide.
  name: How to set progress in an MPP project using Java and Aspose.Tasks
  steps:
  - name: Set up your Java project
    text: Create a new Maven or Gradle project and add the Aspose.Tasks JAR to your
      classpath. This gives you access to the `Project`, `Task`, and related classes.
  - name: Define the document directory
    text: Specify where the project file will be stored. Replace the placeholder with
      the actual path on your machine. `dataDir` is a string that specifies the folder
      path where the MPP file will be saved.
  - name: Create a new project (create mpp project java)
    text: '`Project` represents an in‑memory Microsoft Project file that can be saved
      to .mpp format.'
  - name: Add a task to the project (add task project)
    text: '`Task` is an object representing a single work item within a Project.'
  - name: Set the task’s progress
    text: '`Tsk.PERCENT_COMPLETE` is the field that stores a task’s completion percentage.'
  - name: Display the updated progress
    text: Reading `Tsk.PERCENT_COMPLETE` returns the current progress value for the
      task. By following these steps you have successfully **created an MPP project
      in Java**, added a task, and **changed its progress** – all using Aspose.Tasks.
  type: HowTo
- questions:
  - answer: Any recent version (2023‑2025) supports `Project` creation; using the
      latest release ensures you have all bug fixes and performance improvements.
    question: What version of Aspose.Tasks is required to create an MPP file?
  - answer: Yes, call `project.save("output.pdf", SaveFileFormat.PDF);` after setting
      the progress to generate a visual report.
    question: Can I export the project to PDF after updating progress?
  - answer: Loop through `project.getRootTask().getChildren()` and set `Tsk.PERCENT_COMPLETE`
      for each task; the API updates each task efficiently.
    question: Is it possible to batch‑update progress for many tasks?
  - answer: Resources must be added explicitly; task progress does not affect resource
      allocation unless you modify resource‑related fields.
    question: Does the library handle resource assignments automatically?
  - answer: Use `project.setPassword("yourPassword");` before calling `project.save(...)`
      to encrypt the file.
    question: How do I protect the generated MPP file with a password?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task progress
title: Cara mengatur kemajuan dalam proyek MPP menggunakan Java dan Aspose.Tasks
url: /id/java/task-properties/change-progress/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur kemajuan dalam proyek MPP menggunakan Java dan Aspose.Tasks

## Pendahuluan
Di era **manajemen proyek java** modern, kemampuan untuk **membuat file mpp project java** dan menjaga kemajuan tugas tetap terbaru sangat penting untuk menyelesaikan tepat waktu. Tutorial ini menunjukkan **cara mengatur kemajuan** untuk sebuah tugas secara programatis dengan Aspose.Tasks, sebuah **perpustakaan manajemen proyek java** yang kuat dan bekerja di Windows, Linux, serta macOS. Anda akan melihat seluruh alur—dari pembuatan proyek hingga memverifikasi persentase selesai yang diperbarui—dijelaskan dengan gaya percakapan, langkah demi langkah.

## Jawaban Cepat
- **Apa arti “create mpp project java”?**  
  Ini merujuk pada pembuatan file Microsoft Project (.mpp) secara programatis menggunakan kode Java.
- **Perpustakaan mana yang membantu ini?**  
  Aspose.Tasks for Java, sebuah **perpustakaan manajemen proyek java** khusus.
- **Berapa baris kode yang diperlukan untuk mengatur kemajuan tugas?**  
  Kurang dari 10 baris setelah proyek diinstansiasi.
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?**  
  Ya, lisensi komersial diperlukan; tersedia versi percobaan gratis.
- **Bisakah saya menjalankannya di IDE Java mana pun?**  
  Tentu – semua IDE yang mendukung Java 8+ dapat digunakan.

## Apa itu “create mpp project java”?
Membuat proyek MPP di Java berarti menggunakan kode untuk menghasilkan file Microsoft Project (`.mpp`) yang dapat dibuka di Microsoft Project atau penampil kompatibel lainnya. Hal ini memungkinkan pembuatan jadwal otomatis, pembuatan tugas massal, dan integrasi mulus dengan sistem perusahaan.

## Mengapa menggunakan Aspose.Tasks sebagai perpustakaan manajemen proyek java?
Aspose.Tasks menyediakan **cakupan API lengkap** untuk pembuatan proyek, manipulasi tugas, dan pelaporan. Ia mendukung **lebih dari 30 format input dan output** serta dapat menangani proyek dengan **hingga 10.000 tugas** tanpa harus memuat seluruh file ke memori, memberikan pemrosesan berkinerja tinggi pada perangkat keras yang sederhana.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Lingkungan Pengembangan Java** – JDK 8 atau lebih tinggi terpasang dan dikonfigurasi.  
2. **Perpustakaan Aspose.Tasks untuk Java** – unduh dari situs resmi: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **Direktori Dokumen** – sebuah folder di mesin Anda tempat file `.mpp` yang dihasilkan akan disimpan.

## Impor paket
Pertama, impor kelas Aspose.Tasks yang Anda perlukan. Potongan kode ini menyiapkan lingkungan dan nanti kita akan menambahkan tugas dengan kemajuan 50 %.

`com.aspose.tasks.*` menyediakan kelas inti seperti **Project**, **Task**, dan **Tsk** untuk bekerja dengan file MPP.  

```java
import com.aspose.tasks.*;
```

## Panduan langkah demi langkah

### Langkah 1: Siapkan proyek Java Anda
Buat proyek Maven atau Gradle baru dan tambahkan JAR Aspose.Tasks ke classpath Anda. Ini memberi Anda akses ke kelas `Project`, `Task`, dan kelas terkait lainnya.

### Langkah 2: Tentukan direktori dokumen
Tentukan lokasi penyimpanan file proyek. Ganti placeholder dengan jalur sebenarnya di mesin Anda.

`dataDir` adalah string yang menentukan jalur folder tempat file MPP akan disimpan.  

```java
String dataDir = "Your Document Directory";
```

### Langkah 3: Buat proyek baru (create mpp project java)
`Project` mewakili file Microsoft Project dalam memori yang dapat disimpan dalam format .mpp.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Langkah 4: Tambahkan tugas ke proyek (add task project)
`Task` adalah objek yang mewakili satu item pekerjaan dalam sebuah Project.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

### Langkah 5: Atur kemajuan tugas
`Tsk.PERCENT_COMPLETE` adalah bidang yang menyimpan persentase penyelesaian sebuah tugas.

```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```

### Langkah 6: Tampilkan kemajuan yang diperbarui
Membaca `Tsk.PERCENT_COMPLETE` mengembalikan nilai kemajuan saat ini untuk tugas tersebut.

```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```

Dengan mengikuti langkah‑langkah ini Anda telah berhasil **membuat proyek MPP di Java**, menambahkan sebuah tugas, dan **mengubah kemajuannya** – semuanya menggunakan Aspose.Tasks.

## Cara mengatur kemajuan untuk sebuah tugas di Aspose.Tasks?
Muat objek `Project` yang ada, temukan `Task` target (atau buat baru), dan tetapkan nilai baru ke `Tsk.PERCENT_COMPLETE`. Perpustakaan secara otomatis menghitung ulang nilai roll‑up untuk tugas induk, sehingga jadwal keseluruhan tetap konsisten. Satu baris kode ini sudah cukup untuk memperbarui kemajuan.

## Masalah umum & pemecahan masalah
- **FileNotFoundException** – Pastikan `dataDir` diakhiri dengan pemisah file (`/` atau `\`) dan direktori tersebut ada.  
- **LicenseException** – Untuk penggunaan produksi, muat lisensi Aspose.Tasks Anda sebelum membuat objek `Project`.  
- **Nilai persentase tidak tepat** – Metode `percent` mengharapkan nilai antara 0 dan 100; memberikan angka di luar rentang ini akan menyebabkan pengecualian.

## Pertanyaan yang sering diajukan

**Q: Versi Aspose.Tasks apa yang diperlukan untuk membuat file MPP?**  
A: Versi terbaru apa pun (2023‑2025) mendukung pembuatan `Project`; menggunakan rilis terbaru memastikan Anda memiliki semua perbaikan bug dan peningkatan kinerja.

**Q: Bisakah saya mengekspor proyek ke PDF setelah memperbarui kemajuan?**  
A: Ya, panggil `project.save("output.pdf", SaveFileFormat.PDF);` setelah mengatur kemajuan untuk menghasilkan laporan visual.

**Q: Apakah memungkinkan memperbarui kemajuan secara batch untuk banyak tugas?**  
A: Lakukan loop melalui `project.getRootTask().getChildren()` dan set `Tsk.PERCENT_COMPLETE` untuk setiap tugas; API memperbarui setiap tugas secara efisien.

**Q: Apakah perpustakaan menangani penugasan sumber daya secara otomatis?**  
A: Sumber daya harus ditambahkan secara eksplisit; kemajuan tugas tidak memengaruhi alokasi sumber daya kecuali Anda mengubah bidang yang terkait dengan sumber daya.

**Q: Bagaimana cara melindungi file MPP yang dihasilkan dengan kata sandi?**  
A: Gunakan `project.setPassword("yourPassword");` sebelum memanggil `project.save(...)` untuk mengenkripsi file.

## Kesimpulan
Menguasai **cara mengatur kemajuan** dalam proyek MPP dengan Java memberi Anda kemampuan untuk mengotomatisasi pemeliharaan jadwal, menjaga pemangku kepentingan tetap terinformasi, dan mengintegrasikan data proyek ke dalam alur kerja perusahaan yang lebih besar. Aspose.Tasks, **perpustakaan manajemen proyek java** terkemuka, membuat tugas‑tugas ini menjadi sederhana dan berkinerja tinggi.

**Terakhir Diperbarui:** 2026-09-30  
**Diuji Dengan:** Aspose.Tasks for Java 24.10  
**Penulis:** Aspose

## Tutorial Terkait

- [Manajemen Proyek Java: Persentase Tugas % menggunakan Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)
- [Cara Memperbarui Data Tugas ke Format MPP dengan Aspose.Tasks untuk Java](/tasks/java/task-properties/update-task-data/)
- [Baca dan Atur Prioritas Tugas dengan Aspose.Tasks untuk Java](/tasks/java/task-properties/handle-priorities/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}