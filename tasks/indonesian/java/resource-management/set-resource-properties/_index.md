---
date: 2026-08-24
description: Pelajari cara menambahkan sumber daya MS Project, mengatur tarif standar,
  dan properti sumber daya lainnya di MS Project menggunakan Aspose.Tasks untuk Java,
  serta mengelola sumber daya secara efisien.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Atur Properti Sumber Daya di Aspose.Tasks
og_description: Tambahkan sumber daya MS Project dan atur tarif standar menggunakan
  Aspose.Tasks untuk Java. Pelajari prasyarat, kode langkah demi langkah, dan pemecahan
  masalah dalam panduan singkat ini.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Tambahkan sumber daya MS Project dan atur tarif dengan Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Cara menambahkan sumber daya MS Project dengan Aspose.Tasks
url: /id/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan sumber daya ms project dan atur tarif di Aspose.Tasks

## Pendahuluan
Jika Anda mengembangkan aplikasi Java yang perlu membaca atau menulis file Microsoft Project, **menambahkan sumber daya ms project** dan mengonfigurasi tarif standar merupakan tugas rutin namun penting. Dalam panduan ini Anda akan melihat cara membuat objek `Project`, menambahkan sumber daya, dan mengatur tarif standar serta lembur menggunakan Aspose.Tasks untuk Java. Pada akhir panduan Anda akan dapat mengotomatisasi perhitungan biaya dan menjaga jadwal proyek tetap mutakhir tanpa memerlukan instalasi Microsoft Project.

## Jawaban Cepat
- **Apa kelas yang mewakili file Project?** `Project`
- **Pemanggilan mana yang menambahkan sumber daya baru?** `project.getResources().add()`
- **Bagaimana cara mengatur tarif standar?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Apakah lisensi diperlukan untuk penggunaan produksi?** Ya, Anda harus memuat lisensi Aspose.Tasks yang valid.
- **Versi Java mana yang didukung?** Java 8 dan yang lebih baru (Java 17+ disarankan).

## Apa itu “set standard rate”?
Operasi *set standard rate* menetapkan biaya per jam default untuk sebuah sumber daya. Tarif ini digunakan oleh manajer proyek untuk menghitung biaya tenaga kerja, menghasilkan laporan biaya, dan meramalkan anggaran, memastikan bahwa perhitungan biaya mencerminkan harga yang diharapkan untuk pekerjaan yang dilakukan oleh setiap sumber daya sepanjang siklus hidup proyek.

## Mengapa mengatur tarif dengan Aspose.Tasks?
Aspose.Tasks dapat memproses **lebih dari 50 format input dan output**, termasuk file MPP, MPX, XML, dan Primavera, serta menangani proyek ratusan halaman tanpa harus memuat seluruh file ke dalam memori. Hal ini memungkinkan pemrosesan batch berkecepatan tinggi di server Windows, Linux, atau macOS, mengurangi upaya manual hingga 90 % dalam skenario otomasi tipikal.

## Prasyarat
Sebelum Anda memulai, pastikan hal‑hal berikut sudah siap:

### Penyiapan lingkungan pengembangan Java
1. Instal JDK 8 atau yang lebih baru. Anda dapat mengunduhnya dari [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Pilih IDE seperti IntelliJ IDEA, Eclipse, atau NetBeans dan konfigurasikan untuk pengembangan Java.

### Instalasi Aspose.Tasks untuk Java
1. Unduh paket Aspose.Tasks untuk Java terbaru dari [download page](https://releases.aspose.com/tasks/java/).  
2. Tambahkan file JAR ke classpath proyek Anda atau deklarasikan dependensi Maven/Gradle seperti yang ditunjukkan dalam dokumentasi produk.

## Impor paket
Impor kelas inti Aspose.Tasks yang Anda perlukan. Langkah ini memberi Anda akses ke tipe `Project`, `Resource`, dan `Rsc` yang akan digunakan nanti.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Langkah 1: buat objek proyek
Kelas `Project` adalah objek tingkat atas yang mewakili seluruh file MS Project dalam memori. Membuat instance-nya menghasilkan proyek kosong yang dapat Anda isi dengan tugas, sumber daya, dan data lainnya.

```java
Project project = new Project();
```

## Langkah 2: tambahkan sumber daya (add resource ms project)
Kelas `Resource` memodelkan satu sumber daya proyek seperti orang, peralatan, atau material. Menambahkan sumber daya melalui `project.getResources().add()` mengembalikan instance `Resource` yang tidak null dan siap untuk konfigurasi properti.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Langkah 3: atur properti sumber daya (cara mengatur tarif)
Enum `Rsc` berisi konstanta untuk bidang sumber daya seperti `STANDARD_RATE` dan `OVERTIME_RATE`.  
Anda mengatur tarif standar dan lembur dengan memanggil `set` pada objek `Resource` menggunakan nilai enum `Rsc` yang sesuai. Tarif disimpan sebagai `BigDecimal` untuk mempertahankan presisi moneter.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Masalah umum dan solusi
| Masalah | Mengapa terjadi | Solusi |
|-------|----------------|-----|
| `NullPointerException` when calling `set` | Sumber daya tidak ditambahkan dengan benar. | Pastikan `project.getResources().add()` mengembalikan `Resource` yang tidak null. |
| Rates appear as 0 in the saved file | Menggunakan `int` alih‑alih `BigDecimal`. | Selalu gunakan `BigDecimal.valueOf()` untuk nilai moneter. |
| License not found | File lisensi tidak dimuat sebelum membuat `Project`. | Muat lisensi (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) saat program dimulai. |

## Kesimpulan
Anda kini tahu cara **menambahkan sumber daya ms project**, membuat objek `Project`, dan **mengatur tarif standar serta lembur** menggunakan Aspose.Tasks untuk Java. Kemampuan ini memungkinkan Anda mengotomatisasi perhitungan biaya, menghasilkan laporan khusus, dan mengelola sumber daya MS Project sepenuhnya dari aplikasi Java mana pun.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah Aspose.Tasks untuk Java menangani file MS Project yang kompleks?**  
A: Ya, ia mendukung semua format Project utama, termasuk file besar dengan ribuan tugas dan sumber daya, serta mempertahankan setiap bidang tanpa kehilangan data.

**Q: Apakah tersedia trial gratis?**  
A: Ya, Anda dapat mengakses trial gratis Aspose.Tasks untuk Java dari [Aspose.Tasks free trial page](https://releases.aspose.com/).

**Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat mencari bantuan di [support forum](https://forum.aspose.com/c/tasks/15).

**Q: Bagaimana cara mendapatkan lisensi sementara untuk evaluasi?**  
A: Lisensi sementara tersedia di [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat membeli versi berlisensi?**  
A: Beli lisensi penuh di [purchase page](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutorial Terkait

- [Cara Membuat Sumber Daya – Manajemen Sumber Daya dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/)
- [Tambahkan sumber daya ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/create-resources/)
- [Cara Menambahkan Sumber Daya ke Proyek dan Menangani Properti Penundaan Leveling dalam Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}