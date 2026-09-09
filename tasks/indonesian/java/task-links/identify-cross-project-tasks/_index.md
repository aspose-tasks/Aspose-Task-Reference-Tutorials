---
date: 2026-09-09
description: Pelajari cara mengidentifikasi tugas lintas proyek menggunakan Aspose.Tasks
  untuk Java. Jelajahi integrasi mulus, manajemen efisien, dan contoh dunia nyata.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identifikasi tugas lintas proyek di Aspose.Tasks
og_description: Identifikasi tugas lintas proyek di Aspose.Tasks untuk Java. Pelajari
  cara mengatur direktori dokumen, mengambil ID tugas, dan mengelola proyek terkait
  secara efisien.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identifikasi tugas lintas proyek di Aspose.Tasks – Panduan Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identifikasi tugas lintas proyek di Aspose.Tasks
url: /id/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identifikasi tugas lintas proyek di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara mengidentifikasi tugas lintas proyek** dengan Aspose.Tasks untuk Java. Baik Anda mengelola portofolio jadwal yang saling bergantung maupun perlu mengaudit ketergantungan eksternal, langkah‑langkah di bawah ini menunjukkan cara menemukan tugas yang merujuk ke file proyek lain, mengambil pengidentifikasinya, dan bekerja dengan mereka secara programatik.

## Jawaban Cepat
- **Apa arti “identifikasi tugas lintas proyek”?** Artinya menemukan tugas yang merujuk atau bergantung pada tugas dalam file proyek lain.  
- **Metode mana yang mencetak ID tugas?** Gunakan `externalTask.get(Tsk.ID)` untuk mencetak ID tugas.  
- **Bagaimana cara mengatur direktori dokumen?** Tetapkan jalur folder ke variabel `String` (misalnya, `dataDir`).  
- **Properti mana yang mengambil tugas berdasarkan UID?** Panggil `getChildren().getByUid(yourUid)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan produksi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penyebaran komersial.

## Apa itu “identifikasi tugas lintas proyek”?
Mengidentifikasi tugas lintas‑proyek memungkinkan Anda melacak hubungan antara tugas yang tersebar di beberapa file Microsoft Project. Dengan menemukan tugas yang merujuk atau bergantung pada jadwal eksternal, Anda dapat memahami bagaimana item pekerjaan berinteraksi melintasi batas proyek, mencegah duplikasi usaha, dan menjaga garis waktu yang akurat. Kemampuan ini penting untuk portofolio berskala besar di mana tugas dibagikan atau bergantung pada jadwal eksternal.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Aspose.Tasks untuk Java mendukung **lebih dari 50 format input dan output** (termasuk MPP, MPX, XML, dan CSV) dan **dapat memproses proyek dengan hingga 10.000 tugas** tanpa memuat seluruh file ke memori. Perpustakaan ini bekerja pada platform **yang kompatibel dengan JVM**, tidak memerlukan instalasi Microsoft Project, dan menawarkan akses API penuh ke ID, UID, ID eksternal, serta metadata penautan.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Lingkungan pengembangan Java yang berfungsi (JDK 8 atau lebih tinggi).  
- Aspose.Tasks untuk Java terpasang. Anda dapat mengunduhnya **[di sini](https://releases.aspose.com/tasks/java/)**.  
- File lisensi Aspose.Tasks yang valid jika Anda berencana menjalankan kode di lingkungan produksi.

## Impor paket
Kelas `Project` mewakili file Microsoft Project, `Task` mewakili tugas individu, dan `Tsk` menyediakan konstanta bidang tugas.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Langkah 1: atur direktori dokumen
String `dataDir` menyimpan jalur ke folder yang berisi file `.mpp` Anda.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Langkah 2: muat proyek eksternal
`Project externalProject` memuat file proyek eksternal yang ditentukan untuk inspeksi.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Langkah 3: ambil tugas eksternal berdasarkan uid
`externalProject.getChildren().getByUid(uid)` mengambil tugas dari koleksi tugas proyek eksternal menggunakan pengidentifikasi uniknya.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Langkah 4: cetak ID tugas (kasus penggunaan utama)
`externalTask.get(Tsk.ID)` mengembalikan ID internal yang diberikan oleh Aspose.Tasks untuk tugas tersebut.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Langkah 5: cetak ID tugas asli (eksternal)
`externalTask.get(Tsk.ExternalID)` mengambil ID asli tugas sebagaimana didefinisikan dalam file proyek sumber.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Ulangi langkah‑langkah di atas untuk tugas tambahan apa pun yang perlu Anda lacak lintas proyek.

## Masalah umum & tips
- **Kesalahan jalur** – Pastikan `dataDir` diakhiri dengan pemisah file yang sesuai (`/` atau `\\`).  
- **UID tidak ditemukan** – Verifikasi UID ada di proyek eksternal; gunakan `externalProject.getRootTask().getChildren().size()` untuk menampilkan UID yang tersedia.  
- **Pengecualian lisensi** – Lisensi yang hilang atau tidak valid akan menyebabkan pengecualian lisensi pada saat runtime.  
- **Proyek besar** – Untuk proyek dengan lebih dari 5.000 tugas, pertimbangkan menggunakan `ProjectReader` dengan flag `LoadOptions` untuk streaming data dan mengurangi konsumsi memori.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
A: Ya, Aspose.Tasks mendukung banyak bahasa, termasuk Java, .NET, dan lainnya.

**Q: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks untuk Java?**  
A: Lihat dokumentasi **[di sini](https://reference.aspose.com/tasks/java/)**.

**Q: Apakah ada percobaan gratis untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mendapatkan percobaan gratis **[di sini](https://releases.aspose.com/)**.

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Tasks?**  
A: Dapatkan lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)**.

**Q: Butuh bantuan atau memiliki pertanyaan spesifik?**  
A: Kunjungi forum dukungan Aspose.Tasks **[di sini](https://forum.aspose.com/c/tasks/15)**.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Tutorial Terkait

- [Buat Ketergantungan Tugas Manajemen Proyek di Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Atur Tanggal Mulai Proyek dan Kelola Tugas Induk serta Anak di Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Buat Proyek MPP Java – Ubah Progres Tugas dengan Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}