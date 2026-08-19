---
date: 2026-02-26
description: Pelajari cara menyimpan proyek sebagai PDF dan menghasilkan lembar tugas
  menggunakan Aspose.Tasks untuk Java. Ekspor MPP ke PDF dengan cepat menggunakan
  panduan langkah demi langkah ini.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Simpan Proyek sebagai PDF – Render Lembar Tugas dengan Aspose.Tasks untuk Java
url: /id/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan Proyek sebagai PDF – Render Lembar Tugas di Aspose.Tasks

## Introduction
Dalam panduan komprehensif ini Anda akan menemukan cara **save project as PDF** dan menghasilkan lembar tugas dengan Aspose.Tasks untuk Java. Baik Anda perlu mengekspor file MPP ke PDF untuk tinjauan pemangku kepentingan atau sekadar merender lembar tugas yang bersih untuk pelaporan, tutorial ini akan memandu Anda melalui setiap langkah, menjelaskan mengapa setiap pengaturan penting, dan menampilkan kode tepat yang perlu Anda jalankan.

## Quick Answers
- **What does “save project as pdf” do?** Itu mengonversi file Microsoft Project (MPP) menjadi dokumen PDF, secara opsional memformatnya sebagai lembar tugas.  
- **Which format is used for a task‑sheet PDF?** Opsi `PresentationFormat.TaskSheet` dalam `PdfSaveOptions`.  
- **Do I need a license to run the code?** Lisensi sementara atau penuh diperlukan untuk produksi; versi percobaan gratis dapat digunakan untuk evaluasi.  
- **What are the main prerequisites?** Java JDK, pustaka Aspose.Tasks untuk Java, dan file proyek yang valid (misalnya *.mpp).  
- **Can I customize the PDF layout?** Ya, Aspose.Tasks menawarkan banyak properti `PdfSaveOptions` untuk styling dan pengaturan halaman.

## What is “save project as pdf”?
Menyimpan proyek sebagai PDF mengubah data proyek internal menjadi dokumen portabel yang hanya dapat dibaca. Ini ideal untuk berbagi jadwal, lembar tugas, atau laporan status dengan pemangku kepentingan yang tidak memiliki Microsoft Project terpasang.

## Why render a task sheet?
Lembar tugas menampilkan setiap tugas dalam tampilan tabel, memperlihatkan ID, nama, tanggal mulai/selesai, dan bidang lainnya. Merendernya ke PDF memastikan format yang konsisten di semua platform dan memudahkan pencetakan atau penyisipan ke dokumen lain.

## Prerequisites
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi terbaru terpasang dan `java`/`javac` tersedia di PATH Anda.  
2. **Aspose.Tasks for Java** – unduh pustaka dari situs resmi [here](https://releases.aspose.com/tasks/java/).  
3. File **proyek** yang valid (`*.mpp`) yang ingin Anda konversi, misalnya `NewProductDev.mpp`.  

## Import Packages
Pertama, impor kelas Aspose.Tasks yang diperlukan. Impor ini memberi Anda akses ke opsi penyimpanan PDF, format presentasi, dan objek inti `Project`.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Step‑by‑Step Guide

### Step 1: Set Your Document Directory
Tentukan folder tempat file MPP sumber berada dan tempat PDF yang dihasilkan akan ditulis. Menggunakan jalur absolut atau relatif keduanya dapat; pastikan folder tersebut ada.

```java
String dataDir = "Your Document Directory";
```

### Step 2: Load the Project File
Buat instance `Project` dengan memuat file MPP yang ada. Objek ini mewakili seluruh struktur proyek dalam memori.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Step 3: Configure Save Options – Export MPP to PDF
Instansiasi `PdfSaveOptions` dan beri tahu Aspose.Tasks bahwa Anda menginginkan PDF dirender sebagai **task sheet**. Ini adalah langkah kunci untuk kasus penggunaan *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Step 4: Save the Project as a Task Sheet – Save Project as PDF
Panggil metode `save` pada objek `Project`, berikan nama file target dan opsi yang telah dikonfigurasi. Tindakan ini **mengonversi file MPP ke PDF** yang diformat sebagai lembar tugas.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Step 5: Review the Result
Arahkan ke direktori yang Anda tentukan (`dataDir`). Anda seharusnya melihat `taskSheet.pdf` yang berisi daftar semua tugas dengan format rapi. Buka dengan penampil **PDF** apa pun untuk memverifikasi bahwa konversi berhasil.

## Common Issues and Solutions
- **FileNotFoundException** – Pastikan `dataDir` diakhiri dengan pemisah jalur (`/` atau `\\`) dan nama file MPP sudah benar.  
- **LicenseException** – Jika Anda melihat kesalahan lisensi, terapkan lisensi sementara atau berbayar sebelum memanggil API Aspose.Tasks apa pun.  
- **Blank PDF** – Pastikan proyek memang berisi tugas; proyek kosong akan menghasilkan PDF kosong.

## Frequently Asked Questions

**Q: Is Aspose.Tasks compatible with all Java versions?**  
A: Yes, Aspose.Tasks works with a wide range of Java versions. See the [documentation](https://reference.aspose.com/tasks/java/) for details.

**Q: Can I try Aspose.Tasks before purchasing?**  
A: Absolutely! Explore the free trial version [here](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: Join the Aspose.Tasks community on the [forum](https://forum.aspose.com/c/tasks/15) for support and discussions.

**Q: How do I obtain a temporary license for Aspose.Tasks?**  
A: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I purchase Aspose.Tasks for Java?**  
A: Purchase Aspose.Tasks for Java [here](https://purchase.aspose.com/buy).

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda telah mempelajari cara **save project as PDF**, khususnya merender lembar tugas, menggunakan Aspose.Tasks untuk Java. Kemampuan ini memungkinkan Anda *export MPP to PDF* dengan cepat, berbagi snapshot proyek yang dapat dibaca, dan mengintegrasikan data proyek ke dalam alur kerja pelaporan yang lebih luas.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}