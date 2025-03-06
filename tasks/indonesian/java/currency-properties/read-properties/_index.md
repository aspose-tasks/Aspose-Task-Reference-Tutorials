---
title: Baca Properti Mata Uang di Proyek Aspose.Tasks
linktitle: Baca Properti Mata Uang di Proyek Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengekstrak informasi mata uang dari file MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah disediakan.
weight: 10
url: /id/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Properti Mata Uang di Proyek Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Aspose.Tasks untuk Java untuk membaca properti mata uang dari file Microsoft Project. Aspose.Tasks adalah API Java yang kuat yang memungkinkan pengembang memanipulasi dokumen Microsoft Project tanpa memerlukan instalasi Microsoft Project. Dengan mengikuti langkah-langkah yang diuraikan di bawah ini, Anda akan dapat mengekstrak informasi terkait mata uang dengan mudah.
## Prasyarat
Sebelum melanjutkan tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks untuk Java JAR: Unduh perpustakaan Aspose.Tasks untuk Java dari[Di Sini](https://releases.aspose.com/tasks/java/) dan sertakan dalam proyek Java Anda.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke kelas Java Anda:
```java
import com.aspose.tasks.*;
```
## Langkah 1: Siapkan Direktori Proyek Anda
Pertama, atur direktori proyek Anda tempat file Microsoft Project Anda berada. Anda dapat menentukan jalur direktori ini sebagai berikut:
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur sebenarnya ke direktori proyek Anda.
## Langkah 2: Buat Instans Pembaca Proyek
 Buat contoh a`Project` objek dengan memberikan jalur ke file Microsoft Project Anda:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Pastikan untuk mengganti`"project.mpp"` dengan nama file MS Project Anda.
## Langkah 3: Tampilkan Properti Mata Uang
Ambil dan tampilkan properti mata uang dari file proyek:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Segmen kode ini mengambil informasi seperti kode mata uang, angka, simbol, dan posisi simbol dari file MS Project dan mencetaknya ke konsol.
## Langkah 4: Penyelesaian Proses
Terakhir, cetak pesan yang menunjukkan keberhasilan penyelesaian proses:
```java
System.out.println("Process completed Successfully");
```
## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara membaca properti mata uang dari file Microsoft Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat dengan mudah mengekstrak informasi terkait mata uang dari file proyek Anda secara terprogram, memungkinkan integrasi yang lancar ke dalam aplikasi Java Anda.
## FAQ
### T: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?
J: Aspose.Tasks mendukung berbagai versi Microsoft Project, termasuk file MPP yang dihasilkan oleh MS Project 2003-2021.
### T: Bisakah saya mengubah properti mata uang menggunakan Aspose.Tasks?
J: Ya, Aspose.Tasks memungkinkan Anda membaca dan mengubah properti mata uang di file MS Project secara terprogram.
### T: Apakah Aspose.Tasks cocok untuk penggunaan komersial?
 J: Ya, Aspose.Tasks adalah perpustakaan komersial yang dirancang untuk penggunaan profesional. Anda dapat membeli lisensi[Di Sini](https://purchase.aspose.com/buy).
### T: Apakah Aspose.Tasks menawarkan uji coba gratis?
 J: Ya, Anda dapat memanfaatkan uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat mencari bantuan atau dukungan untuk Aspose.Tasks?
 J: Anda dapat mengunjungi forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
