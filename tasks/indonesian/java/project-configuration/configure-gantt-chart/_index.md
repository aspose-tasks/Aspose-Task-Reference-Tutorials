---
title: Konfigurasikan Tampilan Gantt Chart di Proyek Aspose.Tasks
linktitle: Konfigurasikan Tampilan Gantt Chart di Proyek Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengonfigurasi Tampilan Bagan Proyek Gantt MS di Aspose.Tasks menggunakan Java. Sesuaikan proyek dan visualisasikan dalam bagan Gantt dengan langkah demi langkah.
weight: 10
url: /id/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurasikan Tampilan Gantt Chart di Proyek Aspose.Tasks

## Perkenalan
Dalam tutorial ini, Anda akan mempelajari cara mengonfigurasi Tampilan Bagan Proyek Gantt MS di proyek Aspose.Tasks menggunakan Java. Aspose.Tasks adalah Java API canggih yang memungkinkan Anda bekerja dengan file Microsoft Project secara terprogram. Dengan mengikuti langkah-langkah ini, Anda akan dapat menyesuaikan tampilan bagan Gantt sesuai dengan kebutuhan proyek Anda.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda.
2.  Perpustakaan Aspose.Tasks: Unduh dan instal perpustakaan Aspose.Tasks. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Pilih IDE pilihan Anda. Tutorial ini menggunakan IntelliJ IDEA, tetapi Anda dapat menggunakan IDE apa pun yang Anda sukai.
## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan untuk bekerja dengan Aspose.Tasks di proyek Java Anda. Tambahkan pernyataan import berikut ke file Java Anda:
```java
import com.aspose.tasks.*;
```
Sekarang, mari kita uraikan proses konfigurasi Tampilan Bagan Proyek Gantt MS menjadi petunjuk langkah demi langkah:
## Langkah 1: Siapkan Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur ke direktori data proyek Anda.
## Langkah 2: Muat File Proyek
```java
Project project = new Project(dataDir + "project.mpp");
```
Muat file proyek Anda (`project.mpp` dalam contoh ini) menggunakan`Project` kelas dari Aspose.Tasks.
## Langkah 3: Tambahkan Aktivitas Baru
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Buat tugas baru di proyek Anda menggunakan`Task` kelas dan menambahkannya ke anak-anak tugas root.
## Langkah 4: Tentukan Atribut Khusus
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Tentukan atribut khusus baru menggunakan`ExtendedAttributeDefinition`kelas dan menambahkannya ke atribut perluasan proyek.
## Langkah 5: Tambahkan Atribut Khusus ke Tugas
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Tambahkan atribut khusus ke tugas yang dibuat menggunakan`createExtendedAttribute` metode.
## Langkah 6: Sesuaikan Tabel
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Sesuaikan tabel dengan menambahkan kolom atribut teks dengan lebar, judul, dan perataan yang ditentukan.
## Langkah 7: Simpan Proyek
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Simpan proyek dengan Tampilan Bagan Proyek Gantt MS yang dikonfigurasi. File yang dihasilkan dapat dibuka di Microsoft Project 2010.
## Kesimpulan
Selamat! Anda telah berhasil mengonfigurasi Tampilan Bagan Proyek Gantt MS di proyek Aspose.Tasks menggunakan Java. Anda sekarang dapat menyesuaikan atribut proyek dan memvisualisasikannya dalam bagan Gantt sesuai dengan kebutuhan proyek Anda.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?
J: Ya, Aspose.Tasks tersedia untuk berbagai bahasa pemrograman termasuk .NET, Java, dan C++.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 J: Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?
J: Anda dapat menemukan dukungan dan mengajukan pertanyaan di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### T: Bagaimana cara membeli lisensi untuk Aspose.Tasks?
 J: Anda dapat membeli lisensi dari[Di Sini](https://purchase.aspose.com/buy).
### T: Apakah saya memerlukan lisensi sementara untuk tujuan pengujian?
 J: Ya, Anda bisa mendapatkan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
