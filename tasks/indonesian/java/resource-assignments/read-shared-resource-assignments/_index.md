---
title: Baca Penugasan Sumber Daya Bersama di Aspose.Tasks
linktitle: Baca Penugasan Sumber Daya Bersama di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara membaca penetapan sumber daya bersama di Aspose.Tasks untuk Java. Tingkatkan efisiensi manajemen proyek dengan tutorial langkah demi langkah.
weight: 19
url: /id/java/resource-assignments/read-shared-resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Penugasan Sumber Daya Bersama di Aspose.Tasks

## Perkenalan
Dalam manajemen proyek, alokasi sumber daya yang efisien sangat penting untuk keberhasilan penyelesaian proyek. Aspose.Tasks untuk Java menyediakan alat canggih untuk mengelola sumber daya secara efektif. Salah satu tugas penting adalah membaca penetapan sumber daya bersama, yang memungkinkan Anda memahami bagaimana sumber daya dialokasikan di beberapa proyek.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar bahasa pemrograman Java.
- JDK (Java Development Kit) diinstal pada sistem Anda.
-  Aspose.Tasks untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
Untuk memulai, impor paket yang diperlukan dalam kode Java Anda:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

Mari kita bagi contoh ini menjadi beberapa langkah:
## Langkah 1: Tentukan Direktori Data
```java
String dataDir = "Your Data Directory";
```
Tentukan direktori tempat data proyek Anda berada.
## Langkah 2: Muat File Proyek
```java
Project project = new Project(dataDir + "ResourceCosts.mpp");
```
Muat file proyek yang berisi penetapan sumber daya bersama.
## Langkah 3: Akses Sumber Daya
```java
Resource resource = project.getResources().getByUid(1);
```
Ambil sumber daya dari proyek dengan pengidentifikasi uniknya (UID).
## Langkah 4: Ambil Unit Sumber Daya
```java
Double units = resource.get(Rsc.PEAK_UNITS);
```
Ambil unit puncak sumber daya, yang dihitung menggunakan penugasan dari proyek lain.

## Kesimpulan
Membaca penetapan sumber daya bersama di Aspose.Tasks untuk Java adalah operasi mendasar untuk manajemen proyek yang efisien. Dengan tutorial yang disediakan, Anda dapat dengan mudah mengakses dan menganalisis alokasi sumber daya di beberapa proyek.
## FAQ
### Bisakah saya mengubah penetapan sumber daya menggunakan Aspose.Tasks untuk Java?
Ya, Anda dapat mengubah dan mengelola penetapan sumber daya secara terprogram.
### Apakah Aspose.Tasks untuk Java kompatibel dengan format file proyek yang berbeda?
Ya, ini mendukung berbagai format file proyek seperti MPP, XML, dan MPX.
### Bisakah saya membuat laporan berdasarkan penugasan sumber daya?
Tentu saja, Aspose.Tasks untuk Java memungkinkan Anda membuat laporan khusus berdasarkan data sumber daya.
### Apakah ada batasan ukuran file proyek yang dapat ditanganinya?
Aspose.Tasks untuk Java dapat menangani proyek dengan berbagai ukuran, dari proyek skala kecil hingga besar.
### Apakah dukungan teknis tersedia untuk Aspose.Tasks untuk pengguna Java?
 Ya, Anda bisa mendapatkan dukungan teknis dari forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
