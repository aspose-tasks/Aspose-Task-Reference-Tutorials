---
date: 2026-08-29
description: Pelajari cara mengatur tipe tautan dan mengelola ketergantungan tugas
  dengan Aspose.Tasks untuk Java dalam tutorial langkah demi langkah.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Cara Mengatur Tipe Tautan di Aspose.Tasks untuk Java
og_description: Pelajari cara mengatur tipe tautan dan mengelola ketergantungan tugas
  dengan Aspose.Tasks untuk Java. Panduan langkah demi langkah untuk pengembang.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Cara mengatur tipe tautan di Aspose.Tasks untuk Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Cara Mengatur Tipe Tautan di Aspose.Tasks untuk Java
url: /id/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengatur jenis tautan di Aspose.Tasks untuk Java

## Pendahuluan
Jika Anda bertanya-tanya **cara mengatur tautan** antara tugas saat Anda *mengelola ketergantungan tugas* dalam sebuah proyek, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan memandu Anda membuat proyek baru, menambahkan tugas, dan menentukan jenis tautan (Start‑to‑Start, Finish‑to‑Start, dll.) menggunakan Aspose.Tasks untuk Java. Pada akhir tutorial Anda akan merasa percaya diri menyesuaikan hubungan tugas agar sesuai dengan kebutuhan penjadwalan dunia nyata dan Anda akan melihat bagaimana API menangani rencana berskala besar dengan hingga 10.000 tugas.

## Jawaban Cepat
- **Kelas apa yang mewakili ketergantungan?** `TaskLink` adalah objek inti yang memodelkan tautan antara dua tugas.  
- **Enum mana yang mendefinisikan tipe hubungan?** `TaskLinkType` (misalnya, `StartToStart`, `FinishToStart`).  
- **Bisakah saya membaca jenis tautan yang ada?** Ya – iterasi `Project.getTaskLinks()` dan panggil `getLinkType()`.  
- **Apakah saya memerlukan lisensi untuk kode ini?** Lisensi sementara berfungsi untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Apakah ini kompatibel dengan Java 8+?** Tentu – Aspose.Tasks mendukung Java 8 hingga Java 21, mencakup 13 rilis utama.

## Apa itu tautan tugas?
**Tautan tugas** memodelkan ketergantungan antara dua tugas dalam jadwal proyek. Anda dapat membuat, memodifikasi, atau menghapus `TaskLink` untuk mencerminkan hubungan pendahulu‑penerus, memungkinkan penjadwal menghitung tanggal mulai dan selesai secara otomatis.

## Mengapa menggunakan jenis tautan Aspose.Tasks?
Aspose.Tasks mendukung **lebih dari 30 format input dan output** serta dapat memproses proyek yang berisi **hingga 10.000 tugas** tanpa harus memuat seluruh file ke memori. Kemampuan terkuantifikasi ini memastikan kinerja cepat bahkan untuk rencana berskala perusahaan, dan perpustakaan ini mempertahankan semua fitur Microsoft Project seperti bidang khusus dan penugasan sumber daya.

