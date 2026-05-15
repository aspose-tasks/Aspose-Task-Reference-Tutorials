---
date: 2026-01-13
description: Pelajari cara mengiterasi sumber daya non‑akar dalam file Microsoft Project
  menggunakan Aspose.Tasks untuk Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Iterasi Sumber Daya Non-Akar dengan Aspose.Tasks untuk Java
url: /id/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Iterasi Sumber Daya Non-Root dengan Aspose.Tasks untuk Java

## Introduction
Aspose.Tasks untuk Java adalah pustaka yang kuat yang memberikan pengembang cara bersih dan berorientasi‑objek untuk bekerja dengan file Microsoft Project. Dalam tutorial ini Anda akan belajar **cara mengiterasi sumber daya non‑root** sehingga Anda dapat membaca, memodifikasi, atau menganalisis data sumber daya tanpa berurusan dengan placeholder root. Baik Anda sedang membangun alat pelaporan, skrip migrasi, atau penjadwal khusus, menguasai teknik ini akan membuat kode Anda lebih tepat dan efisien.

## Quick Answers
- **Apa arti “sumber daya non‑root”?** Sebuah sumber daya yang bukan placeholder “Project” default (node root).  
- **Mengapa menyaring sumber daya root?** Root tidak memiliki data penjadwalan yang berguna dan dapat membuat laporan menjadi berantakan.  
- **Kelas Aspose.Tasks mana yang menyediakan koleksi sumber daya?** `Project.getResources()`.  
- **Apakah saya memerlukan lisensi untuk kode ini?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya menggunakan ini dengan Java 17?** Ya – Aspose.Tasks mendukung Java 8 ke atas.

## Prerequisites
Sebelum menyelam ke dalam kode, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – Instal JDK terbaru dari [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Pustaka Aspose.Tasks untuk Java** – Unduh JAR terbaru dari [download page](https://releases.aspose.com/tasks/java/).  

## Import Packages
Di proyek Java Anda, impor kelas Aspose.Tasks yang diperlukan:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Step 1: Set up the Data Directory
```java
String dataDir = "Your Data Directory";
```
Ganti `"Your Data Directory"` dengan path absolut tempat file `.mpp` Anda berada.

## Step 2: Load the Project File
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Ini membuat instance `Project` dengan memuat **ResourceCosts.mpp** dari folder yang Anda tentukan.

## Step 3: Iterate Over Non-Root Resources
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Loop ini berjalan melalui setiap objek `Resource` dalam proyek. Pemeriksaan `isRoot()` melewatkan sumber daya root bawaan, dan pernyataan `System.out.println` mencetak nama setiap **sumber daya non‑root**.

## How to Iterate Non-Root Resources
Potongan kode di atas memperlihatkan pola inti:

1. Dapatkan koleksi lengkap dengan `prj.getResources()`.  
2. Gunakan `isRoot()` untuk menyaring placeholder.  
3. Akses bidang sumber daya apa pun (misalnya `Rsc.NAME`, `Rsc.COST`) sesuai kebutuhan.

Anda dapat memperluas pola ini untuk mengakumulasi biaya, mengekspor ke CSV, atau menerapkan aturan bisnis khusus.

## Common Pitfalls & Tips
- **Pemeriksaan null** – Beberapa sumber daya mungkin memiliki bidang opsional; selalu lindungi terhadap `null` saat memanggil `get()`.  
- **Kinerja** – Untuk proyek yang sangat besar, pertimbangkan iterasi dengan loop berbasis indeks untuk menghindari pembuatan koleksi menengah.  
- **Lisensi** – Menjalankan kode tanpa lisensi yang valid akan menambahkan watermark pada file yang diekspor; pastikan Anda mengaktifkan lisensi di awal aplikasi.

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda kini **tahu cara mengiterasi sumber daya non‑root** menggunakan Aspose.Tasks untuk Java. Teknik ini membantu Anda fokus pada sumber daya proyek yang sebenarnya, membersihkan ekstrak data, dan membangun solusi manajemen proyek yang lebih andal.

## FAQ's
### Bisakah saya menggunakan Aspose.Tasks untuk Java untuk membuat file proyek baru?
Ya, Aspose.Tasks menyediakan kemampuan CRUD (Create, Read, Update, Delete) lengkap untuk format proyek MPP, MPT, dan XML.  

### Apakah Aspose.Tasks mendukung semua versi file Microsoft Project?
Tentu saja. Ia menangani file Project 2003‑2019, termasuk spesifikasi MPP terbaru.  

### Apakah Aspose.Tasks kompatibel dengan kerangka kerja Java seperti Spring?
Ya, Anda dapat menyuntikkan pustaka ke dalam bean Spring atau menggunakannya dalam aplikasi Java standar apa pun.  

### Bisakah saya menyesuaikan bidang data proyek menggunakan Aspose.Tasks?
Tentu. API memungkinkan Anda menambah, memodifikasi, atau menghapus bidang khusus pada tugas, sumber daya, dan penugasan.  

### Apakah Aspose.Tasks menyediakan dukungan dan dokumentasi untuk pengembang?
Produk ini mencakup dokumentasi API yang komprehensif, contoh kode, dan forum dukungan khusus untuk bantuan cepat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Terakhir Diperbarui:** 2026-01-13  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose