---
date: 2026-09-20
description: Pelajari cara mengelola ketergantungan tugas proyek menggunakan Aspose.Tasks
  for Java. Panduan ini menunjukkan cara menambahkan predecessor links, mencetak task
  names, dan mengatur task dependencies secara efisien.
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: Kelola ketergantungan tugas proyek melalui Aspose.Tasks for Java
og_description: Pelajari cara mengelola ketergantungan tugas proyek menggunakan Aspose.Tasks
  for Java. Panduan ini menunjukkan cara menambahkan predecessor links, mencetak task
  names, dan mengatur task dependencies secara efisien.
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: Kelola ketergantungan tugas proyek melalui Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: Kelola ketergantungan tugas proyek melalui Aspose.Tasks for Java
url: /id/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola ketergantungan tugas proyek melalui Aspose.Tasks untuk Java

## Pendahuluan
Ketergantungan tugas proyek adalah tulang punggung dari setiap jadwal realistis, memungkinkan Anda memodelkan pekerjaan mana yang harus selesai sebelum pekerjaan lain dapat dimulai. Dalam tutorial ini Anda akan belajar cara mengelola **ketergantungan tugas proyek** dengan Aspose.Tasks untuk Java, termasuk cara menambahkan tautan pendahulu, mencetak nama tugas, dan mengatur ketergantungan tugas secara programatis.

## Jawaban Cepat
- **Apa langkah pertama?** Muat file MPP Anda ke dalam objek `Project`.  
- **Bagaimana cara menambahkan pendahulu?** Buat sebuah `TaskLink` dan atur `PredecessorTaskUid` serta `SuccessorTaskUid`-nya.  
- **Bisakah Anda menampilkan semua tautan?** Gunakan `project.getTaskLinks()` dan iterasi koleksinya.  
- **Apakah saya memerlukan lisensi?** Lisensi sementara dapat digunakan untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 atau lebih tinggi.

## Apa itu ketergantungan tugas proyek?
Ketergantungan tugas proyek mendefinisikan hubungan logis antara dua tugas, seperti Finish‑to‑Start atau Start‑to‑Start, dan menentukan urutan pekerjaan yang harus dilakukan. Dengan menetapkan tautan ini, jadwal secara otomatis menghormati kendala dunia nyata, mencegah aktivitas yang tumpang tindih, dan memastikan bahwa tugas hilir hanya dimulai ketika prasyaratnya terpenuhi.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Aspose.Tasks untuk Java mendukung lebih dari tiga puluh format file proyek, termasuk versi Microsoft Project terbaru, dan dapat memproses file hingga dua gigabyte tanpa memuat seluruh dokumen ke dalam memori. Kemampuan berperforma tinggi ini memungkinkan Anda memanipulasi jadwal besar, menghasilkan laporan, dan melakukan pembaruan massal secara efisien, menjadikannya ideal untuk solusi manajemen proyek berskala perusahaan.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

- Lingkungan Pengembangan Java: Java 8 atau lebih baru terpasang di mesin Anda.  
- Perpustakaan Aspose.Tasks untuk Java: Unduh dan instal perpustakaan Aspose.Tasks dari [halaman unduhan Aspose.Tasks untuk Java](https://releases.aspose.com/tasks/java/).  
- Lingkungan Pengembangan Terintegrasi (IDE): Eclipse, IntelliJ IDEA, atau IDE kompatibel Java apa pun yang Anda sukai.

## Impor paket
Anda perlu mengimpor kelas inti yang memungkinkan manipulasi proyek.

Kelas `Project` adalah titik masuk untuk memuat dan menyimpan file Microsoft Project.  
Kelas `TaskLink` mewakili sebuah ketergantungan antara dua tugas.  

## Cara menambahkan tautan pendahulu antara dua tugas?
Buat sebuah instance `TaskLink`, tetapkan UID tugas pendahulu dan UID tugas penerus, pilih `TaskLinkType` yang sesuai seperti Finish‑to‑Start, lalu tambahkan tautan ke koleksi tautan tugas proyek. Setelah ditambahkan, jadwal langsung mencerminkan hubungan ketergantungan baru.

### Langkah 1: inisialisasi objek proyek
Buat instance baru dari kelas `Project` dan berikan jalur ke file proyek Anda (mis., `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### Langkah 2: akses tautan tugas
Ambil semua tautan tugas dari proyek menggunakan metode `getTaskLinks()`.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Langkah 3: iterasi melalui tautan tugas
Gunakan loop untuk iterasi setiap tautan tugas dalam koleksi dan cetak informasi tentang tugas pendahulu dan penerus.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### Langkah 4: tambahkan tautan pendahulu baru (opsional)
Jika Anda perlu membuat ketergantungan baru, buat instance `TaskLink`, atur `PredecessorTaskUid`, `SuccessorTaskUid`, dan `LinkType`, lalu tambahkan ke koleksi tautan proyek.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

Ulangi langkah-langkah ini sesuai kebutuhan untuk persyaratan proyek spesifik Anda.

## Masalah umum dan solusi
- **Pendahulu hilang setelah menambahkan tautan** – Pastikan Anda memanggil `project.updateTaskLinks()` (atau menyimpan dan memuat ulang) sehingga grafik internal diperbarui.  
- **Penurunan kinerja pada file besar** – Gunakan `project.setReadOnly(true)` sebelum operasi massal untuk mengurangi beban memori.  
- **Tipe tautan tidak tepat** – Verifikasi bahwa Anda menggunakan nilai enum `TaskLinkType` yang benar (mis., `FinishToStart`) untuk mencocokkan logika jadwal Anda.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dalam proyek Java yang sudah ada?**  
A: Ya, cukup tambahkan JAR Aspose.Tasks ke classpath Anda atau ke dependensi Maven/Gradle.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai format file proyek?**  
A: Ya, ia mendukung MPP, XML, CSV, dan lebih dari 30 format tambahan.

**Q: Bagaimana cara memperoleh lisensi sementara untuk Aspose.Tasks?**  
A: Dapatkan lisensi sementara dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks?**  
A: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk dukungan komunitas dan diskusi.

**Q: Bisakah saya mengunduh percobaan gratis Aspose.Tasks untuk Java?**  
A: Ya, unduh percobaan gratis dari [halaman percobaan gratis Aspose](https://releases.aspose.com/).

---

**Terakhir Diperbarui:** 2026-09-20  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Ketergantungan Tugas Manajemen Proyek di Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Atur Tanggal Mulai Proyek dan Kelola Tugas Induk serta Anak di Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Baca dan Atur Prioritas Tugas dengan Aspose.Tasks untuk Java](/tasks/java/task-properties/handle-priorities/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}