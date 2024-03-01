---
title: Baca Data Tabel dari File di Aspose.Tasks
linktitle: Baca Data Tabel dari File di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Buka kekuatan Aspose.Tasks untuk Java. Pelajari cara mengekstrak data tabel dari file dalam tutorial komprehensif ini.
type: docs
weight: 17
url: /id/java/project-data-reading/read-table-data/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara membaca data tabel dari file menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah pustaka Java canggih yang memungkinkan pengembang bekerja dengan dokumen Microsoft Project secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduh dan menginstalnya dari situs web Oracle.
2.  File JAR Aspose.Tasks untuk Java: Unduh perpustakaan Aspose.Tasks untuk Java dari[tautan unduhan](https://releases.aspose.com/tasks/java/) dan sertakan dalam proyek Java Anda.

## Paket Impor
Impor paket yang diperlukan untuk bekerja dengan Aspose.Tasks di proyek Java Anda:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## Langkah 1: Siapkan Direktori Data
Tentukan jalur ke direktori tempat file Proyek Anda berada:
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur sebenarnya ke direktori data Anda.
## Langkah 2: Muat File Proyek
Muat file Proyek menggunakan Aspose.Tasks:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 Pastikan untuk mengganti`"Project2003.mpp"` dengan nama file Proyek Anda.
## Langkah 3: Ambil Informasi Tabel
Dapatkan tabel dari proyek dan ulangi bidangnya:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
Cuplikan kode ini mengambil informasi tentang bidang tabel seperti lebar, judul, dan perataan.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara membaca data tabel dari file menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat mengekstrak dan memanipulasi data secara efisien dari dokumen Microsoft Project di aplikasi Java Anda.
## FAQ
### T: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?
J: Aspose.Tasks mendukung berbagai versi Microsoft Project, termasuk Project 2003, 2007, 2010, 2013, dan 2016.
### T: Dapatkah saya mengubah data tabel dan menyimpannya kembali ke file Proyek?
J: Ya, Anda dapat menggunakan Aspose.Tasks untuk mengubah data tabel secara terprogram dan menyimpan perubahan ke file Proyek asli.
### T: Apakah Aspose.Tasks memerlukan lisensi terpisah untuk penggunaan komersial?
 J: Ya, Anda perlu membeli lisensi Aspose.Tasks jika Anda ingin menggunakannya dalam lingkungan komersial. Anda dapat memperoleh lisensi dari[halaman pembelian](https://purchase.aspose.com/buy).
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 J: Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis dari[halaman rilis](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan bantuan dan dukungan untuk Aspose.Tasks?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15)atas bantuan dan dukungan dari komunitas dan tim Aspose.