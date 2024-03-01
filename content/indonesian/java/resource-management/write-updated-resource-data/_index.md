---
title: Tulis Data Sumber Daya yang Diperbarui di Aspose.Tasks
linktitle: Tulis Data Sumber Daya yang Diperbarui di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara memperbarui data sumber daya dengan mudah di file MS Project menggunakan Aspose.Tasks untuk Java.
type: docs
weight: 21
url: /id/java/resource-management/write-updated-resource-data/
---
## Perkenalan
Dalam tutorial ini, kami akan memandu Anda dalam memperbarui data sumber daya Microsoft Project menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah Java API canggih yang memungkinkan Anda memanipulasi file Microsoft Project tanpa memerlukan Microsoft Project untuk diinstal di sistem Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Tugas untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Pengetahuan dasar tentang pemrograman Java.

## Paket Impor

Pertama, Anda perlu mengimpor paket yang diperlukan untuk bekerja dengan Aspose.Tasks dalam kode Java Anda. Tambahkan pernyataan import berikut ke file Java Anda:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Langkah 1: Siapkan Direktori Data Anda

Tentukan direktori tempat file data Anda berada:

```java
String dataDir = "Your Data Directory";
```

## Langkah 2: Tentukan File Input dan Output

Tentukan jalur untuk file input MS Project dan file yang diperbarui yang dihasilkan:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Uji file dengan satu rsc untuk diperbarui
String resultFile = dataDir + "OutputMPP.mpp"; // File untuk menulis proyek uji
```

## Langkah 3: Muat Proyek

 Muat file Proyek MS ke dalam a`Project` obyek:

```java
Project project = new Project(file);
```

## Langkah 4: Tambahkan Sumber Daya dan Tetapkan Atribut

Tambahkan sumber daya baru ke proyek dan atur atributnya seperti tarif standar, tarif lembur, dan grup:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Langkah 5: Simpan Proyek

Simpan proyek yang diperbarui dengan data sumber daya yang dimodifikasi:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Kesimpulan

Dalam tutorial ini, kami telah menunjukkan cara memperbarui data sumber daya MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat secara efisien memanipulasi informasi sumber daya dalam file MS Project Anda secara terprogram.

## FAQ

### Q1: Dapatkah saya memperbarui beberapa sumber daya dalam proyek yang sama menggunakan Aspose.Tasks untuk Java?

A1: Ya, Anda dapat memperbarui beberapa sumber daya dengan mengulanginya dan mengatur atributnya sesuai dengan itu.

### Q2: Apakah Aspose.Tasks mendukung format file lain selain MS Project?

A2: Ya, Aspose.Tasks mendukung berbagai format file termasuk XML, MPP, dan lainnya.

### Q3: Apakah Aspose.Tasks kompatibel dengan versi Java yang berbeda?

A3: Aspose.Tasks kompatibel dengan Java versi 6 ke atas.

### Q4: Dapatkah saya melakukan operasi lain pada file MS Project dengan Aspose.Tasks?

A4: Ya, Anda dapat melakukan berbagai operasi seperti membaca, menulis, dan memanipulasi tugas, sumber daya, dan kalender.

### Q5: Di mana saya dapat menemukan bantuan atau dukungan tambahan untuk Aspose.Tasks?

 A5: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun.
