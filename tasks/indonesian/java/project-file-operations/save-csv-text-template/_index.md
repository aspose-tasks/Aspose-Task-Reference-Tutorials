---
date: 2025-12-21
description: Pelajari cara menyimpan proyek sebagai templat, mengekspor MPP ke CSV,
  dan mengonversi MPP ke teks menggunakan Aspose.Tasks untuk Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspose.Tasks untuk Java
url: /id/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspise.Tasks

## Introduction
Dalam tutorial ini, Anda akan menemukan **cara menyimpan proyek sebagai template** dan juga cara mengekspor file Microsoft Project (MPP) Anda ke format CSV dan teks biasa menggunakan pustaka Aspose.Tasks untuk Java. Apakah Anda perlu membuat template proyek yang dapat digunakan kembali, menghasilkan laporan CSV untuk analitik, atau menghasilkan ekstrak teks sederhana untuk integrasi, langkah‑langkah ini akan memandu Anda melalui proses dengan cepat dan efisien.

## Quick Answers
- **Bisakah saya mengekspor MPP ke CSV?** Ya – gunakan `project.save(..., SaveFileFormat.CSV)`.  
- **Bagaimana cara mengekspor teks?** Simpan dengan `SaveFileFormat.TEXT`.  
- **Apa yang dilakukan “save project as template”?** Itu membuat file `.mpt` yang menghapus nilai aktual dan baseline, siap untuk digunakan kembali.  
- **Apakah saya membutuhkan lisensi?** Versi percobaan tersedia; lisensi komersial diperlukan untuk produksi.  
- **Versi Java apa yang diperlukan?** Java 8+ didukung.

## What is “save project as template”?
Menyimpan proyek sebagai template (`.mpt`) menangkap struktur, hierarki tugas, dan penugasan sumber daya sambil menghapus tanggal mulai/selesai aktual serta data baseline. Hal ini menjadikan template ideal untuk menggunakan kembali tata letak proyek standar pada banyak proyek baru.

## Why use Aspose.Tasks for Java?
Aspose.Tasks memungkinkan Anda memanipulasi file Microsoft Project tanpa harus menginstal Microsoft Project itu sendiri. Ia mendukung **cara mengekspor MPP**, **cara mengekspor teks**, dan **mengonversi MPP ke CSV**, semuanya dari kode Java murni, yang sempurna untuk otomatisasi sisi server, pipeline CI, atau utilitas desktop.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. Java Development Kit (JDK) 8 atau yang lebih tinggi terpasang.  
2. Pustaka Aspose.Tasks untuk Java ditambahkan ke proyek Anda. Unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. Familiaritas dasar dengan sintaks Java serta pengaturan proyek Maven/Gradle.

## Import Packages
First, import the required classes in your Java source file:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Save Project as CSV (Export MPP to CSV)
Mengekspor file MPP ke CSV berguna untuk analisis data di Excel atau alat BI.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Save Project as Text (How to Export Text)
Jika Anda membutuhkan representasi teks biasa dari tugas, sumber daya, atau penugasan, simpan proyek sebagai file teks.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Save as Text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Save Project as Template (Create Project Template Java)
Membuat template yang dapat digunakan kembali menghapus tanggal aktual dan baseline, meninggalkan kerangka bersih untuk proyek baru.

### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Step 2: Set Template Options
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Step 3: Save as Template
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Common Issues & Tips
- **File Tidak Ditemukan:** Pastikan jalur ke `YourProject.mpp` benar atau gunakan jalur absolut.  
- **Pengecualian Lisensi:** Tanpa lisensi yang valid, pustaka berjalan dalam mode evaluasi dan dapat menambahkan watermark. Terapkan lisensi Anda di awal kode (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Proyek Besar:** Untuk file MPP yang sangat besar, pertimbangkan meningkatkan ukuran heap JVM (`-Xmx2g`) untuk menghindari `OutOfMemoryError`.

## Conclusion
Kami telah membahas **cara menyimpan proyek sebagai template**, serta cara **mengekspor MPP ke CSV** dan **mengonversi MPP ke teks** menggunakan Aspose.Tasks untuk Java. Kemampuan ini memungkinkan Anda mengotomatisasi penanganan data proyek, menghasilkan template yang dapat digunakan kembali, dan mengintegrasikan informasi proyek ke sistem lain—semua tanpa perlu menginstal Microsoft Project.

## FAQ's
### Q: Can Aspose.Tasks for Java handle complex project files?
A: Tentu saja! Aspose.Tasks untuk Java dapat menangani proyek dengan berbagai tingkat kompleksitas dengan mudah, menyediakan dukungan komprehensif untuk format file Microsoft Project.

### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Ya, Anda dapat memperoleh versi percobaan gratis Aspose.Tasks untuk Java dari [here](https://releases.aspose.com/).

### Q: Where can I find support for Aspose.Tasks for Java?
A: Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan mengenai Aspose.Tasks untuk Java.

### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Ya, Anda dapat membeli lisensi sementara dari [here](https://purchase.aspose.com/temporary-license/), yang memungkinkan Anda mengevaluasi potensi penuh pustaka ini.

### Q: Is Aspose.Tasks for Java compatible with different operating systems?
A: Ya, Aspose.Tasks untuk Java kompatibel dengan berbagai sistem operasi, termasuk Windows, macOS, dan Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

---