## Prasyarat
- **Lingkungan Pengembangan Java** – JDK 8 atau yang lebih baru sudah terpasang dan dikonfigurasi.  
- **Pustaka Aspose.Tasks** – Unduh JAR terbaru dari [tautan unduhan](https://releases.aspose.com/tasks/java/).  
- **Direktori Dokumen** – Buat folder di mesin Anda tempat Anda akan menyimpan file contoh proyek.

## Impor paket
Kami mulai dengan mengimpor kelas-kelas penting Aspose.Tasks. Ini menyiapkan IDE untuk mengenali panggilan API yang akan kami gunakan nanti.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Cara mengatur jenis tautan di Aspose.Tasks untuk Java?
Muat instance `Project` yang baru, tambahkan dua tugas, lalu buat `TaskLink` dengan `TaskLinkType` yang diinginkan. Pola dua langkah ini memungkinkan Anda mendefinisikan salah satu dari empat tipe ketergantungan standar dalam satu pemanggilan. `Project` mewakili seluruh file proyek dan jadwalnya. `Task` adalah item kerja individu dalam proyek. `TaskLink` menghubungkan tugas pendahulu dengan tugas penerus. `TaskLinkType` adalah enumerasi yang menentukan hubungan (Start‑to‑Start, Finish‑to‑Start, dll.).

### Langkah 1: mengatur jenis tautan
`TaskLink` mewakili ketergantungan antara dua tugas, sementara `TaskLinkType` mengenumerasikan tipe hubungan yang mungkin seperti `StartToStart`. Pada langkah ini kami membuat proyek baru, menambahkan dua tugas, dan menautkannya menggunakan hubungan **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Pro tip:** Anda dapat mengganti `StartToStart` dengan `FinishToStart`, `StartToFinish`, atau `FinishToFinish` tergantung pada ketergantungan yang perlu Anda **kelola ketergantungan tugas**.

### Langkah 2: mendapatkan jenis tautan
`Project.getTaskLinks()` mengembalikan koleksi semua objek `TaskLink` dalam jadwal. Dengan mengiterasi koleksi ini Anda dapat membaca `TaskLinkType` masing‑masing tautan dan memverifikasi bahwa hubungan yang benar telah disimpan.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

Konsol akan menampilkan nilai seperti `StartToStart`, `FinishToStart`, dll., mengonfirmasi jenis tautan yang sebelumnya Anda atur.

## Masalah umum & solusi
- **NullPointerException saat menambahkan tautan** – Pastikan kedua tugas pendahulu dan penerus sudah ditambahkan ke proyek sebelum membuat `TaskLink`.  
- **Jenis tautan tidak tepat setelah menyimpan** – Selalu panggil `project.save("output.mpp")` (atau format lain yang didukung) setelah mengatur jenis tautan untuk menyimpan perubahan.  
- **Lisensi tidak ditemukan** – Letakkan file lisensi Aspose.Tasks Anda di classpath proyek dan muat dengan `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Pertanyaan yang sering diajukan

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai lingkungan Java?**  
A: Ya, Aspose.Tasks terintegrasi dengan Java SE standar, Java EE, dan kit pengembangan Android tanpa ketergantungan tambahan.

**Q: Bisakah saya menyesuaikan jenis tautan berdasarkan kebutuhan proyek saya?**  
A: Tentu. Enum `TaskLinkType` menyediakan empat tipe standar, dan Anda dapat menggabungkannya dengan nilai lag untuk memodelkan jadwal yang kompleks.

**Q: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks untuk Java?**  
A: Lihat [dokumentasi Aspose.Tasks untuk Java](https://reference.aspose.com/tasks/java/) untuk panduan mendalam, referensi API, dan contoh kode.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?**  
A: Kunjungi [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk memperoleh lisensi sementara untuk keperluan pengujian.

**Q: Di mana saya dapat mendapatkan dukungan untuk pertanyaan terkait Aspose.Tasks?**  
A: Bergabunglah dengan komunitas Aspose.Tasks di [forum dukungan](https://forum.aspose.com/c/tasks/15) untuk bantuan dan diskusi.

**Q: Bisakah saya mengubah jenis tautan setelah proyek disimpan?**  
A: Ya. Muat proyek, ambil `TaskLink`, panggil `setLinkType()` dengan nilai enum baru, dan simpan proyek kembali.

**Q: Apakah Aspose.Tasks mendukung pembacaan file Microsoft Project (MPP)?**  
A: Ya. Gunakan `new Project("file.mpp")` untuk memuat file MPP dan bekerja dengan tautan tugasnya seperti contoh XML di atas.

---

**Terakhir Diperbarui:** 2026-08-29  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Tautan Tugas Lintas Proyek di Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Atur Tanggal Mulai Proyek dan Kelola Tugas Induk serta Anak di Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Muat File MPP Java - Kelola Properti Proyek dengan Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}