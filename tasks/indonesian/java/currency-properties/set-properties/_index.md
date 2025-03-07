---
title: Tetapkan Properti Mata Uang di Proyek Aspose.Tasks
linktitle: Tetapkan Properti Mata Uang di Proyek Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengatur properti mata uang di proyek Aspose.Tasks menggunakan Java. Memanipulasi file Microsoft Project dengan mudah.
weight: 11
url: /id/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tetapkan Properti Mata Uang di Proyek Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengatur properti mata uang di proyek Aspose.Tasks menggunakan Java. Aspose.Tasks adalah perpustakaan Java yang kuat yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks for Java Library: Unduh dan instal perpustakaan Aspose.Tasks for Java dari[tautan unduhan](https://releases.aspose.com/tasks/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Pilih IDE pilihan Anda seperti Eclipse atau IntelliJ IDEA.
## Paket Impor
Pertama, mari impor paket yang diperlukan untuk bekerja dengan Aspose.Tasks di Java.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## Langkah 1: Tetapkan Direktori Data
Tetapkan direktori data tempat file proyek Anda berada.
```java
String dataDir = "Your Data Directory";
```
## Langkah 2: Buat Instans Proyek
Buat instans proyek baru menggunakan Aspose.Tasks.
```java
Project project = new Project();
```
## Langkah 3: Tetapkan Properti Mata Uang
Sekarang, mari kita atur properti mata uang untuk proyek tersebut.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## Langkah 4: Simpan Proyek
Simpan proyek dengan properti mata uang yang diperbarui.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## Langkah 5: Tampilkan Pesan Penyelesaian
Menampilkan pesan yang menunjukkan keberhasilan penyelesaian proses.
```java
System.out.println("Process completed Successfully");
```
Selamat! Anda telah berhasil menyetel properti mata uang di proyek Aspose.Tasks menggunakan Java.
## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menggunakan Aspose.Tasks untuk Java untuk mengatur properti mata uang dalam file proyek. Dengan Aspose.Tasks, pengembang dapat memanipulasi data proyek secara efisien, menjadikannya alat yang berharga untuk aplikasi manajemen proyek.
## FAQ
### Bisakah saya menetapkan banyak mata uang dalam satu proyek menggunakan Aspose.Tasks?
Ya, Aspose.Tasks memungkinkan Anda menangani banyak mata uang dalam satu file proyek.
### Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?
Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.
### Apakah Aspose.Tasks menyediakan dukungan untuk format mata uang khusus?
Tentu saja, Aspose.Tasks menawarkan fleksibilitas dalam menentukan format mata uang khusus untuk memenuhi persyaratan proyek tertentu.
### Bisakah saya mengintegrasikan Aspose.Tasks dengan pustaka atau kerangka kerja Java lainnya?
Ya, Aspose.Tasks dapat diintegrasikan dengan lancar dengan pustaka dan kerangka kerja Java lainnya, sehingga meningkatkan fungsionalitas dan keserbagunaannya.
### Di mana saya dapat menemukan dukungan atau bantuan tambahan untuk Aspose.Tasks?
 Untuk dukungan tambahan, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15), tempat Anda dapat menemukan sumber daya bermanfaat dan terlibat dengan komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
