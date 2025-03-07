---
title: Baca Data Fase Waktu untuk Sumber Daya di Aspose.Tasks
linktitle: Baca Data Fase Waktu untuk Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengekstrak data bertahap dari sumber daya MS Project menggunakan Aspose.Tasks untuk Java. Tutorial langkah demi langkah.
weight: 15
url: /id/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Data Fase Waktu untuk Sumber Daya di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses membaca data bertahap untuk sumber daya MS Project menggunakan Aspose.Tasks untuk Java. Pustaka ini menyediakan fungsionalitas canggih untuk mengelola file Microsoft Project secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari[situs web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) dan ikuti petunjuk instalasi.
2.  Aspose.Tasks untuk Perpustakaan Java: Unduh perpustakaan Aspose.Tasks untuk Java dari[Unduh Halaman](https://releases.aspose.com/tasks/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

## Paket Impor
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Langkah 1: Siapkan Direktori Data
Pertama, tentukan direktori tempat file MS Project Anda berada.
```java
String dataDir = "Your Data Directory";
```
## Langkah 2: Baca File Templat Proyek MS
Tentukan nama file template MS Project Anda.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Langkah 3: Baca File Input sebagai Proyek
Baca file input menggunakan Aspose.Tasks dan muat sebagai objek Proyek.
```java
Project project = new Project(dataDir + fileName);
```
## Langkah 4: Dapatkan Sumber Daya berdasarkan ID
Ambil sumber daya yang diinginkan dari proyek dengan pengidentifikasi uniknya (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Langkah 5: Cetak Data Bertahap Waktu untuk Pekerjaan Sumber Daya
Cetak data bertahap waktu untuk pekerjaan sumber daya.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Langkah 6: Cetak Data Bertahap Waktu untuk Biaya Sumber Daya
Cetak data bertahap waktu untuk biaya sumber daya.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara membaca data bertahap untuk sumber daya MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat secara efisien mengekstrak informasi berharga dari file proyek Anda secara terprogram.
## FAQ
### Bisakah Aspose.Tasks menangani jenis file proyek lain selain dari Microsoft Project?
Ya, Aspose.Tasks mendukung berbagai format file, termasuk MPP, XML, dan CSV.
### Apakah Aspose.Tasks kompatibel dengan lingkungan pengembangan Java yang berbeda?
Ya, Aspose.Tasks kompatibel dengan semua IDE dan kerangka kerja Java utama.
### Bisakah saya memanipulasi data proyek menggunakan Aspose.Tasks?
Tentu saja, Aspose.Tasks menyediakan API ekstensif untuk membuat, memodifikasi, dan menganalisis data proyek.
### Apakah Aspose.Tasks cocok untuk proyek tingkat perusahaan?
Ya, Aspose.Tasks banyak digunakan di lingkungan perusahaan karena keandalan dan skalabilitasnya.
### Di mana saya dapat menemukan dukungan jika saya mengalami masalah saat menggunakan Aspose.Tasks?
 Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) atas bantuan dari masyarakat dan tim pendukung.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
