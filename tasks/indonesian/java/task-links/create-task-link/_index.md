---
date: 2026-07-05
description: Pelajari cara membuat ketergantungan tugas manajemen proyek di Java menggunakan
  Aspose.Tasks. Ikuti panduan langkah demi langkah ini dengan potongan kode.
keywords:
- project management task dependencies
- Aspose.Tasks Java
- task linking tutorial
linktitle: Buat Ketergantungan Tugas Manajemen Proyek di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  headline: Create Project Management Task Dependencies in Aspose.Tasks
  type: TechArticle
- description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  name: Create Project Management Task Dependencies in Aspose.Tasks
  steps:
  - name: Set Document Directory
    text: Define the directory where your documents are stored to ensure Aspose.Tasks
      locates and processes files correctly. The `java.nio.file.Paths` utility helps
      you build platform‑independent file paths. java // The path to the documents
      directory. String dataDir = "Your Document Directory";
  - name: Initialize Project and Tasks
    text: Create a new project and initialize tasks within it. In this example, "Task
      1" and "Task 2" are added to the root task. The `Task` class represents an individual
      work item; each task can have its own ID, name, and schedule. java Project project
      = new Project(dataDir + "project5.mpp"); Task pred = pr
  - name: Establish Task Link
    text: Utilize the `getTaskLinks()` method to add a link between two tasks. This
      example demonstrates linking "Task 1" as a predecessor to "Task 2." The `TaskLink`
      object defines the type of dependency (Finish‑to‑Start, Start‑to‑Start, etc.)
      and optional lag. java TaskLink link = project.getTaskLinks().add
  - name: Display Result
    text: Print a message indicating the successful completion of the task link creation
      process. This step is crucial for debugging and verification. A simple `System.out.println`
      call confirms that the link was added without errors. java // Display the result
      of the conversion. System.out.println("Task Link
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks seamlessly integrates with Spring, Jakarta EE, Android,
      and any standard Java environment.
    question: Can I use Aspose.Tasks for Java with other Java frameworks?
  - answer: Yes, explore the functionalities with the [free trial](https://releases.aspose.com/)
      before making a commitment.
    question: Is there a free trial available before purchasing the library?
  - answer: Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: Yes, check the documentation for comprehensive sample projects and code
      snippets.
    question: Are there any sample projects available for reference?
  - answer: Secure your copy by visiting the [purchase page](https://purchase.aspose.com/buy)
      and explore licensing options.
    question: What is the recommended way to purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Buat Ketergantungan Tugas Manajemen Proyek di Aspose.Tasks
url: /id/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Ketergantungan Tugas Manajemen Proyek di Aspose.Tasks

## Pendahuluan
Ketergantungan tugas manajemen proyek adalah tulang punggung dari setiap jadwal yang terstruktur dengan baik, memungkinkan perhitungan otomatis tanggal mulai, tanggal selesai, dan jalur kritis. Dalam tutorial ini Anda akan belajar cara membuat **project management task dependencies** dalam Java menggunakan Aspose.Tasks, sebuah perpustakaan yang mendukung lebih dari 50 format file dan dapat menangani proyek dengan ribuan tugas tanpa memuat seluruh file ke memori. Ikuti langkah‑langkah di bawah ini untuk menautkan tugas, memverifikasi tautan, dan mengintegrasikan solusi ke dalam aplikasi dunia nyata.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Membuat tautan tugas (dependencies) dengan Aspose.Tasks untuk Java.  
- **Berapa banyak baris kode yang diperlukan?** Logika penghubungan inti dapat diselesaikan dalam hanya dua pernyataan.  
- **Apakah saya memerlukan lisensi untuk mencobanya?** Versi percobaan gratis selama 30 hari tersedia; lisensi diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 sampai 17 didukung sepenuhnya.  
- **Bisakah saya menautkan lebih dari dua tugas?** Ya – ulangi pola penautan untuk sejumlah pasangan pendahulu‑penerus.

## Apa itu ketergantungan tugas manajemen proyek?
Ketergantungan tugas manajemen proyek mendefinisikan bagaimana mulai atau selesai satu tugas berhubungan dengan tugas lainnya, menentukan urutan pekerjaan yang harus dilakukan. Aspose.Tasks merepresentasikan hubungan ini melalui objek `TaskLink`, yang dapat Anda buat, ubah, atau hapus secara programatis.

## Mengapa menggunakan Aspose.Tasks untuk penautan tugas?
Aspose.Tasks mendukung **lebih dari 50 format input dan output** (termasuk MPP, XML, dan CSV) dan dapat memproses proyek dengan **lebih dari 10.000 tugas** sambil menggunakan kurang dari 200 MB RAM pada server tipikal. API‑nya memberi Anda kontrol detail atas jenis tautan, waktu jeda, dan penanganan kendala tanpa memerlukan instalasi Microsoft Project.

## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Siapkan lingkungan pengembangan Java yang berfungsi di mesin Anda.  
- Perpustakaan Aspose.Tasks: Unduh dan integrasikan perpustakaan Aspose.Tasks untuk Java, tersedia [di sini](https://releases.aspose.com/tasks/java/).

## Impor Paket
Untuk memulai, impor paket yang diperlukan ke dalam proyek Java Anda. Ini penting untuk mengakses fungsionalitas Aspose.Tasks.

Kelas `Project` adalah titik masuk Aspose.Tasks yang mewakili seluruh file proyek dalam memori.  
```text
```java
import com.aspose.tasks.*;
```
```

## Cara membuat tautan tugas menggunakan Aspose.Tasks untuk Java?
Muat atau buat sebuah instance `Project`, tambahkan tugas yang diperlukan, lalu panggil `getTaskLinks().add()` untuk menetapkan ketergantungan. Metode ini membuat objek `TaskLink` yang menautkan tugas pendahulu dan penerus, dengan opsi untuk menentukan jenis tautan dan jeda. Langkah‑langkah berikut akan memandu Anda melalui kode yang tepat—tanpa boilerplate tambahan.

### Langkah 1: Atur Direktori Dokumen
Tentukan direktori tempat dokumen Anda disimpan untuk memastikan Aspose.Tasks menemukan dan memproses file dengan benar.

Utilitas `java.nio.file.Paths` membantu Anda membangun jalur file yang independen platform.  
```text
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
```

### Langkah 2: Inisialisasi Proyek dan Tugas
Buat proyek baru dan inisialisasi tugas di dalamnya. Pada contoh ini, "Task 1" dan "Task 2" ditambahkan ke tugas root.

Kelas `Task` mewakili item kerja individu; setiap tugas dapat memiliki ID, nama, dan jadwalnya masing‑masing.  
```text
```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```
```

### Langkah 3: Membuat Tautan Tugas
Manfaatkan metode `getTaskLinks()` untuk menambahkan tautan antara dua tugas. Contoh ini menunjukkan penautan "Task 1" sebagai pendahulu ke "Task 2."

Objek `TaskLink` menentukan jenis ketergantungan (Finish‑to‑Start, Start‑to‑Start, dll.) dan jeda opsional.  
```text
```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```
```

### Langkah 4: Tampilkan Hasil
Cetak pesan yang menunjukkan keberhasilan proses pembuatan tautan tugas. Langkah ini penting untuk debugging dan verifikasi.

Pemanggilan `System.out.println` sederhana mengonfirmasi bahwa tautan telah ditambahkan tanpa error.  
```text
```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```
```

Ulangi langkah‑langkah ini untuk skenario penautan tugas yang lebih rumit, sesuaikan nama tugas, dan tetapkan ketergantungan sesuai kebutuhan proyek Anda.

Rujuk ke [Aspose.Tasks Documentation](https://reference.aspose.com/tasks/java/) untuk informasi API yang detail.  
Untuk dukungan komunitas, kunjungi [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15).

## Masalah Umum dan Solusinya
Metode `save` menulis proyek ke jalur file yang ditentukan, menyimpan semua perubahan termasuk tautan yang ditambahkan.  
Enumerasi `TaskLinkType` mendefinisikan jenis hubungan, seperti `FinishToStart` untuk ketergantungan selesai‑ke‑mulai.

- **Tautan tidak muncul di file yang disimpan** – Pastikan Anda memanggil `project.save(outputPath)` setelah menambahkan tautan.  
- **Jenis tautan tidak tepat** – Gunakan `TaskLinkType.FinishToStart`, `StartToStart`, dll., untuk menyesuaikan dengan logika penjadwalan Anda.  
- **Proyek besar menyebabkan lonjakan memori** – Aktifkan `project.setReadOnly(true)` sebelum memuat untuk bekerja dalam mode streaming.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan kerangka kerja Java lain?**  
A: Ya, Aspose.Tasks terintegrasi mulus dengan Spring, Jakarta EE, Android, dan lingkungan Java standar apa pun.

**Q: Apakah tersedia versi percobaan gratis sebelum membeli perpustakaan?**  
A: Ya, jelajahi fungsionalitas dengan [free trial](https://releases.aspose.com/) sebelum membuat komitmen.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Dapatkan lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.

**Q: Apakah ada proyek contoh yang tersedia untuk referensi?**  
A: Ya, periksa dokumentasi untuk proyek contoh komprehensif dan potongan kode.

**Q: Apa cara yang direkomendasikan untuk membeli Aspose.Tasks untuk Java?**  
A: Amankan salinan Anda dengan mengunjungi [purchase page](https://purchase.aspose.com/buy) dan jelajahi opsi lisensi.

---

**Terakhir Diperbarui:** 2026-07-05  
**Diuji dengan:** Aspose.Tasks 24.12 untuk Java  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Tugas Aspose Java – Properti Tugas](/tasks/java/task-properties/)
- [Baseline Manajemen Proyek – Penjadwalan Tugas dengan Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)
- [Cara Membuat Sumber Daya – Manajemen Sumber Daya dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}