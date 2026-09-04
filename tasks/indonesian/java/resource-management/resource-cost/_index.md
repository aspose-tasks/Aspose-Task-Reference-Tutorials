---
date: 2026-06-15
description: Pelajari cara mengelola biaya dalam file MS Project menggunakan Aspose.Tasks
  untuk Java, termasuk cara memuat file MPP dan membaca actual cost work serta budgeted
  cost schedule.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Kelola Biaya Sumber Daya di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Mengelola Biaya di MS Project dengan Aspose.Tasks untuk Java
url: /id/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengelola Biaya di MS Project dengan Aspose.Tasks untuk Java

## Pendahuluan

Mengelola anggaran proyek adalah tanggung jawab utama bagi setiap manajer proyek, dan **cara mengelola biaya** secara efektif dapat menentukan keberhasilan proyek. Aspose.Tasks untuk Java memberi Anda kontrol programatis atas file Microsoft Project, memungkinkan Anda membaca dan memperbarui data biaya sumber daya tanpa harus membuka file .mpp secara manual. Dalam tutorial ini Anda akan melihat langkah demi langkah cara memuat file MPP, memeriksa actual cost work, dan mengekstrak jadwal biaya yang dianggarkan untuk setiap sumber daya.

## Jawaban Cepat
- **Apa yang dilakukan Aspose.Tasks untuk Java?** Ia membaca dan menulis file Microsoft Project (.mpp) tanpa memerlukan Microsoft Project terinstal.  
- **Bagaimana cara memuat file MPP?** Gunakan `new Project("path/to/file.mpp")` – API mem-parsing file di memori.  
- **Bidang biaya mana yang tersedia?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS), dan Budgeted Cost of Work Performed (BCWP).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Lisensi sementara gratis dapat digunakan untuk pengujian; lisensi penuh diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 dan yang lebih baru, termasuk Java 17 LTS.

## Cara Mengelola Biaya di MS Project?

Muat proyek Anda dengan `new Project("yourFile.mpp")`, kemudian iterasi melalui setiap objek `Resource` untuk membaca properti terkait biaya seperti ACWP, BCWS, dan BCWP. Aspose.Tasks secara otomatis mengonversi nilai biaya internal ke mata uang proyek, sehingga Anda dapat menampilkan atau menyimpannya langsung. Pendekatan ini menghilangkan perhitungan spreadsheet manual dan menjamin konsistensi data di semua laporan proyek.

## Prasyarat

1. Pemahaman dasar tentang pemrograman Java.  
2. Perpustakaan Aspose.Tasks untuk Java ditambahkan ke proyek Anda (Maven/Gradle atau JAR manual).  
3. Akses ke file Microsoft Project (`.mpp`) yang ingin Anda analisis.  

## Impor Paket

Kelas `Project` dan `Resource` adalah titik masuk untuk bekerja dengan data proyek.

Kelas `Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Langkah 1: Tentukan Direktori Data

Pertama, tentukan folder yang berisi file `.mpp` Anda. Jalur ini dapat berupa absolut atau relatif terhadap direktori kerja aplikasi Anda.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Langkah 2: Muat File MS Project

`Project` memuat file dan membangun model objek yang dapat Anda query. API mem-parsing file tanpa memerlukan Microsoft Project terinstal, mendukung lebih dari 30 format input.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Langkah 3: Iterasi Melalui Sumber Daya

Objek `Resource` mewakili orang, peralatan, atau material yang mengonsumsi anggaran. Anda dapat melakukan loop melalui koleksi `project.getResources()` untuk mengakses masing‑masing.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Langkah 4: Periksa Nama dan Biaya Sumber Daya

Untuk setiap sumber daya, pastikan bahwa nama telah didefinisikan, kemudian baca bidang biaya. Metode `getActualCost()` mengembalikan **actual cost work** (ACWP), sementara `getBudgetedCost()` memberikan Anda **budgeted cost schedule** (BCWS/BCWP).

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Mengapa Menggunakan Aspose.Tasks untuk Java untuk Memuat File MPP?

Aspose.Tasks mendukung **lebih dari 30 format file** (termasuk `.mpp`, `.xml`, dan `.xlsx`) dan dapat memproses proyek dengan **hingga 10.000 tugas** sambil menggunakan kurang dari 200 MB RAM. Perpustakaan melakukan semua perhitungan di sisi server, menghilangkan kebutuhan akan salinan Microsoft Project berlisensi.

## Masalah Umum dan Solusinya

- **Null resource names:** Beberapa file warisan berisi sumber daya placeholder. Selalu periksa `resource.getName() != null` sebelum mengakses properti biaya.  
- **Large files causing memory pressure:** LoadOptions adalah kelas konfigurasi yang memungkinkan Anda menentukan data proyek mana yang akan dimuat. Gunakan `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` untuk memuat hanya data yang Anda butuhkan, kemudian aktifkan nanti jika diperlukan.  
- **Currency mismatches:** API menghormati pengaturan mata uang proyek; Anda dapat menimpanya dengan `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` jika diperlukan. CostRateTableType mengenumerasi berbagai tabel tarif biaya yang dapat diterapkan pada sebuah tugas.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?**  
A: Ya, ia sepenuhnya mendukung tugas ringkasan bersarang, beberapa kalender sumber daya, dan bidang khusus di semua versi Project yang didukung.

**Q: Apakah perpustakaan kompatibel dengan berbagai versi file Microsoft Project?**  
A: Tentu saja. Aspose.Tasks membaca dan menulis file dari Microsoft Project 2000 hingga format terbaru 2023.

**Q: Dapatkah saya mengintegrasikan Aspose.Tasks untuk Java dengan perpustakaan Java lainnya?**  
A: Ya, API mengembalikan objek Java standar, memungkinkan integrasi mulus dengan kerangka kerja logging, alat ORM, atau perpustakaan pelaporan.

**Q: Apakah Aspose.Tasks untuk Java menawarkan dukungan pelanggan?**  
A: Aspose menyediakan dukungan forum khusus, dokumentasi terperinci, dan bantuan email responsif untuk pengguna berlisensi.

**Q: Apakah ada percobaan gratis untuk Aspose.Tasks untuk Java?**  
A: Anda dapat mengunduh lisensi evaluasi 30‑hari dari situs web Aspose untuk menjelajahi semua fitur tanpa biaya.

---

**Terakhir Diperbarui:** 2026-06-15  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Menghitung Variansi Biaya dan Mengelola Biaya Penugasan dengan Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Manajemen Anggaran, Pekerjaan, dan Biaya untuk Tugas di Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Menambahkan sumber daya ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}