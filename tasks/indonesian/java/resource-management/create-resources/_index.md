---
date: 2026-08-18
description: Pelajari cara menambahkan sumber daya ms project dalam Java menggunakan
  Aspose.Tasks. Tutorial langkah demi langkah ini menunjukkan cara membuat dan mengonfigurasi
  sumber daya Microsoft Project secara programatis.
keywords:
- add resource ms project
- aspose tasks java
- resource management java
- add multiple resources
- how to add resource
lastmod: 2026-08-18
linktitle: Buat Sumber Daya di Aspose.Tasks
og_description: Pelajari cara menambahkan sumber daya ms project dalam Java menggunakan
  Aspose.Tasks. Panduan ini membawa Anda melalui prasyarat, langkah kode, dan masalah
  umum dalam waktu kurang dari 10 menit.
og_image_alt: Screenshot of Java code adding a resource to a Microsoft Project file
  with Aspose.Tasks
og_title: Menambahkan sumber daya ms project dengan Aspose.Tasks untuk Java
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add resource ms project in Java using Aspose.Tasks. This
    step‑by‑step tutorial shows creating and configuring Microsoft Project resources
    programmatically.
  headline: Add resource ms project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to add resource ms project in Java using Aspose.Tasks. This
    step‑by‑step tutorial shows creating and configuring Microsoft Project resources
    programmatically.
  name: Add resource ms project with Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Aspose.Tasks for Java library** – download it from the official Aspose.Tasks
      for Java download page [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from the official Aspose.Tasks
      for Java download page [download page](https://releases.aspose.com/tasks/java/).'
  - name: An IDE (IntelliJ, Eclipse) or a build tool such as Maven/Gradle to reference
      the Aspose.Tasks JAR.
    text: An IDE (IntelliJ, Eclipse) or a build tool such as Maven/Gradle to reference
      the Aspose.Tasks JAR.
  type: HowTo
- questions:
  - answer: Call `project.getResources().add("Resource1");` repeatedly, or iterate
      over a collection of names and add each one inside a loop.
    question: How do I add multiple resources in one go?
  - answer: Yes—use `resource.set(ResourceFieldId.Text1, "Custom Value");` to store
      additional information such as department or skill level.
    question: Can I set custom fields for a resource?
  - answer: While Aspose.Tasks doesn’t read Excel directly, you can read the spreadsheet
      with Aspose.Cells, then create resources programmatically using the same `add`
      method.
    question: Is it possible to import resources from an Excel file?
  - answer: Yes—Aspose.Tasks can save to .xml, .pdf, .xlsx, and several other formats
      supported by the API.
    question: Does the library support saving to formats other than .mpp?
  - answer: The sample works with all recent releases; we tested it with Aspose.Tasks
      24.x for Java.
    question: What version of Aspose.Tasks is required for this code?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add resource ms project
- aspose.tasks
- java project automation
title: Menambahkan sumber daya ms project dengan Aspose.Tasks untuk Java
url: /id/java/resource-management/create-resources/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan sumber daya ms project dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **menambahkan sumber daya ms project** secara programatis menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda membangun solusi manajemen proyek khusus atau mengotomatisasi pembaruan massal pada file Microsoft Project yang ada, langkah‑langkah di bawah ini mencakup semuanya mulai dari penyiapan lingkungan hingga menyimpan sumber daya yang sepenuhnya terdefinisi. Pendekatan ini bekerja pada platform apa pun yang menjalankan Java, tanpa memerlukan Microsoft Project terpasang.

## Jawaban Cepat
- **Apa tujuan utama?** Untuk menambahkan sumber daya baru—orang, peralatan, atau material—ke file Microsoft Project menggunakan Java.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengembangan; lisensi permanen membuka semua fitur untuk produksi.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit untuk skenario dasar yang ditunjukkan di sini.  
- **Bisakah saya menambahkan beberapa sumber daya?** Ya—ulangi pemanggilan `add` untuk setiap sumber daya tambahan atau lakukan loop pada koleksi.

## Apa itu “menambahkan sumber daya ke proyek”?
**Menambahkan sumber daya ke proyek** berarti menyisipkan catatan sumber daya baru—seperti anggota tim, peralatan, atau material yang dapat dikonsumsi—ke dalam file Microsoft Project (.mpp). Setelah ditambahkan, sumber daya dapat ditugaskan ke tugas, biaya dapat dilacak, dan muncul dalam laporan yang dihasilkan dari proyek.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Anda dapat menambahkan sumber daya ke proyek hanya dengan dua baris kode Java, dan pustaka ini menangani semua struktur XML dan biner di bawahnya secara otomatis. Aspose.Tasks mendukung **lebih dari 50 metode API** di seluruh tugas, sumber daya, kalender, dan pelaporan, serta dapat memproses proyek dengan **lebih dari 10.000 tugas** dalam waktu kurang dari 2 detik pada perangkat keras server tipikal, menjadikannya ideal untuk otomasi skala perusahaan.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru terpasang.  
2. **Aspose.Tasks untuk Java** – unduh dari halaman unduhan resmi Aspose.Tasks untuk Java [download page](https://releases.aspose.com/tasks/java/).  
3. IDE (IntelliJ, Eclipse) atau alat build seperti Maven/Gradle untuk merujuk JAR Aspose.Tasks.

## Impor paket
Di file sumber Java Anda, impor kelas Aspose.Tasks penting yang akan Anda gunakan sepanjang tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
```

## Langkah 1: menginisialisasi objek proyek
Kelas `Project` adalah objek tingkat‑atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori. Membuat sebuah instance memberi Anda wadah untuk tugas, sumber daya, kalender, dan data proyek lainnya.

```java
Project project = new Project();
```

## Langkah 2: menambahkan sumber daya
Kelas `Resource` memodelkan sumber daya proyek seperti orang, peralatan, atau material. Menambahkan sebuah instance ke koleksi sumber daya proyek mendaftarkannya dalam file sehingga Anda dapat kemudian menugaskannya ke tugas atau mengatur tarif biaya.

```java
Resource resource = project.getResources().add("ResourceName");
```

> **Tip Pro:** Setelah menambahkan sumber daya, Anda dapat mengatur properti tambahan seperti `resource.setCostRateTable(...)` atau `resource.setType(ResourceType.Work)` untuk menyesuaikan perilakunya.

## Masalah umum dan solusi
| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| **NullPointerException** saat memanggil `project.getResources()` | Objek Project tidak diinisialisasi. | Pastikan `Project project = new Project();` dijalankan sebelum mengakses sumber daya. |
| **Sumber daya tidak muncul dalam file yang disimpan** | Lupa menyimpan proyek setelah menambahkan sumber daya. | Panggil `project.save("MyProject.mpp");` (tambahkan langkah penyimpanan jika diperlukan). |
| **Kesalahan lisensi** | Menggunakan versi percobaan tanpa menerapkan lisensi sementara. | Terapkan lisensi sementara melalui `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Kesimpulan
Anda kini telah mempelajari cara **menambahkan sumber daya ms project** menggunakan Aspose.Tasks untuk Java. Pendekatan programatis yang ringkas ini memungkinkan Anda mengelola sumber daya secara skala, mengotomatisasi pembaruan massal, dan mengintegrasikan data Microsoft Project ke dalam aplikasi Java Anda sendiri tanpa ketergantungan UI apa pun.

## Pertanyaan yang Sering Diajukan
**T: Bagaimana cara menambahkan beberapa sumber daya sekaligus?**  
J: Panggil `project.getResources().add("Resource1");` berulang kali, atau iterasi atas koleksi nama dan tambahkan masing‑masing di dalam loop.

**T: Bisakah saya mengatur bidang khusus untuk sebuah sumber daya?**  
J: Ya—gunakan `resource.set(ResourceFieldId.Text1, "Custom Value");` untuk menyimpan informasi tambahan seperti departemen atau tingkat keahlian.

**T: Apakah memungkinkan mengimpor sumber daya dari file Excel?**  
J: Meskipun Aspose.Tasks tidak membaca Excel secara langsung, Anda dapat membaca spreadsheet dengan Aspose.Cells, lalu membuat sumber daya secara programatis menggunakan metode `add` yang sama.

**T: Apakah pustaka ini mendukung penyimpanan ke format selain .mpp?**  
J: Ya—Aspose.Tasks dapat menyimpan ke .xml, .pdf, .xlsx, dan beberapa format lain yang didukung oleh API.

**T: Versi Aspose.Tasks apa yang diperlukan untuk kode ini?**  
J: Contoh ini bekerja dengan semua rilis terbaru; kami mengujinya dengan Aspose.Tasks 24.x untuk Java.

---

**Terakhir Diperbarui:** 2026-08-18  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.x (terbaru pada saat penulisan)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat Sumber Daya – Manajemen Sumber Daya dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/)
- [Kelola Biaya Sumber Daya MS Project dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/resource-cost/)
- [Cara Menambahkan Sumber Daya ke Proyek dan Menangani Properti Penundaan Leveling dalam Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}