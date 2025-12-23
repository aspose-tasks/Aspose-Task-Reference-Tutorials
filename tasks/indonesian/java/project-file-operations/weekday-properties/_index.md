---
date: 2025-12-23
description: Pelajari cara menggunakan Aspose Tasks Java untuk memperbarui jadwal
  proyek, mengatur hari mulai minggu, mengubah hari per bulan, dan menyesuaikan kalender
  proyek secara efisien.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Mengelola Properti Hari Kerja
url: /id/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Mengelola Properti Hari Kerja

## Introduction
Aspose.Tasks for Java (aspose tasks java) adalah API yang kuat yang memungkinkan pengembang Java bekerja dengan file Microsoft Project tanpa perlu menginstal Microsoft Project. Dalam tutorial ini Anda akan belajar cara **memuat file MPP**, **mengatur hari mulai minggu**, **mengubah hari per bulan**, dan **menyesuaikan kalender proyek**—semua langkah penting untuk memperbarui jadwal proyek. Pada akhir tutorial, Anda akan dapat menyesuaikan properti hari kerja secara programatis dan menyimpan perubahan dalam format yang Anda butuhkan.

## Quick Answers
- **Apa kelas utama untuk menangani proyek?** `Project` dari library Aspose.Tasks.  
- **Bagaimana cara mengubah hari mulai minggu?** Gunakan `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Bisakah saya memuat file .mpp yang ada?** Ya—instansiasi `Project` dengan path file.  
- **Metode mana yang menyimpan proyek sebagai XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan gratis dapat digunakan untuk evaluasi; lisensi diperlukan untuk produksi.

## Prerequisites
Sebelum Anda memulai, pastikan Anda memiliki hal berikut:

- **Java Development Kit (JDK)** – versi terbaru terinstal.  
- **Aspose.Tasks for Java library** – unduh di [sini](https://releases.aspose.com/tasks/java/).  
- **IDE** seperti IntelliJ IDEA, Eclipse, atau NetBeans.  

## Import Packages
Untuk memulai, impor kelas Aspose.Tasks yang penting:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Sekarang mari kita bahas setiap langkah mengelola properti hari kerja.

## Step 1: Load an MPP File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Di sini kami **memuat file .mpp yang ada** (`load mpp file`) sehingga kami dapat memeriksa dan mengubah pengaturan kalendernya.*

## Step 2: Display Current Weekday Properties
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Kode ini mencetak **hari mulai minggu**, **hari per bulan**, **menit per hari**, dan **menit per minggu** saat ini—elemen inti yang sering Anda perlukan untuk **menyesuaikan kalender proyek**.

## Step 3: Set New Weekday Properties
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Pada langkah ini kami **mengatur hari mulai minggu** ke Senin, **mengubah hari per bulan** menjadi 24, dan menyesuaikan jumlah menit harian serta mingguan. Pengaturan ini umum ketika Anda perlu **memperbarui jadwal proyek** agar sesuai dengan kalender kerja non‑standar.

## Step 4: Save the Updated Project
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Proyek yang dimodifikasi disimpan sebagai file XML, memudahkan untuk dibagikan atau diimpor ke alat lain.

## Step 5: Confirm the Operation
```java
System.out.println("Process completed Successfully");
```
Pesan konsol sederhana memberi tahu Anda bahwa alur kerja selesai tanpa error.

## Common Issues & Tips
- **Path file tidak tepat** – Pastikan `dataDir` diakhiri dengan slash atau gunakan `Paths.get(...)` untuk path yang independen platform.  
- **Lisensi belum diatur** – Pada lingkungan produksi, panggil `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` sebelum membuat `Project`.  
- **Hari mulai minggu tidak terduga** – Pastikan Anda menggunakan nilai enum `DayType` yang tepat (mis., `DayType.Sunday`).  

## Frequently Asked Questions

**Q: Apakah Aspose.Tasks for Java dapat menangani struktur proyek yang kompleks?**  
A: Ya, Aspose.Tasks for Java menyediakan dukungan komprehensif untuk menangani struktur proyek yang kompleks dengan mudah.

**Q: Apakah Aspose.Tasks for Java kompatibel dengan berbagai versi file Microsoft Project?**  
A: Tentu saja, Aspose.Tasks for Java mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di seluruh platform.

**Q: Bisakah saya mengintegrasikan Aspose.Tasks for Java ke dalam aplikasi Java yang sudah ada?**  
A: Ya, Aspose.Tasks for Java menawarkan kemampuan integrasi yang mulus, memungkinkan Anda meningkatkan aplikasi Java dengan fitur manajemen proyek yang kuat.

**Q: Apakah Aspose.Tasks for Java menyediakan dokumentasi dan dukungan?**  
A: Ya, Anda dapat mengakses dokumentasi lengkap dan dukungan komunitas untuk Aspose.Tasks for Java di [website](https://releases.aspose.com/).

**Q: Apakah ada versi percobaan gratis untuk Aspose.Tasks for Java?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis Aspose.Tasks for Java dari [website](https://reference.aspose.com/tasks/java/) untuk menjelajahi fiturnya sebelum melakukan pembelian.

---

**Terakhir Diperbarui:** 2025-12-23  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}