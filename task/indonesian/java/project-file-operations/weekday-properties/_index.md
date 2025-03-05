---
title: Properti Hari Kerja di Aspose.Tasks
linktitle: Properti Hari Kerja di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola properti hari kerja secara efisien di Aspose.Tasks untuk Java. Sesuaikan tanggal mulai minggu, hari per bulan, dan lainnya dengan mudah.
type: docs
weight: 25
url: /id/java/project-file-operations/weekday-properties/
---
## Perkenalan
Aspose.Tasks untuk Java adalah API canggih yang memungkinkan pengembang Java bekerja dengan file Microsoft Project tanpa menginstal Microsoft Project di mesin. Salah satu fungsi utamanya adalah mengelola properti hari kerja, memungkinkan pengguna menyesuaikan tanggal mulai minggu, hari per bulan, menit per hari, dan menit per minggu. Tutorial ini akan memberikan panduan rinci tentang cara memanfaatkan fitur-fitur ini secara efektif.
## Prasyarat
Sebelum mendalami Aspose.Tasks untuk Java, pastikan Anda memiliki prasyarat berikut:
### Kit Pengembangan Java (JDK)
Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduh dan menginstal JDK terbaru dari situs Oracle.
### Aspose.Tugas untuk Perpustakaan Java
 Unduh dan instal perpustakaan Aspose.Tasks untuk Java dari situs web. Anda dapat mengakses tautan unduhan[Di Sini](https://releases.aspose.com/tasks/java/).
### Lingkungan Pengembangan Terpadu (IDE)
Pilih IDE pilihan Anda untuk pengembangan Java. Pilihan populer termasuk IntelliJ IDEA, Eclipse, atau NetBeans.
## Paket Impor
Untuk memulai, impor paket Aspose.Tasks yang diperlukan ke proyek Java Anda. Begini caranya:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk pemahaman yang lebih baik.
## Langkah 1: Muat File Proyek
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Langkah ini melibatkan memuat file Proyek bernama "project.mpp" dari direktori data yang ditentukan.
## Langkah 2: Tampilkan Properti Hari Kerja
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Di sini, kami mengambil dan mencetak properti tanggal mulai minggu, hari per bulan, menit per hari, dan menit per minggu dari proyek yang dimuat.
## Langkah 3: Mengatur Properti Hari Kerja
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Langkah ini melibatkan pembuatan instance proyek baru dan pengaturan properti hari kerja khusus seperti hari mulai minggu, hari per bulan, menit per hari, dan menit per minggu.
## Langkah 4: Simpan Proyek
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Terakhir, kami menyimpan proyek yang dimodifikasi dengan properti hari kerja yang diperbarui sebagai file XML.
## Langkah 5: Tampilkan Hasil
```java
System.out.println("Process completed Successfully");
```
Langkah ini mengonfirmasi keberhasilan penyelesaian proses.
## Kesimpulan
Menguasai properti hari kerja di Aspose.Tasks untuk Java sangat penting untuk manajemen proyek yang efektif. Dengan mengikuti tutorial ini, Anda telah mempelajari cara memanipulasi dan menyesuaikan properti hari kerja dengan mudah. Jelajahi dokumentasi dan contoh lebih lanjut untuk meningkatkan kemampuan manajemen proyek Anda.
## FAQ
### T: Dapatkah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?
J: Ya, Aspose.Tasks untuk Java memberikan dukungan komprehensif untuk menangani struktur proyek yang kompleks dengan mudah.
### T: Apakah Aspose.Tasks untuk Java kompatibel dengan versi file Microsoft Project yang berbeda?
J: Tentu saja, Aspose.Tasks untuk Java mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas antar platform.
### T: Bisakah saya mengintegrasikan Aspose.Tasks for Java ke dalam aplikasi Java saya yang sudah ada?
J: Ya, Aspose.Tasks untuk Java menawarkan kemampuan integrasi yang lancar, memungkinkan Anda menyempurnakan aplikasi Java dengan fitur manajemen proyek yang canggih.
### T: Apakah Aspose.Tasks untuk Java menyediakan dokumentasi dan dukungan?
 J: Ya, Anda dapat mengakses dokumentasi ekstensif dan dukungan komunitas untuk Aspose.Tasks for Java di situs mereka[situs web](https://releases.aspose.com/).
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
J: Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis untuk Java dari situs mereka[situs web](https://reference.aspose.com/tasks/java/) untuk menjelajahi fitur-fiturnya sebelum melakukan pembelian.