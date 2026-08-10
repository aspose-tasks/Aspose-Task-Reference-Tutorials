---
date: 2026-07-14
description: Pelajari cara menghentikan penugasan sumber daya java, mengelola penugasan
  sumber daya, dan melihat contoh menggunakan Aspose.Tasks for Java dalam panduan
  langkah demi langkah ini.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Hentikan dan Lanjutkan Penugasan Sumber Daya di Aspose.Tasks
og_description: Hentikan penugasan sumber daya java dengan Aspose.Tasks. Tutorial
  ini menunjukkan cara menjeda dan melanjutkan penugasan, menangani tanggal, dan mengintegrasikan
  API tanpa Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Hentikan Penugasan Sumber Daya Java – Panduan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Cara Menghentikan Penugasan Sumber Daya Java – Lanjutkan dengan Aspose.Tasks
url: /id/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menghentikan Penugasan Sumber Daya Java – Melanjutkan dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar **how to stop resource assignment java** dan kemudian melanjutkannya menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah API Java yang kuat yang memungkinkan Anda membaca dan menulis file Microsoft Project, memanipulasi jadwal, dan mengontrol penugasan sumber daya—semua tanpa perlu menginstal Microsoft Project. Kami akan membahas setiap langkah, menjelaskan mengapa setiap baris penting, dan berbagi tips praktis yang dapat Anda terapkan pada rencana proyek dunia nyata.

## Jawaban Cepat
- **What does “stop assignment” mean?** Itu menandai penugasan sumber daya sebagai tidak aktif sementara mulai dari tanggal penghentian tertentu.  
- **Can I resume the same assignment later?** Ya, dengan menetapkan tanggal resume pada penugasan yang sama.  
- **Do I need Microsoft Project to use this API?** Tidak, Aspose.Tasks berfungsi secara independen dari Microsoft Project.  
- **Which Java version is required?** Java 8 atau lebih tinggi disarankan.  
- **Where can I download the library?** Dari halaman unduhan resmi Aspose.Tasks Java.

## Cara menghentikan resource assignment java?
Muat proyek Anda, temukan `ResourceAssignment` target, tetapkan tanggal `STOP`, secara opsional tetapkan tanggal `RESUME`, lalu simpan file. Urutan ini menghentikan pekerjaan untuk periode yang ditentukan dan secara otomatis mengaktifkannya kembali setelah tanggal resume, memberi Anda kontrol yang tepat atas kalender sumber daya tanpa mengedit file secara manual.

## Apa itu “how to stop assignment” dalam konteks Aspose.Tasks?
Menghentikan sebuah penugasan memberi tahu penjadwal untuk mengabaikan pekerjaan yang dialokasikan ke sebuah sumber daya setelah **stop date** hingga **resume date** (jika ada). Ini berguna untuk menangani cuti, downtime peralatan, atau periode apa pun ketika sebuah sumber daya tidak boleh dianggap aktif.

## Mengapa menggunakan Aspose.Tasks untuk mengelola penugasan sumber daya?
Aspose.Tasks memungkinkan Anda mengontrol tanggal penugasan secara programatis, menghilangkan edit manual dan mengurangi risiko kesalahan. Ia mendukung **lebih dari 50 format input dan output** dan dapat memproses proyek dengan **hingga 10.000 tugas** sambil menjaga penggunaan memori di bawah 200 MB karena data diproses secara streaming alih-alih memuat seluruh file ke memori. API ini berjalan di semua OS yang mendukung Java, memberikan fleksibilitas lintas‑platform.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki:

- Java Development Kit (JDK) 8 atau yang lebih baru terinstal.  
- Perpustakaan Aspose.Tasks untuk Java sudah diunduh. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/tasks/java/).  
- Pemahaman dasar tentang pemrograman Java.  

## Mengimpor Paket
Kelas `Project`, `ResourceAssignment`, dan `Asn` berada di namespace `com.aspose.tasks`. Impor mereka di bagian atas file sumber Anda:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Langkah 1: Muat File Proyek
Kelas `Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori. Membuat sebuah instance memuat file dan memberi Anda akses ke tugas, sumber daya, dan penugasan.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Langkah 2: Iterasi Melalui Penugasan Sumber Daya
Objek `ResourceAssignment` menampilkan semua bidang yang terkait dengan penugasan. Kami menetapkan **minimum date** untuk menyaring tanggal placeholder dan kemudian melakukan loop melalui setiap penugasan. Pola ini adalah contoh *resource assignment* standar untuk inspeksi atau modifikasi.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Langkah 3: Periksa Tanggal STOP dan RESUME
Dalam blok ini kami memeriksa bidang `STOP` dan `RESUME` untuk setiap penugasan. Jika sebuah tanggal sebelum `minDate` kami, kami menganggapnya tidak diatur (`"NA"`); jika tidak, kami mencetak tanggal sebenarnya. Logika ini penting untuk **manage resource assignments** dengan benar.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Masalah Umum dan Solusinya
- **Null dates** – `ra.get(Asn.STOP)` mungkin mengembalikan `null`. Lindungi dengan menambahkan pemeriksaan null sebelum memanggil `.before(minDate)`.  
- **Incorrect file path** – Pastikan `dataDir` diakhiri dengan pemisah jalur (`/` atau `\\`) yang sesuai untuk OS Anda.  
- **Version mismatch** – Gunakan versi terbaru Aspose.Tasks untuk Java untuk menghindari nilai enum yang hilang.

## Pertanyaan yang Sering Diajukan

**Q: How do I programmatically set a stop date for an assignment?**  
A: Gunakan `ra.set(Asn.STOP, yourDateObject);` dimana `yourDateObject` adalah `java.util.Date`.

**Q: What happens if the resume date is earlier than the stop date?**  
A: API tidak menegakkan urutan kronologis; namun, penjadwal akan memperlakukan penugasan sebagai aktif hanya setelah tanggal yang lebih akhir di antara keduanya, jadi Anda harus memvalidasi tanggal secara manual.

**Q: Can I filter assignments to only those that have a stop date set?**  
A: Ya, iterasi melalui `prj.getResourceAssignments()` dan periksa `ra.get(Asn.STOP) != null`.

**Q: Is it possible to remove a stop date once set?**  
A: Tetapkan tanggal stop menjadi `null` dengan `ra.set(Asn.STOP, null);` lalu simpan proyek.

**Q: Does Aspose.Tasks support other date‑related fields like start, finish, or actual start?**  
A: Tentu saja. Enum `Asn` menyediakan konstanta untuk semua bidang penugasan, seperti `Asn.START`, `Asn.FINISH`, dll.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini mengetahui **how to stop resource assignment java**, memeriksa tanggal stop/resume, dan melanjutkan penugasan bila diperlukan. Kemampuan ini memungkinkan Anda **manage resource assignments** dengan lebih tepat, terutama dalam skenario seperti cuti sumber daya atau downtime peralatan. Jangan ragu untuk memperluas contoh ini untuk memperbarui tanggal, menghasilkan laporan, atau mengintegrasikannya dengan logika penjadwalan Anda sendiri.

---

**Terakhir Diperbarui:** 2026-07-14  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Cara Menghitung Variansi Biaya dan Mengelola Biaya Penugasan dengan Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Cara Menambahkan Catatan ke Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}