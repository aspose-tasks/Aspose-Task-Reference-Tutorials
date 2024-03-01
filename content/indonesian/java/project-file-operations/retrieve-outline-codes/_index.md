---
title: Ambil Kode Garis Besar Proyek MS di Aspose.Tasks
linktitle: Ambil Kode Garis Besar di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengambil kode kerangka Microsoft Project secara terprogram menggunakan Aspose.Tasks untuk Java. Tingkatkan kemampuan manajemen proyek Anda.
type: docs
weight: 15
url: /id/java/project-file-operations/retrieve-outline-codes/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengambil kode kerangka Microsoft Project menggunakan Aspose.Tasks untuk Java. Kode garis besar di MS Project menyediakan cara terstruktur untuk mengkategorikan dan mengatur tugas, sumber daya, dan penugasan proyek. Aspose.Tasks adalah pustaka Java canggih yang memungkinkan pengembang memanipulasi dan mengelola file Microsoft Project secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda telah menyiapkan prasyarat berikut:
### 1. Lingkungan Pengembangan Java
Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari situs web Oracle.
### 2. Perpustakaan Aspose.Tugas
 Unduh dan sertakan perpustakaan Aspose.Tasks dalam proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Aspose.Tugas untuk Halaman Unduhan Java](https://releases.aspose.com/tasks/java/).
## Paket Impor
Pertama, impor paket yang diperlukan dari Aspose.Tasks dalam kode Java Anda:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Sekarang mari kita uraikan kode contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Muat Proyek
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 Pada langkah ini, kami memuat file Microsoft Project ke dalam a`Project` objek menggunakan nama file yang disediakan.
## Langkah 2: Ambil Kode Garis Besar
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Kami mengulangi setiap definisi kode garis besar dalam proyek.
## Langkah 3: Akses Properti Kode Garis Besar
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Kami mengambil dan mencetak berbagai properti definisi kode kerangka seperti Alias, ID Bidang, dan Nama Bidang.
## Langkah 4: Periksa Kode Kustom Perusahaan
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Kami memeriksa apakah kode garis besar adalah kode khusus perusahaan dan mencetak hasilnya sesuai.
## Langkah 5: Tampilkan Masker Kode Garis Besar
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Kami mengulangi setiap topeng yang terkait dengan kode kerangka dan mencetak level dan nilai topengnya.
## Langkah 6: Tampilkan Nilai Kode Garis Besar
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Kami mengulangi setiap nilai kode garis besar dan mencetak deskripsi, ID nilai, nilai, dan jenisnya.
## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara mengambil kode kerangka Proyek MS menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat mengakses dan memanipulasi kode kerangka secara efektif dalam aplikasi Java Anda, sehingga memungkinkan kemampuan manajemen proyek tingkat lanjut.
## FAQ
### Q1: Dapatkah saya menggunakan Aspose.Tasks untuk Java untuk mengubah kode kerangka dalam file Proyek?
J: Ya, Aspose.Tasks untuk Java menyediakan API untuk mengubah kode kerangka dalam file MS Project secara terprogram.
### Q2: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis untuk Java dari[Situs web Aspose.Tasks](https://releases.aspose.com/).
### Q3: Bagaimana saya bisa mendapatkan dukungan teknis untuk Aspose.Tasks untuk Java?
 J: Anda bisa mendapatkan dukungan teknis dengan mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) dan memposting pertanyaan Anda di sana.
### Q4: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat membeli lisensi sementara untuk Aspose.Tasks untuk Java dari[halaman pembelian](https://purchase.aspose.com/temporary-license/).
### Q5: Di mana saya dapat menemukan dokumentasi lengkap Aspose.Tasks untuk Java?
 J: Anda bisa merujuk ke[dokumentasi](https://reference.aspose.com/tasks/java/) untuk informasi mendetail tentang penggunaan Aspose.Tasks untuk Java.