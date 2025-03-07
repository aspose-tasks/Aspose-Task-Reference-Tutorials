---
title: Kelola Properti Tahun Anggaran di Aspose.Tasks
linktitle: Kelola Properti Tahun Anggaran di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola properti tahun fiskal secara efisien menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah dengan contoh disediakan.
weight: 15
url: /id/java/project-management/fiscal-year-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola Properti Tahun Anggaran di Aspose.Tasks

## Perkenalan
Aspose.Tasks adalah pustaka Java canggih yang memungkinkan pengembang mengelola file proyek secara efisien, termasuk menangani properti tahun fiskal. Dalam tutorial ini, kita akan memandu proses pengelolaan properti tahun fiskal menggunakan Aspose.Tasks di Java.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks untuk Java JAR: Unduh perpustakaan Aspose.Tasks untuk Java dari[Di Sini](https://releases.aspose.com/tasks/java/) dan sertakan dalam proyek Anda.

## Paket Impor
Untuk memulai, impor paket yang diperlukan ke file Java Anda:
```java
import com.aspose.tasks.*;
```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Muat File Proyek
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Pada langkah ini, kita memuat file proyek bernama "project.mpp" yang terletak di direktori data yang ditentukan.
## Langkah 2: Tampilkan Properti Tahun Anggaran
```java
//Menampilkan properti tahun fiskal
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
Langkah ini mengambil dan mencetak tanggal mulai dan penomoran tahun fiskal dari proyek yang dimuat.
## Langkah 3: Menetapkan Properti Tahun Anggaran Proyek
```java
//Buat contoh proyek
Project prj = new Project();
//Tetapkan properti tahun fiskal
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Simpan proyek sebagai file proyek XML
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Di sini, kami membuat contoh proyek baru, menetapkan tanggal mulai tahun fiskal ke Juli dan mengaktifkan penomoran tahun fiskal. Kemudian, kami menyimpan proyek yang dimodifikasi sebagai file XML.
## Langkah 4: Tampilkan Hasil
```java
//Tampilkan hasil konversi.
System.out.println("Process completed Successfully");
```
Terakhir, kami mencetak pesan yang menunjukkan keberhasilan penyelesaian proses.

## Kesimpulan
Mengelola properti tahun fiskal di Aspose.Tasks untuk Java sangatlah mudah dengan API yang disediakan. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara efisien menangani tugas-tugas terkait tahun fiskal di proyek Anda.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks for Java untuk memanipulasi properti proyek lainnya?
J: Ya, Aspose.Tasks menyediakan fungsionalitas komprehensif untuk mengelola berbagai properti proyek selain properti tahun fiskal.
### T: Apakah Aspose.Tasks untuk Java kompatibel dengan format file proyek yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai format file proyek termasuk MPP, XML, dan lainnya.
### T: Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah apa pun saat menggunakan Aspose.Tasks untuk Java?
 J: Anda dapat mencari bantuan dari komunitas Aspose.Tasks di[forum](https://forum.aspose.com/c/tasks/15)atau hubungi tim dukungan mereka secara langsung.
### T: Apakah Aspose.Tasks menawarkan versi uji coba gratis?
 J: Ya, Anda dapat mengakses Aspose.Tasks versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat membeli lisensi Aspose.Tasks untuk Java?
 J: Anda dapat membeli lisensi Aspose.Tasks untuk Java dari[Di Sini](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
