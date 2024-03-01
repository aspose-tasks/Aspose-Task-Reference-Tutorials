---
title: Simpan Sebagai CSV, Teks, dan Templat di Aspose.Tasks
linktitle: Simpan Sebagai CSV, Teks, dan Templat di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menyimpan file Microsoft Project dalam format CSV, Teks, dan Templat menggunakan Aspose.Tasks untuk Java.
type: docs
weight: 16
url: /id/java/project-file-operations/save-csv-text-template/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menyimpan file proyek dalam berbagai format seperti CSV, Teks, dan Templat menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah pustaka Java canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project tanpa perlu menginstal Microsoft Project.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Tasks untuk perpustakaan Java diunduh dan dikonfigurasi di proyek Java Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Pengetahuan dasar bahasa pemrograman Java.

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan ke file Java Anda:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Simpan Proyek Sebagai CSV
Mari kita uraikan langkah-langkah untuk menyimpan proyek sebagai CSV:
### Langkah 1: Muat Proyek
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Langkah 2: Simpan sebagai CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Simpan Proyek Sebagai Teks
Inilah cara Anda dapat menyimpan proyek sebagai Teks:
### Langkah 1: Muat Proyek
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Langkah 2: Simpan sebagai Teks
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Simpan Proyek Sebagai Templat
Menyimpan proyek sebagai templat melibatkan langkah-langkah berikut:
### Langkah 1: Muat Proyek
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Langkah 2: Tetapkan Opsi Templat
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Langkah 3: Simpan sebagai Templat
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menyimpan file Microsoft Project sebagai CSV, Teks, dan Templat menggunakan Aspose.Tasks untuk Java. Dengan langkah-langkah sederhana ini, Anda dapat mengelola file proyek Anda secara efisien dalam berbagai format, sehingga meningkatkan produktivitas Anda sebagai pengembang Java.
## FAQ
### T: Dapatkah Aspose.Tasks untuk Java menangani file proyek yang kompleks?
J: Tentu saja! Aspose.Tasks untuk Java dapat menangani proyek dengan kompleksitas yang berbeda-beda dengan mudah, memberikan dukungan komprehensif untuk format file Microsoft Project.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks untuk Java dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun mengenai Aspose.Tasks untuk Java.
### T: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat membeli lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/), memungkinkan Anda mengevaluasi potensi penuh perpustakaan.
### T: Apakah Aspose.Tasks untuk Java kompatibel dengan sistem operasi yang berbeda?
J: Ya, Aspose.Tasks for Java kompatibel dengan berbagai sistem operasi, termasuk Windows, macOS, dan Linux.