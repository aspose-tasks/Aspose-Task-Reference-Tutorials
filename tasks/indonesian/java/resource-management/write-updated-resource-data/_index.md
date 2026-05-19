---
date: 2026-01-15
description: Pelajari cara menambahkan sumber daya ke proyek, memperbarui data sumber
  daya, dan menyimpan proyek sebagai MPP menggunakan Aspose.Tasks untuk Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Tambahkan Sumber Daya ke Proyek Menggunakan Aspose.Tasks untuk Java
url: /id/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menambahkan Sumber Daya ke Proyek Menggunakan Aspose.Tasks untuk Java

## Introduction
Dalam tutorial praktis ini Anda akan menemukan **cara menambahkan sumber daya ke proyek** secara programatis dengan API Aspose.Tasks Java. Kami akan memandu Anda memuat file XML MS Project yang ada, menyisipkan sumber daya baru, memperbarui propertinya, dan akhirnya **menyimpan proyek sebagai MPP**. Pada akhir tutorial Anda akan memiliki pola yang jelas dan dapat diulang yang dapat Anda gunakan dalam alat pelaporan atau otomatisasi berbasis Java apa pun.

## Quick Answers
- **Apa arti “add resource to project”?** Itu membuat entri sumber daya baru (orang, peralatan, material) di dalam file Microsoft Project.  
- **Perpustakaan mana yang menangani ini?** Aspose.Tasks untuk Java – tidak perlu menginstal Microsoft Project.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengonversi XML ke MPP?** Ya – muat file XML dan **save project as MPP** menggunakan `project.save(...)`.  
- **Versi Java apa yang dibutuhkan?** Java 6 atau lebih baru (Java 8+ disarankan).

## What is “add resource to project”?
Menambahkan sumber daya ke proyek berarti menyisipkan baris baru dalam tabel Resources pada file MS Project. Baris ini menyimpan detail seperti nama, tarif biaya, grup, dan bidang khusus yang dapat dirujuk oleh tugas di kemudian hari.

## Why use Aspose.Tasks for Java?
- **Tidak bergantung pada Microsoft Project** – berfungsi di sistem operasi apa pun atau server CI.  
- **Fidelity penuh** – mempertahankan semua fitur native Project saat mengonversi antar format.  
- **API kaya** – memungkinkan Anda membaca, menulis, dan memanipulasi tugas, sumber daya, kalender, dan lainnya.

## Prerequisites
Sebelum Anda memulai, pastikan Anda memiliki:

1. Java Development Kit (JDK) 8 atau yang lebih baru terinstal.  
2. Perpustakaan Aspose.Tasks untuk Java – unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. Familiaritas dasar dengan sintaks Java serta pengaturan proyek Maven/Gradle.

## Import Packages
Tambahkan kelas Aspose.Tasks yang diperlukan ke file sumber Java Anda:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Set Up Your Data Directory
Tentukan lokasi di mana file XML sumber dan file MPP hasil akan disimpan:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Specify Input and Output Files
Tunjuk file XML yang ingin Anda konversi (**convert XML to MPP**) dan file MPP target yang akan berisi sumber daya baru:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Step 3: Load the Project
Buat objek `Project` dari sumber XML:

```java
Project project = new Project(file);
```

## Step 4: Add a Resource and Set Attributes
Di sinilah kita **add resource to project** dan mengonfigurasi tarif serta grupnya:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Pro tip:* Anda dapat mengulangi pemanggilan `add` di dalam loop untuk **update multiple resources** dalam satu kali proses.

## Step 5: Save the Project
Akhirnya, **save project as MPP** untuk menyimpan perubahan:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusion
Anda baru saja mempelajari **cara menambahkan sumber daya ke proyek**, memperbarui propertinya, dan **menyimpan proyek sebagai MPP** menggunakan Aspose.Tasks untuk Java. Pendekatan ini ideal untuk pipeline pelaporan otomatis, impor sumber daya massal, atau skenario apa pun yang memerlukan manipulasi file MS Project tanpa aplikasi desktop.

## Frequently Asked Questions

**Q1: Can I update multiple resources in the same project using Aspose.Tasks for Java?**  
A: Ya, iterasi melalui `project.getResources()` atau panggil `add` berulang kali, mengatur bidang masing‑masing sumber daya sesuai kebutuhan.

**Q2: Does Aspose.Tasks support other file formats besides MS Project?**  
A: Tentu – XML, MPP, MPX, Primavera, dan lainnya semuanya didukung.

**Q3: Is Aspose.Tasks compatible with different versions of Java?**  
A: Perpustakaan ini bekerja dengan Java 6 dan yang lebih baru; Java 8+ sangat disarankan untuk kinerja optimal.

**Q4: Can I perform other operations on MS Project files with Aspose.Tasks?**  
A: Ya, Anda dapat membaca/menulis tugas, kalender, penugasan, bidang khusus, bahkan menghasilkan laporan.

**Q5: Where can I find additional help or support for Aspose.Tasks?**  
A: Kunjungi [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk bantuan komunitas dan dukungan resmi.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}