---
title: Perhitungan Persentase Sumber Daya Proyek MS dengan Aspose.Tasks
linktitle: Lakukan Penghitungan Persentase Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menghitung persentase sumber daya MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah dengan contoh kode disertakan.
type: docs
weight: 14
url: /id/java/resource-management/percentage-calculations/
---
## Perkenalan
Selamat datang di panduan langkah demi langkah kami dalam melakukan penghitungan persentase untuk sumber daya MS Project menggunakan Aspose.Tasks untuk Java. Dalam tutorial ini, kita akan mempelajari proses memanfaatkan Aspose.Tasks untuk memanipulasi dan mengekstrak data sumber daya dari file Microsoft Project secara efisien. Aspose.Tasks adalah Java API canggih yang menyediakan fitur komprehensif untuk bekerja dengan dokumen Microsoft Project, memungkinkan pengembang mengintegrasikan fungsi manajemen proyek ke dalam aplikasi Java mereka dengan lancar.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
### Lingkungan Pengembangan Jawa
 Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari[Di Sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Perpustakaan Aspose.Tugas
Anda harus memiliki perpustakaan Aspose.Tasks yang terintegrasi ke dalam proyek Java Anda. Jika Anda belum melakukannya, Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/tasks/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi[Di Sini](https://reference.aspose.com/tasks/java/).

## Paket Impor
Sebelum kita mulai coding, mari impor paket yang diperlukan untuk tutorial ini:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## Langkah 1: Siapkan Jalur File Proyek
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur ke file Microsoft Project Anda.
## Langkah 2: Muat Proyek
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Kode ini memuat file Microsoft Project bernama "Software Development.mpp" yang terletak di direktori data yang ditentukan.
## Langkah 3: Ulangi Melalui Sumber Daya
```java
for (Resource res : prj.getResources()) {
```
Kami mengulang setiap sumber daya dalam proyek.
## Langkah 4: Periksa Nama Sumber Daya dan Persentase Pekerjaan yang Selesai
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Kami memeriksa apakah nama sumber daya tidak nol dan kemudian mencetak persentase pekerjaan yang diselesaikan untuk setiap sumber daya.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara memanfaatkan Aspose.Tasks untuk Java untuk melakukan penghitungan persentase sumber daya MS Project secara efisien. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengintegrasikan fungsi manajemen proyek ke dalam aplikasi Java Anda, memberikan kontrol dan wawasan yang lebih baik mengenai pemanfaatan sumber daya proyek.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks untuk Java dengan kerangka Java lainnya?
Ya, Aspose.Tasks untuk Java kompatibel dengan berbagai kerangka kerja Java seperti Spring, Hibernate, dan banyak lagi.
### Apakah Aspose.Tasks mendukung semua versi file Microsoft Project?
Aspose.Tasks menyediakan dukungan untuk semua versi file Microsoft Project, termasuk MPP, MPT, XML, dan banyak lagi.
### Bisakah saya memanipulasi jadwal proyek menggunakan Aspose.Tasks?
Tentu saja, Aspose.Tasks menawarkan fitur komprehensif untuk memanipulasi jadwal proyek, termasuk tugas, sumber daya, kalender, dan banyak lagi.
### Apakah ada forum komunitas untuk dukungan Aspose.Tasks?
 Ya, Anda dapat menemukan bantuan dan berinteraksi dengan pengguna lain di forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### Apakah Aspose.Tasks menawarkan lisensi sementara untuk tujuan evaluasi?
 Ya, Anda dapat memperoleh izin sementara untuk evaluasi dari[Di Sini](https://purchase.aspose.com/temporary-license/).